---
title: Como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com System.Text.Json
description: Saiba como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas ao serializar e desserializar de JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599070"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a>Como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com System.Text.Json

Neste artigo, você aprenderá a habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com o `System.Text.Json` namespace.

## <a name="case-insensitive-property-matching"></a>Correspondência de propriedade que não diferencia maiúsculas de minúsculas

Por padrão, a desserialização procura as correspondências de nome de propriedade que diferenciam maiúsculas de minúsculas entre JSON e as propriedades do objeto de destino. Para alterar esse comportamento, defina <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> como `true` :

> [!NOTE]
> O [padrão da Web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) não diferencia maiúsculas de minúsculas.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

Aqui está um exemplo de JSON com nomes de Propriedade do camel case. Ele pode ser desserializado no seguinte tipo que tem nomes de propriedade de caso de Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Criar uma instância de JsonSerializerOptions](system-text-json-configure-options.md)
* [Personalizar nomes e valores da propriedade](system-text-json-customize-properties.md)
* [Ignorar propriedades](system-text-json-ignore-properties.md)
* [Permitir JSON inválido](system-text-json-invalid-json.md)
* [Manipular JSON de estouro](system-text-json-handle-overflow.md)
* [Preservar referências circulares](system-text-json-preserve-references.md)
* [Tipos imutáveis e acessadores não públicos](system-text-json-immutability.md)
* [Serialização polimórfica](system-text-json-polymorphism.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
