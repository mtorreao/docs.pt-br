---
title: Como serializar e desserializar JSON usando C#-.NET
description: Saiba como usar o System.Text.Json namespace para serializar e desserializar do JSON no .net. Inclui o código de exemplo.
ms.date: 12/02/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: dc1f8dab0d8d1ab5001797140a3bbfe4a02cb52b
ms.sourcegitcommit: 0014aa4d5cb2da56a70e03fc68f663d64df5247a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96918561"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Como serializar e desserializar (empacotar e desempacotar) JSON no .NET

Este artigo mostra como usar o <xref:System.Text.Json?displayProperty=fullName> namespace para serializar e desserializar de JavaScript Object Notation (JSON). Se você estiver portando um código existente do `Newtonsoft.Json` , consulte [como migrar `System.Text.Json` para o ](system-text-json-migrate-from-newtonsoft-how-to.md).

As direções e o código de exemplo usam a biblioteca diretamente, não por meio de uma estrutura como [ASP.NET Core](/aspnet/core/).

A maior parte do código de exemplo de serialização define <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` "muito impresso" o JSON (com recuo e espaço em branco para legibilidade humana). Para uso em produção, você normalmente aceitaria o valor padrão de `false` para essa configuração.

Os exemplos de código referem-se à seguinte classe e variantes dela:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a>Namespaces

O <xref:System.Text.Json> namespace contém todos os pontos de entrada e os tipos principais. O <xref:System.Text.Json.Serialization> namespace contém atributos e APIs para cenários avançados e personalização específicas para serialização e desserialização. Os exemplos de código mostrados neste artigo exigem `using` diretivas para um ou ambos os namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <xref:System.Runtime.Serialization>Não há suporte para atributos do namespace no `System.Text.Json` .

## <a name="how-to-write-net-objects-as-json-serialize"></a>Como escrever objetos .NET como JSON (Serialize)

Para gravar JSON em uma cadeia de caracteres ou em um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> método.

O exemplo a seguir cria JSON como uma cadeia de caracteres:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

O exemplo a seguir usa código síncrono para criar um arquivo JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

O exemplo a seguir usa código assíncrono para criar um arquivo JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

Os exemplos anteriores usam a inferência de tipos para o tipo que está sendo serializado. Uma sobrecarga de `Serialize()` usa um parâmetro de tipo genérico:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a>Exemplo de serialização

Aqui está uma classe de exemplo que contém propriedades de tipo de coleção e um tipo definido pelo usuário:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> "POCO" significa [objeto CLR antigo](https://en.wikipedia.org/wiki/Plain_old_CLR_object). Um POCO é um tipo .NET que não depende de nenhum tipo específico de estrutura, por exemplo, por meio de herança ou atributos.

A saída JSON da serialização de uma instância do tipo anterior é semelhante ao exemplo a seguir. A saída JSON é reduzidos (espaço em branco, recuo e caracteres de nova linha são removidos) por padrão:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

O exemplo a seguir mostra o mesmo JSON, mas formatado (ou seja, muito impresso com espaço em branco e recuo):

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

## <a name="serialize-to-utf-8"></a>Serializar para UTF-8

Para serializar para UTF-8, chame o <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> método:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

Uma <xref:System.Text.Json.JsonSerializer.Serialize%2A> sobrecarga que usa um <xref:System.Text.Json.Utf8JsonWriter> também está disponível.

A serialização para UTF-8 é de cerca de 5-10% mais rápida do que usar os métodos baseados em cadeia de caracteres. A diferença é porque os bytes (como UTF-8) não precisam ser convertidos em cadeias de caracteres (UTF-16).

## <a name="serialization-behavior"></a>Comportamento de serialização

::: zone pivot="dotnet-5-0"

* Por padrão, todas as propriedades públicas são serializadas. Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).
* O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* Por padrão, o JSON é reduzidos. Você pode [muito imprimir o JSON](#serialize-to-formatted-json).
* Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET. Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).
* Por padrão, referências circulares são detectadas e exceções geradas. Você pode [preservar referências e manipular referências circulares](system-text-json-preserve-references.md).
* Por padrão, os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados. Você pode [incluir campos](#include-fields).

Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes. Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Por padrão, todas as propriedades públicas são serializadas. Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).
* O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* Por padrão, o JSON é reduzidos. Você pode [muito imprimir o JSON](#serialize-to-formatted-json).
* Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET. Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).
* Referências circulares são detectadas e exceções geradas.
* Os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados.
::: zone-end

Os tipos com suporte incluem:
::: zone pivot="dotnet-5-0"

* Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.
* [Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.
* Matrizes unidimensionais e denteadas ( `T[][]` ).
* Coleções e dicionários dos namespaces a seguir.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.
* [Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.
* Matrizes unidimensionais e denteadas ( `ArrayName[][]` ).
* `Dictionary<string,TValue>` onde `TValue` é `object` , `JsonElement` , ou um poco.
* Coleções dos namespaces a seguir.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para lidar com tipos adicionais ou para fornecer funcionalidade que não é suportada pelos conversores internos.

## <a name="how-to-read-json-as-net-objects-deserialize"></a>Como ler JSON como objetos .NET (desserializar)

Para desserializar de uma cadeia de caracteres ou de um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> método.

O exemplo a seguir lê JSON de uma cadeia de caracteres e cria uma instância da `WeatherForecastWithPOCOs` classe mostrada anteriormente para o [exemplo de serialização](#serialization-example):

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

Para desserializar de um arquivo usando código síncrono, leia o arquivo em uma cadeia de caracteres, conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

Para desserializar de um arquivo usando código assíncrono, chame o <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> método:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a>Desserializar de UTF-8

Para desserializar do UTF-8, chame uma <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> sobrecarga que usa um `ReadOnlySpan<byte>` ou um `Utf8JsonReader` , conforme mostrado nos exemplos a seguir. Os exemplos pressupõem que o JSON esteja em uma matriz de bytes chamada jsonUtf8Bytes.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a>Comportamento de desserialização

Os seguintes comportamentos se aplicam ao desserializar JSON:

::: zone pivot="dotnet-5-0"

* Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas. Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md).
* Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.
* Os construtores não públicos são ignorados pelo serializador.
* Há suporte para desserialização para objetos imutáveis ou propriedades somente leitura. Consulte [tipos e registros imutáveis](system-text-json-immutability.md).
* Por padrão, há suporte para enums como números. Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).
* Por padrão, os campos são ignorados. Você pode [incluir campos](#include-fields).
* Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw. Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).
* A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.

Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes. Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

::: zone pivot="dotnet-core-3-1"

* Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas. Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md). ASP.NET Core aplicativos [especificam a diferenciação de maiúsculas e minúsculas por padrão](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
* Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.
* Um construtor sem parâmetros, que pode ser público, interno ou privado, é usado para desserialização.
* A desserialização para objetos imutáveis ou propriedades somente leitura não tem suporte.
* Por padrão, há suporte para enums como números. Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).
* Não há suporte para campos.
* Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw. Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).
* A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.

Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes. Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).
::: zone-end

Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para fornecer funcionalidade que não é suportada pelos conversores internos.

## <a name="serialize-to-formatted-json"></a>Serializar para JSON formatado

Para imprimir a saída JSON com muita impressão, defina <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` :

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

