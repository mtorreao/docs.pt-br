---
title: Como personalizar a codificação de caracteres com System.Text.Json
description: Saiba como personalizar a codificação de caracteres ao serializar e desserializar do JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f6a50a3ca2a5e871294cf7c056cbf197a61cd668
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439907"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a>Como personalizar a codificação de caracteres com System.Text.Json

Por padrão, o serializador escapa todos os caracteres não ASCII. Ou seja, ele substitui por `\uxxxx` onde `xxxx` está o código Unicode do caractere. Por exemplo, se a `Summary` propriedade no JSON a seguir estiver definida como cirílico `жарко` , o `WeatherForecast` objeto será serializado, conforme mostrado neste exemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a>Serializar conjuntos de caracteres de idioma

Para serializar os conjuntos de caracteres de um ou mais idiomas sem saída, especifique os [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) ao criar uma instância do <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> , conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

Este código não sai de escape de caracteres cirílico ou grego. Se a `Summary` propriedade for definida como cirílico `жарко` , o `WeatherForecast` objeto será serializado, conforme mostrado neste exemplo:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Para serializar todos os conjuntos de idiomas sem saída, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType> .

## <a name="serialize-specific-characters"></a>Serializar caracteres específicos

Uma alternativa é especificar os caracteres individuais que você deseja permitir sem ter escape. O exemplo a seguir serializa apenas os dois primeiros caracteres de `жарко` :

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

Aqui está um exemplo de JSON produzido pelo código anterior:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a>Serializar todos os caracteres

Para minimizar a saída, você pode usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> , conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> Em comparação com o codificador padrão, o `UnsafeRelaxedJsonEscaping` codificador é mais permissivo de permitir que os caracteres passem sem escape:
>
> * Ele não sai de caracteres sensíveis a HTML, como `<` ,, `>` `&` e `'` .
> * Ele não oferece nenhuma proteção adicional de defesa profunda contra ataques XSS ou de divulgação de informações, como aqueles que podem resultar do cliente e do servidor que estão descordando no conjunto de *caracteres*.
>
> Use o codificador não seguro somente quando for conhecido que o cliente irá interpretar a carga resultante como JSON codificado em UTF-8. Por exemplo, você pode usá-lo se o servidor estiver enviando o cabeçalho de resposta `Content-Type: application/json; charset=utf-8` . Nunca permita que a `UnsafeRelaxedJsonEscaping` saída bruta seja emitida em uma página HTML ou em um `<script>` elemento.

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Como escrever serializadores personalizados e desserializadores](write-custom-serializer-deserializer.md)
* [Como escrever conversores personalizados para serialização JSON](system-text-json-converters-how-to.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
