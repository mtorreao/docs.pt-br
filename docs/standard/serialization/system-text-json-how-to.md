---
title: Como serializar e desserializar JSON usando C#-.NET
description: Saiba como usar o System.Text.Json namespace para serializar e desserializar do JSON no .net. Inclui o código de exemplo.
ms.date: 12/02/2020
ms.custom: contperf-fy21q2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 46203aa1b4daa4281c7c26191f7df947967fa1c0
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513257"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="43db2-104">Como serializar e desserializar (empacotar e desempacotar) JSON no .NET</span><span class="sxs-lookup"><span data-stu-id="43db2-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="43db2-105">Este artigo mostra como usar o <xref:System.Text.Json?displayProperty=fullName> namespace para serializar e desserializar de JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="43db2-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="43db2-106">Se você estiver portando um código existente do `Newtonsoft.Json` , consulte [como migrar `System.Text.Json` para o ](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="43db2-107">As direções e o código de exemplo usam a biblioteca diretamente, não por meio de uma estrutura como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="43db2-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="43db2-108">A maior parte do código de exemplo de serialização define <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` "muito impresso" o JSON (com recuo e espaço em branco para legibilidade humana).</span><span class="sxs-lookup"><span data-stu-id="43db2-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="43db2-109">Para uso em produção, você normalmente aceitaria o valor padrão de `false` para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="43db2-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="43db2-110">Os exemplos de código referem-se à seguinte classe e variantes dela:</span><span class="sxs-lookup"><span data-stu-id="43db2-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a><span data-ttu-id="43db2-111">Namespaces</span><span class="sxs-lookup"><span data-stu-id="43db2-111">Namespaces</span></span>

<span data-ttu-id="43db2-112">O <xref:System.Text.Json> namespace contém todos os pontos de entrada e os tipos principais.</span><span class="sxs-lookup"><span data-stu-id="43db2-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="43db2-113">O <xref:System.Text.Json.Serialization> namespace contém atributos e APIs para cenários avançados e personalização específicas para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="43db2-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="43db2-114">Os exemplos de código mostrados neste artigo exigem `using` diretivas para um ou ambos os namespaces:</span><span class="sxs-lookup"><span data-stu-id="43db2-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="43db2-115"><xref:System.Runtime.Serialization>Não há suporte para atributos do namespace no `System.Text.Json` .</span><span class="sxs-lookup"><span data-stu-id="43db2-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="43db2-116">Como escrever objetos .NET como JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="43db2-116">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="43db2-117">Para gravar JSON em uma cadeia de caracteres ou em um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="43db2-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="43db2-118">O exemplo a seguir cria JSON como uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="43db2-118">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="43db2-119">O exemplo a seguir usa código síncrono para criar um arquivo JSON:</span><span class="sxs-lookup"><span data-stu-id="43db2-119">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="43db2-120">O exemplo a seguir usa código assíncrono para criar um arquivo JSON:</span><span class="sxs-lookup"><span data-stu-id="43db2-120">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="43db2-121">Os exemplos anteriores usam a inferência de tipos para o tipo que está sendo serializado.</span><span class="sxs-lookup"><span data-stu-id="43db2-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="43db2-122">Uma sobrecarga de `Serialize()` usa um parâmetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="43db2-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="43db2-123">Exemplo de serialização</span><span class="sxs-lookup"><span data-stu-id="43db2-123">Serialization example</span></span>

<span data-ttu-id="43db2-124">Aqui está uma classe de exemplo que contém propriedades de tipo de coleção e um tipo definido pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="43db2-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="43db2-125">"POCO" significa [objeto CLR antigo](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="43db2-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="43db2-126">Um POCO é um tipo .NET que não depende de nenhum tipo específico de estrutura, por exemplo, por meio de herança ou atributos.</span><span class="sxs-lookup"><span data-stu-id="43db2-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="43db2-127">A saída JSON da serialização de uma instância do tipo anterior é semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="43db2-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="43db2-128">A saída JSON é reduzidos (espaço em branco, recuo e caracteres de nova linha são removidos) por padrão:</span><span class="sxs-lookup"><span data-stu-id="43db2-128">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="43db2-129">O exemplo a seguir mostra o mesmo JSON, mas formatado (ou seja, muito impresso com espaço em branco e recuo):</span><span class="sxs-lookup"><span data-stu-id="43db2-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

## <a name="serialize-to-utf-8"></a><span data-ttu-id="43db2-130">Serializar para UTF-8</span><span class="sxs-lookup"><span data-stu-id="43db2-130">Serialize to UTF-8</span></span>

<span data-ttu-id="43db2-131">Para serializar para UTF-8, chame o <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> método:</span><span class="sxs-lookup"><span data-stu-id="43db2-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="43db2-132">Uma <xref:System.Text.Json.JsonSerializer.Serialize%2A> sobrecarga que usa um <xref:System.Text.Json.Utf8JsonWriter> também está disponível.</span><span class="sxs-lookup"><span data-stu-id="43db2-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="43db2-133">A serialização para UTF-8 é de cerca de 5-10% mais rápida do que usar os métodos baseados em cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="43db2-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="43db2-134">A diferença é porque os bytes (como UTF-8) não precisam ser convertidos em cadeias de caracteres (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="43db2-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="43db2-135">Comportamento de serialização</span><span class="sxs-lookup"><span data-stu-id="43db2-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="43db2-136">Por padrão, todas as propriedades públicas são serializadas.</span><span class="sxs-lookup"><span data-stu-id="43db2-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="43db2-137">Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-137">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="43db2-138">O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="43db2-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="43db2-139">Por padrão, o JSON é reduzidos.</span><span class="sxs-lookup"><span data-stu-id="43db2-139">By default, JSON is minified.</span></span> <span data-ttu-id="43db2-140">Você pode [muito imprimir o JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="43db2-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="43db2-141">Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET.</span><span class="sxs-lookup"><span data-stu-id="43db2-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="43db2-142">Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-142">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="43db2-143">Por padrão, referências circulares são detectadas e exceções geradas.</span><span class="sxs-lookup"><span data-stu-id="43db2-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="43db2-144">Você pode [preservar referências e manipular referências circulares](system-text-json-preserve-references.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-144">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="43db2-145">Por padrão, os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="43db2-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="43db2-146">Você pode [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="43db2-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="43db2-147">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="43db2-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="43db2-148">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="43db2-148">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="43db2-149">Por padrão, todas as propriedades públicas são serializadas.</span><span class="sxs-lookup"><span data-stu-id="43db2-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="43db2-150">Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-150">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="43db2-151">O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="43db2-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="43db2-152">Por padrão, o JSON é reduzidos.</span><span class="sxs-lookup"><span data-stu-id="43db2-152">By default, JSON is minified.</span></span> <span data-ttu-id="43db2-153">Você pode [muito imprimir o JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="43db2-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="43db2-154">Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET.</span><span class="sxs-lookup"><span data-stu-id="43db2-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="43db2-155">Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-155">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="43db2-156">Referências circulares são detectadas e exceções geradas.</span><span class="sxs-lookup"><span data-stu-id="43db2-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="43db2-157">Os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="43db2-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="43db2-158">Os tipos com suporte incluem:</span><span class="sxs-lookup"><span data-stu-id="43db2-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="43db2-159">Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.</span><span class="sxs-lookup"><span data-stu-id="43db2-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="43db2-160">[Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="43db2-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="43db2-161">Matrizes unidimensionais e denteadas ( `T[][]` ).</span><span class="sxs-lookup"><span data-stu-id="43db2-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="43db2-162">Coleções e dicionários dos namespaces a seguir.</span><span class="sxs-lookup"><span data-stu-id="43db2-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="43db2-163">Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.</span><span class="sxs-lookup"><span data-stu-id="43db2-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="43db2-164">[Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="43db2-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="43db2-165">Matrizes unidimensionais e denteadas ( `ArrayName[][]` ).</span><span class="sxs-lookup"><span data-stu-id="43db2-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="43db2-166">`Dictionary<string,TValue>` onde `TValue` é `object` , `JsonElement` , ou um poco.</span><span class="sxs-lookup"><span data-stu-id="43db2-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="43db2-167">Coleções dos namespaces a seguir.</span><span class="sxs-lookup"><span data-stu-id="43db2-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="43db2-168">Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para lidar com tipos adicionais ou para fornecer funcionalidade que não é suportada pelos conversores internos.</span><span class="sxs-lookup"><span data-stu-id="43db2-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="43db2-169">Como ler JSON como objetos .NET (desserializar)</span><span class="sxs-lookup"><span data-stu-id="43db2-169">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="43db2-170">Para desserializar de uma cadeia de caracteres ou de um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="43db2-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="43db2-171">O exemplo a seguir lê JSON de uma cadeia de caracteres e cria uma instância da `WeatherForecastWithPOCOs` classe mostrada anteriormente para o [exemplo de serialização](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="43db2-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="43db2-172">Para desserializar de um arquivo usando código síncrono, leia o arquivo em uma cadeia de caracteres, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="43db2-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="43db2-173">Para desserializar de um arquivo usando código assíncrono, chame o <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> método:</span><span class="sxs-lookup"><span data-stu-id="43db2-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="43db2-174">Desserializar de UTF-8</span><span class="sxs-lookup"><span data-stu-id="43db2-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="43db2-175">Para desserializar do UTF-8, chame uma <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> sobrecarga que usa um `ReadOnlySpan<byte>` ou um `Utf8JsonReader` , conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="43db2-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="43db2-176">Os exemplos pressupõem que o JSON esteja em uma matriz de bytes chamada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="43db2-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="43db2-177">Comportamento de desserialização</span><span class="sxs-lookup"><span data-stu-id="43db2-177">Deserialization behavior</span></span>

<span data-ttu-id="43db2-178">Os seguintes comportamentos se aplicam ao desserializar JSON:</span><span class="sxs-lookup"><span data-stu-id="43db2-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="43db2-179">Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="43db2-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="43db2-180">Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-180">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="43db2-181">Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.</span><span class="sxs-lookup"><span data-stu-id="43db2-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="43db2-182">Os construtores não públicos são ignorados pelo serializador.</span><span class="sxs-lookup"><span data-stu-id="43db2-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="43db2-183">Há suporte para desserialização para objetos imutáveis ou propriedades somente leitura.</span><span class="sxs-lookup"><span data-stu-id="43db2-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="43db2-184">Consulte [tipos e registros imutáveis](system-text-json-immutability.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-184">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="43db2-185">Por padrão, há suporte para enums como números.</span><span class="sxs-lookup"><span data-stu-id="43db2-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="43db2-186">Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="43db2-186">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="43db2-187">Por padrão, os campos são ignorados.</span><span class="sxs-lookup"><span data-stu-id="43db2-187">By default, fields are ignored.</span></span> <span data-ttu-id="43db2-188">Você pode [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="43db2-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="43db2-189">Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw.</span><span class="sxs-lookup"><span data-stu-id="43db2-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="43db2-190">Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-190">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="43db2-191">A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.</span><span class="sxs-lookup"><span data-stu-id="43db2-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="43db2-192">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="43db2-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="43db2-193">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="43db2-193">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="43db2-194">Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="43db2-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="43db2-195">Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-195">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="43db2-196">ASP.NET Core aplicativos [especificam a diferenciação de maiúsculas e minúsculas por padrão](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="43db2-196">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="43db2-197">Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.</span><span class="sxs-lookup"><span data-stu-id="43db2-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="43db2-198">Um construtor sem parâmetros, que pode ser público, interno ou privado, é usado para desserialização.</span><span class="sxs-lookup"><span data-stu-id="43db2-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="43db2-199">A desserialização para objetos imutáveis ou propriedades somente leitura não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="43db2-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="43db2-200">Por padrão, há suporte para enums como números.</span><span class="sxs-lookup"><span data-stu-id="43db2-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="43db2-201">Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="43db2-201">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="43db2-202">Não há suporte para campos.</span><span class="sxs-lookup"><span data-stu-id="43db2-202">Fields aren't supported.</span></span>
* <span data-ttu-id="43db2-203">Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw.</span><span class="sxs-lookup"><span data-stu-id="43db2-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="43db2-204">Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="43db2-204">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="43db2-205">A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.</span><span class="sxs-lookup"><span data-stu-id="43db2-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="43db2-206">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="43db2-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="43db2-207">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="43db2-207">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="43db2-208">Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para fornecer funcionalidade que não é suportada pelos conversores internos.</span><span class="sxs-lookup"><span data-stu-id="43db2-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="43db2-209">Serializar para JSON formatado</span><span class="sxs-lookup"><span data-stu-id="43db2-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="43db2-210">Para imprimir a saída JSON com muita impressão, defina <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` :</span><span class="sxs-lookup"><span data-stu-id="43db2-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="43db2-211">Aqui está um tipo de exemplo a ser serializado e a saída JSON bem impressa:</span><span class="sxs-lookup"><span data-stu-id="43db2-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="43db2-212">Se você usar `JsonSerializerOptions` repetidamente com as mesmas opções, não crie uma nova `JsonSerializerOptions` instância toda vez que usá-la.</span><span class="sxs-lookup"><span data-stu-id="43db2-212">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="43db2-213">Reutilize a mesma instância para cada chamada.</span><span class="sxs-lookup"><span data-stu-id="43db2-213">Reuse the same instance for every call.</span></span> <span data-ttu-id="43db2-214">Para obter mais informações, consulte [reutilizar instâncias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="43db2-214">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="include-fields"></a><span data-ttu-id="43db2-215">Incluir campos</span><span class="sxs-lookup"><span data-stu-id="43db2-215">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="43db2-216">Use a <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> configuração global ou o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos ao serializar ou desserializar, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="43db2-216">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="43db2-217">Para ignorar campos somente leitura, use a <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> configuração global.</span><span class="sxs-lookup"><span data-stu-id="43db2-217">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="43db2-218">Não há suporte para campos no System.Text.Json no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="43db2-218">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="43db2-219">[Conversores personalizados](system-text-json-converters-how-to.md) podem fornecer essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="43db2-219">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="43db2-220">Métodos de extensão HttpClient e HttpContent</span><span class="sxs-lookup"><span data-stu-id="43db2-220">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="43db2-221">A serialização e a desserialização de cargas JSON da rede são operações comuns.</span><span class="sxs-lookup"><span data-stu-id="43db2-221">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="43db2-222">Os métodos de extensão em [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) e [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permitem que você execute essas operações em uma única linha de código.</span><span class="sxs-lookup"><span data-stu-id="43db2-222">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="43db2-223">Esses métodos de extensão usam [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="43db2-223">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="43db2-224">O exemplo a seguir ilustra o uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> e <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="43db2-224">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="43db2-225">Também há métodos de extensão para System.Text.Json em [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="43db2-225">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="43db2-226">Métodos de extensão em `HttpClient` e `HttpContent` não estão disponíveis no System.Text.Json no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="43db2-226">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="43db2-227">Consulte também</span><span class="sxs-lookup"><span data-stu-id="43db2-227">See also</span></span>

* [<span data-ttu-id="43db2-228">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="43db2-228">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="43db2-229">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="43db2-229">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="43db2-230">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="43db2-230">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="43db2-231">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="43db2-231">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="43db2-232">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="43db2-232">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="43db2-233">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="43db2-233">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="43db2-234">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="43db2-234">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="43db2-235">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="43db2-235">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="43db2-236">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="43db2-236">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="43db2-237">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="43db2-237">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="43db2-238">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="43db2-238">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="43db2-239">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="43db2-239">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="43db2-240">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="43db2-240">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="43db2-241">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="43db2-241">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="43db2-242">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="43db2-242">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="43db2-243">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="43db2-243">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="43db2-244">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="43db2-244">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
