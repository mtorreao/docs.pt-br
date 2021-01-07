---
title: Como serializar e desserializar JSON usando C#-.NET
description: Saiba como usar o System.Text.Json namespace para serializar e desserializar do JSON no .net. Inclui o código de exemplo.
ms.date: 01/04/2021
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
ms.openlocfilehash: 541ac80ce40b0410167b14f96e36b354d19411db
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970896"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="5c54f-104">Como serializar e desserializar (empacotar e desempacotar) JSON no .NET</span><span class="sxs-lookup"><span data-stu-id="5c54f-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="5c54f-105">Este artigo mostra como usar o <xref:System.Text.Json?displayProperty=fullName> namespace para serializar e desserializar de JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="5c54f-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="5c54f-106">Se você estiver portando um código existente do `Newtonsoft.Json` , consulte [como migrar `System.Text.Json` para o ](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="5c54f-107">As direções e o código de exemplo usam a biblioteca diretamente, não por meio de uma estrutura como [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="5c54f-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="5c54f-108">A maior parte do código de exemplo de serialização define <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` "muito impresso" o JSON (com recuo e espaço em branco para legibilidade humana).</span><span class="sxs-lookup"><span data-stu-id="5c54f-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="5c54f-109">Para uso em produção, você normalmente aceitaria o valor padrão de `false` para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="5c54f-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="5c54f-110">Os exemplos de código referem-se à seguinte classe e variantes dela:</span><span class="sxs-lookup"><span data-stu-id="5c54f-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

> [!NOTE]
> <span data-ttu-id="5c54f-111">System.Text.Json usa [structs de referência](../../csharp/language-reference/builtin-types/struct.md#ref-struct), que não têm suporte do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c54f-111">System.Text.Json uses [ref structs](../../csharp/language-reference/builtin-types/struct.md#ref-struct), which are not supported by Visual Basic.</span></span> <span data-ttu-id="5c54f-112">Se você tentar usar System.Text.Json APIs com Visual Basic, obterá erros de compilação BC40000.</span><span class="sxs-lookup"><span data-stu-id="5c54f-112">If you try to use System.Text.Json APIs with Visual Basic, you get BC40000 compile errors.</span></span> <span data-ttu-id="5c54f-113">A mensagem de erro indica que o problema é uma API obsoleta, mas o problema real é a falta de `ref struct` suporte no compilador.</span><span class="sxs-lookup"><span data-stu-id="5c54f-113">The error message indicates that the problem is an obsolete API, but the actual issue is lack of `ref struct` support in the compiler.</span></span>

## <a name="namespaces"></a><span data-ttu-id="5c54f-114">Namespaces</span><span class="sxs-lookup"><span data-stu-id="5c54f-114">Namespaces</span></span>

<span data-ttu-id="5c54f-115">O <xref:System.Text.Json> namespace contém todos os pontos de entrada e os tipos principais.</span><span class="sxs-lookup"><span data-stu-id="5c54f-115">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="5c54f-116">O <xref:System.Text.Json.Serialization> namespace contém atributos e APIs para cenários avançados e personalização específicas para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="5c54f-116">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="5c54f-117">Os exemplos de código mostrados neste artigo exigem `using` diretivas para um ou ambos os namespaces:</span><span class="sxs-lookup"><span data-stu-id="5c54f-117">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="5c54f-118"><xref:System.Runtime.Serialization>Não há suporte para atributos do namespace no `System.Text.Json` .</span><span class="sxs-lookup"><span data-stu-id="5c54f-118">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="5c54f-119">Como escrever objetos .NET como JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="5c54f-119">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="5c54f-120">Para gravar JSON em uma cadeia de caracteres ou em um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="5c54f-120">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="5c54f-121">O exemplo a seguir cria JSON como uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="5c54f-121">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="5c54f-122">O exemplo a seguir usa código síncrono para criar um arquivo JSON:</span><span class="sxs-lookup"><span data-stu-id="5c54f-122">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="5c54f-123">O exemplo a seguir usa código assíncrono para criar um arquivo JSON:</span><span class="sxs-lookup"><span data-stu-id="5c54f-123">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="5c54f-124">Os exemplos anteriores usam a inferência de tipos para o tipo que está sendo serializado.</span><span class="sxs-lookup"><span data-stu-id="5c54f-124">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="5c54f-125">Uma sobrecarga de `Serialize()` usa um parâmetro de tipo genérico:</span><span class="sxs-lookup"><span data-stu-id="5c54f-125">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="5c54f-126">Exemplo de serialização</span><span class="sxs-lookup"><span data-stu-id="5c54f-126">Serialization example</span></span>

<span data-ttu-id="5c54f-127">Aqui está uma classe de exemplo que contém propriedades de tipo de coleção e um tipo definido pelo usuário:</span><span class="sxs-lookup"><span data-stu-id="5c54f-127">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="5c54f-128">"POCO" significa [objeto CLR antigo](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span><span class="sxs-lookup"><span data-stu-id="5c54f-128">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="5c54f-129">Um POCO é um tipo .NET que não depende de nenhum tipo específico de estrutura, por exemplo, por meio de herança ou atributos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-129">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="5c54f-130">A saída JSON da serialização de uma instância do tipo anterior é semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c54f-130">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="5c54f-131">A saída JSON é reduzidos (espaço em branco, recuo e caracteres de nova linha são removidos) por padrão:</span><span class="sxs-lookup"><span data-stu-id="5c54f-131">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="5c54f-132">O exemplo a seguir mostra o mesmo JSON, mas formatado (ou seja, muito impresso com espaço em branco e recuo):</span><span class="sxs-lookup"><span data-stu-id="5c54f-132">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

## <a name="serialize-to-utf-8"></a><span data-ttu-id="5c54f-133">Serializar para UTF-8</span><span class="sxs-lookup"><span data-stu-id="5c54f-133">Serialize to UTF-8</span></span>

<span data-ttu-id="5c54f-134">Para serializar para UTF-8, chame o <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> método:</span><span class="sxs-lookup"><span data-stu-id="5c54f-134">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="5c54f-135">Uma <xref:System.Text.Json.JsonSerializer.Serialize%2A> sobrecarga que usa um <xref:System.Text.Json.Utf8JsonWriter> também está disponível.</span><span class="sxs-lookup"><span data-stu-id="5c54f-135">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="5c54f-136">A serialização para UTF-8 é de cerca de 5-10% mais rápida do que usar os métodos baseados em cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5c54f-136">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="5c54f-137">A diferença é porque os bytes (como UTF-8) não precisam ser convertidos em cadeias de caracteres (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="5c54f-137">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="5c54f-138">Comportamento de serialização</span><span class="sxs-lookup"><span data-stu-id="5c54f-138">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="5c54f-139">Por padrão, todas as propriedades públicas são serializadas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-139">By default, all public properties are serialized.</span></span> <span data-ttu-id="5c54f-140">Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-140">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="5c54f-141">O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="5c54f-141">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="5c54f-142">Por padrão, o JSON é reduzidos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-142">By default, JSON is minified.</span></span> <span data-ttu-id="5c54f-143">Você pode [muito imprimir o JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="5c54f-143">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="5c54f-144">Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET.</span><span class="sxs-lookup"><span data-stu-id="5c54f-144">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="5c54f-145">Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-145">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="5c54f-146">Por padrão, referências circulares são detectadas e exceções geradas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-146">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="5c54f-147">Você pode [preservar referências e manipular referências circulares](system-text-json-preserve-references.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-147">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="5c54f-148">Por padrão, os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5c54f-148">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="5c54f-149">Você pode [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="5c54f-149">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="5c54f-150">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="5c54f-150">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="5c54f-151">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-151">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="5c54f-152">Por padrão, todas as propriedades públicas são serializadas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-152">By default, all public properties are serialized.</span></span> <span data-ttu-id="5c54f-153">Você pode [especificar propriedades a serem ignoradas](system-text-json-ignore-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-153">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="5c54f-154">O [codificador padrão](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapa caracteres não ASCII, caracteres sensíveis a HTML dentro do intervalo ASCII e caracteres que devem ser ignorados de acordo com [a especificação JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="5c54f-154">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="5c54f-155">Por padrão, o JSON é reduzidos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-155">By default, JSON is minified.</span></span> <span data-ttu-id="5c54f-156">Você pode [muito imprimir o JSON](#serialize-to-formatted-json).</span><span class="sxs-lookup"><span data-stu-id="5c54f-156">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="5c54f-157">Por padrão, a capitalização de nomes JSON corresponde aos nomes .NET.</span><span class="sxs-lookup"><span data-stu-id="5c54f-157">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="5c54f-158">Você pode personalizar o uso de [maiúsculas e minúsculas de nomes](system-text-json-customize-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-158">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="5c54f-159">Referências circulares são detectadas e exceções geradas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-159">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="5c54f-160">Os [campos](../../csharp/programming-guide/classes-and-structs/fields.md) são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5c54f-160">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="5c54f-161">Os tipos com suporte incluem:</span><span class="sxs-lookup"><span data-stu-id="5c54f-161">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="5c54f-162">Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.</span><span class="sxs-lookup"><span data-stu-id="5c54f-162">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="5c54f-163">[Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5c54f-163">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="5c54f-164">Matrizes unidimensionais e denteadas ( `T[][]` ).</span><span class="sxs-lookup"><span data-stu-id="5c54f-164">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="5c54f-165">Coleções e dicionários dos namespaces a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c54f-165">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="5c54f-166">Primitivos .NET que mapeiam para primitivos JavaScript, como tipos numéricos, cadeias de caracteres e booliano.</span><span class="sxs-lookup"><span data-stu-id="5c54f-166">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="5c54f-167">[Pocos (objetos CLR antigos)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5c54f-167">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="5c54f-168">Matrizes unidimensionais e denteadas ( `ArrayName[][]` ).</span><span class="sxs-lookup"><span data-stu-id="5c54f-168">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="5c54f-169">`Dictionary<string,TValue>` onde `TValue` é `object` , `JsonElement` , ou um poco.</span><span class="sxs-lookup"><span data-stu-id="5c54f-169">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="5c54f-170">Coleções dos namespaces a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c54f-170">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="5c54f-171">Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para lidar com tipos adicionais ou para fornecer funcionalidade que não é suportada pelos conversores internos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-171">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="5c54f-172">Como ler JSON como objetos .NET (desserializar)</span><span class="sxs-lookup"><span data-stu-id="5c54f-172">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="5c54f-173">Para desserializar de uma cadeia de caracteres ou de um arquivo, chame o <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="5c54f-173">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="5c54f-174">O exemplo a seguir lê JSON de uma cadeia de caracteres e cria uma instância da `WeatherForecastWithPOCOs` classe mostrada anteriormente para o [exemplo de serialização](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="5c54f-174">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="5c54f-175">Para desserializar de um arquivo usando código síncrono, leia o arquivo em uma cadeia de caracteres, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="5c54f-175">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="5c54f-176">Para desserializar de um arquivo usando código assíncrono, chame o <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> método:</span><span class="sxs-lookup"><span data-stu-id="5c54f-176">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

> [!TIP]
> <span data-ttu-id="5c54f-177">Se você tiver o JSON que deseja desserializar e não tiver a classe para desserializá-lo, o Visual Studio 2019 poderá gerar automaticamente a classe de que você precisa:</span><span class="sxs-lookup"><span data-stu-id="5c54f-177">If you have JSON that you want to deserialize, and you don't have the class to deserialize it into, Visual Studio 2019 can automatically generate the class you need:</span></span>
>
> 1. <span data-ttu-id="5c54f-178">Copie o JSON que você precisa para desserializar.</span><span class="sxs-lookup"><span data-stu-id="5c54f-178">Copy the JSON that you need to deserialize.</span></span>
> 1. <span data-ttu-id="5c54f-179">Crie um arquivo de classe e exclua o código do modelo.</span><span class="sxs-lookup"><span data-stu-id="5c54f-179">Create a class file and delete the template code.</span></span>
> 1. <span data-ttu-id="5c54f-180">Escolha **Editar**  >  **colar**  >  **JSON especial como classes**.</span><span class="sxs-lookup"><span data-stu-id="5c54f-180">Choose **Edit** > **Paste Special** > **Paste JSON as Classes**.</span></span>
>
> <span data-ttu-id="5c54f-181">O resultado é uma classe que você pode usar para o destino de desserialização.</span><span class="sxs-lookup"><span data-stu-id="5c54f-181">The result is a class that you can use for your deserialization target.</span></span>

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="5c54f-182">Desserializar de UTF-8</span><span class="sxs-lookup"><span data-stu-id="5c54f-182">Deserialize from UTF-8</span></span>

<span data-ttu-id="5c54f-183">Para desserializar do UTF-8, chame uma <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> sobrecarga que usa um `ReadOnlySpan<byte>` ou um `Utf8JsonReader` , conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c54f-183">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="5c54f-184">Os exemplos pressupõem que o JSON esteja em uma matriz de bytes chamada jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="5c54f-184">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="5c54f-185">Comportamento de desserialização</span><span class="sxs-lookup"><span data-stu-id="5c54f-185">Deserialization behavior</span></span>

<span data-ttu-id="5c54f-186">Os seguintes comportamentos se aplicam ao desserializar JSON:</span><span class="sxs-lookup"><span data-stu-id="5c54f-186">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="5c54f-187">Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-187">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="5c54f-188">Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-188">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="5c54f-189">Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.</span><span class="sxs-lookup"><span data-stu-id="5c54f-189">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="5c54f-190">Os construtores não públicos são ignorados pelo serializador.</span><span class="sxs-lookup"><span data-stu-id="5c54f-190">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="5c54f-191">Há suporte para desserialização para objetos imutáveis ou propriedades somente leitura.</span><span class="sxs-lookup"><span data-stu-id="5c54f-191">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="5c54f-192">Consulte [tipos e registros imutáveis](system-text-json-immutability.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-192">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="5c54f-193">Por padrão, há suporte para enums como números.</span><span class="sxs-lookup"><span data-stu-id="5c54f-193">By default, enums are supported as numbers.</span></span> <span data-ttu-id="5c54f-194">Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="5c54f-194">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="5c54f-195">Por padrão, os campos são ignorados.</span><span class="sxs-lookup"><span data-stu-id="5c54f-195">By default, fields are ignored.</span></span> <span data-ttu-id="5c54f-196">Você pode [incluir campos](#include-fields).</span><span class="sxs-lookup"><span data-stu-id="5c54f-196">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="5c54f-197">Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw.</span><span class="sxs-lookup"><span data-stu-id="5c54f-197">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="5c54f-198">Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-198">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="5c54f-199">A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.</span><span class="sxs-lookup"><span data-stu-id="5c54f-199">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="5c54f-200">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="5c54f-200">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="5c54f-201">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-201">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="5c54f-202">Por padrão, a correspondência de nome de propriedade diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5c54f-202">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="5c54f-203">Você pode [especificar a não diferenciação de maiúsculas e minúsculas](system-text-json-character-casing.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-203">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="5c54f-204">ASP.NET Core aplicativos [especificam a diferenciação de maiúsculas e minúsculas por padrão](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-204">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="5c54f-205">Se o JSON contiver um valor para uma propriedade somente leitura, o valor será ignorado e nenhuma exceção será lançada.</span><span class="sxs-lookup"><span data-stu-id="5c54f-205">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="5c54f-206">Um construtor sem parâmetros, que pode ser público, interno ou privado, é usado para desserialização.</span><span class="sxs-lookup"><span data-stu-id="5c54f-206">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="5c54f-207">A desserialização para objetos imutáveis ou propriedades somente leitura não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="5c54f-207">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="5c54f-208">Por padrão, há suporte para enums como números.</span><span class="sxs-lookup"><span data-stu-id="5c54f-208">By default, enums are supported as numbers.</span></span> <span data-ttu-id="5c54f-209">Você pode [serializar nomes de enumeração como cadeias de caracteres](system-text-json-customize-properties.md#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="5c54f-209">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="5c54f-210">Não há suporte para campos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-210">Fields aren't supported.</span></span>
* <span data-ttu-id="5c54f-211">Por padrão, comentários ou vírgulas à direita nas exceções do JSON throw.</span><span class="sxs-lookup"><span data-stu-id="5c54f-211">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="5c54f-212">Você pode [permitir comentários e vírgulas à direita](system-text-json-invalid-json.md).</span><span class="sxs-lookup"><span data-stu-id="5c54f-212">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="5c54f-213">A [profundidade máxima padrão](xref:System.Text.Json.JsonReaderOptions.MaxDepth) é 64.</span><span class="sxs-lookup"><span data-stu-id="5c54f-213">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="5c54f-214">Quando você usa System.Text.Json indiretamente em um aplicativo ASP.NET Core, alguns comportamentos padrão são diferentes.</span><span class="sxs-lookup"><span data-stu-id="5c54f-214">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="5c54f-215">Para obter mais informações, consulte [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-215">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="5c54f-216">Você pode [implementar conversores personalizados](system-text-json-converters-how-to.md) para fornecer funcionalidade que não é suportada pelos conversores internos.</span><span class="sxs-lookup"><span data-stu-id="5c54f-216">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="5c54f-217">Serializar para JSON formatado</span><span class="sxs-lookup"><span data-stu-id="5c54f-217">Serialize to formatted JSON</span></span>

<span data-ttu-id="5c54f-218">Para imprimir a saída JSON com muita impressão, defina <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> como `true` :</span><span class="sxs-lookup"><span data-stu-id="5c54f-218">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="5c54f-219">Aqui está um tipo de exemplo a ser serializado e a saída JSON bem impressa:</span><span class="sxs-lookup"><span data-stu-id="5c54f-219">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="5c54f-220">Se você usar `JsonSerializerOptions` repetidamente com as mesmas opções, não crie uma nova `JsonSerializerOptions` instância toda vez que usá-la.</span><span class="sxs-lookup"><span data-stu-id="5c54f-220">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="5c54f-221">Reutilize a mesma instância para cada chamada.</span><span class="sxs-lookup"><span data-stu-id="5c54f-221">Reuse the same instance for every call.</span></span> <span data-ttu-id="5c54f-222">Para obter mais informações, consulte [reutilizar instâncias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="5c54f-222">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="include-fields"></a><span data-ttu-id="5c54f-223">Incluir campos</span><span class="sxs-lookup"><span data-stu-id="5c54f-223">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="5c54f-224">Use a <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> configuração global ou o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) para incluir campos ao serializar ou desserializar, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="5c54f-224">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="5c54f-225">Para ignorar campos somente leitura, use a <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> configuração global.</span><span class="sxs-lookup"><span data-stu-id="5c54f-225">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="5c54f-226">Não há suporte para campos no System.Text.Json no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="5c54f-226">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="5c54f-227">[Conversores personalizados](system-text-json-converters-how-to.md) podem fornecer essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="5c54f-227">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="5c54f-228">Métodos de extensão HttpClient e HttpContent</span><span class="sxs-lookup"><span data-stu-id="5c54f-228">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="5c54f-229">A serialização e a desserialização de cargas JSON da rede são operações comuns.</span><span class="sxs-lookup"><span data-stu-id="5c54f-229">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="5c54f-230">Os métodos de extensão em [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) e [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) permitem que você execute essas operações em uma única linha de código.</span><span class="sxs-lookup"><span data-stu-id="5c54f-230">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="5c54f-231">Esses métodos de extensão usam [padrões da Web para JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-231">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="5c54f-232">O exemplo a seguir ilustra o uso de <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> e <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="5c54f-232">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="5c54f-233">Também há métodos de extensão para System.Text.Json em [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span><span class="sxs-lookup"><span data-stu-id="5c54f-233">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="5c54f-234">Métodos de extensão em `HttpClient` e `HttpContent` não estão disponíveis no System.Text.Json no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="5c54f-234">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="5c54f-235">Veja também</span><span class="sxs-lookup"><span data-stu-id="5c54f-235">See also</span></span>

* [<span data-ttu-id="5c54f-236">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="5c54f-236">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="5c54f-237">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="5c54f-237">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="5c54f-238">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="5c54f-238">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="5c54f-239">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="5c54f-239">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="5c54f-240">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="5c54f-240">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="5c54f-241">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="5c54f-241">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="5c54f-242">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="5c54f-242">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="5c54f-243">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="5c54f-243">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="5c54f-244">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="5c54f-244">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="5c54f-245">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="5c54f-245">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="5c54f-246">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="5c54f-246">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="5c54f-247">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="5c54f-247">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="5c54f-248">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="5c54f-248">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="5c54f-249">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="5c54f-249">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="5c54f-250">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5c54f-250">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="5c54f-251">Tipos de coleção com suporte no System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="5c54f-251">Supported collection types in System.Text.Json</span></span>](system-text-json-supported-collection-types.md)
* <span data-ttu-id="5c54f-252">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="5c54f-252">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="5c54f-253">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="5c54f-253">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