Aqui está um tipo de exemplo a ser serializado e a saída JSON bem impressa:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Se você usar `JsonSerializerOptions` repetidamente com as mesmas opções, não crie uma nova `JsonSerializerOptions` instância toda vez que usá-la. Reutilize a mesma instância para cada chamada. Para obter mais informações, consulte [reutilizar instâncias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).

## <a name="include-fields"></a>Incluir campos

::: zone pivot="dotnet-5-0"
Use a <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> configuração global ou o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos ao serializar ou desserializar, conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

Para ignorar campos somente leitura, use a <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> configuração global.
::: zone-end

::: zone pivot="dotnet-core-3-1"
Não há suporte para campos no System.Text.Json no .NET Core 3,1. [Conversores personalizados](system-text-json-converters-how-to.md) podem fornecer essa funcionalidade.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>Métodos de extensão HttpClient e HttpContent

::: zone pivot="dotnet-5-0"

A serialização e a desserialização de cargas JSON da rede são operações comuns. Os métodos de extensão em [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) e [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permitem que você execute essas operações em uma única linha de código. Esses métodos de extensão usam [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).

O exemplo a seguir ilustra o uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> e <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> :

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

Também há métodos de extensão para System.Text.Json em [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).
::: zone-end

::: zone pivot="dotnet-core-3-1"
Métodos de extensão em `HttpClient` e `HttpContent` não estão disponíveis no System.Text.Json no .NET Core 3,1.
::: zone-end

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Como gravar conversores personalizados](system-text-json-converters-how-to.md)
* [Como migrar do Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Suporte a DateTime e DateTimeOffset em System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
