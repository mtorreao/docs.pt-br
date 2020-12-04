---
title: Como personalizar nomes de propriedade e valores com System.Text.Json
description: Saiba como personalizar nomes de propriedade e valores ao serializar com o System.Text.Json no .net.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c754d41071e886bc1efcc3a30e249bf9e554ab5b
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599584"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a><span data-ttu-id="27bb2-103">Como personalizar nomes de propriedade e valores com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="27bb2-103">How to customize property names and values with System.Text.Json</span></span>

<span data-ttu-id="27bb2-104">Por padrão, os nomes de propriedade e as chaves de dicionário são inalterados na saída JSON, incluindo maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="27bb2-104">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="27bb2-105">Os valores de enumeração são representados como números.</span><span class="sxs-lookup"><span data-stu-id="27bb2-105">Enum values are represented as numbers.</span></span> <span data-ttu-id="27bb2-106">Neste artigo, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="27bb2-106">In this article, you'll learn how to:</span></span>

> [!NOTE]
> <span data-ttu-id="27bb2-107">O [padrão da Web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) é o camel case.</span><span class="sxs-lookup"><span data-stu-id="27bb2-107">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is camel case.</span></span>

* [<span data-ttu-id="27bb2-108">Personalizar nomes de propriedade individuais</span><span class="sxs-lookup"><span data-stu-id="27bb2-108">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="27bb2-109">Converter todos os nomes de propriedade em camel case</span><span class="sxs-lookup"><span data-stu-id="27bb2-109">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="27bb2-110">Implementar uma política de nomenclatura de propriedade personalizada</span><span class="sxs-lookup"><span data-stu-id="27bb2-110">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="27bb2-111">Converter chaves de dicionário em camel case</span><span class="sxs-lookup"><span data-stu-id="27bb2-111">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="27bb2-112">Converter enums em cadeias de caracteres e camel case</span><span class="sxs-lookup"><span data-stu-id="27bb2-112">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="27bb2-113">Para outros cenários que exigem tratamento especial de valores e nomes de propriedade JSON, você pode [implementar conversores personalizados](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="27bb2-113">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

## <a name="customize-individual-property-names"></a><span data-ttu-id="27bb2-114">Personalizar nomes de propriedade individuais</span><span class="sxs-lookup"><span data-stu-id="27bb2-114">Customize individual property names</span></span>

<span data-ttu-id="27bb2-115">Para definir o nome de propriedades individuais, use o atributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="27bb2-115">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="27bb2-116">Veja um exemplo de tipo para serializar e o JSON resultante:</span><span class="sxs-lookup"><span data-stu-id="27bb2-116">Here's an example type to serialize and resulting JSON:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="27bb2-117">O nome da propriedade definido por este atributo:</span><span class="sxs-lookup"><span data-stu-id="27bb2-117">The property name set by this attribute:</span></span>

* <span data-ttu-id="27bb2-118">Aplica-se em ambas as direções, para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="27bb2-118">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="27bb2-119">Tem precedência sobre as políticas de nomenclatura de propriedade.</span><span class="sxs-lookup"><span data-stu-id="27bb2-119">Takes precedence over property naming policies.</span></span>

## <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="27bb2-120">Usar o camel case para todos os nomes de propriedade JSON</span><span class="sxs-lookup"><span data-stu-id="27bb2-120">Use camel case for all JSON property names</span></span>

<span data-ttu-id="27bb2-121">Para usar o camel case para todos os nomes de propriedade JSON, defina como <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> `JsonNamingPolicy.CamelCase` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-121">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

<span data-ttu-id="27bb2-122">Aqui está uma classe de exemplo para serializar e a saída JSON:</span><span class="sxs-lookup"><span data-stu-id="27bb2-122">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="27bb2-123">A política de nomenclatura de Propriedade do camel case:</span><span class="sxs-lookup"><span data-stu-id="27bb2-123">The camel case property naming policy:</span></span>

* <span data-ttu-id="27bb2-124">Aplica-se à serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="27bb2-124">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="27bb2-125">É substituído por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="27bb2-125">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="27bb2-126">É por isso que o nome da propriedade JSON `Wind` no exemplo não é camel case.</span><span class="sxs-lookup"><span data-stu-id="27bb2-126">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

## <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="27bb2-127">Usar uma política de nomenclatura de propriedade JSON personalizada</span><span class="sxs-lookup"><span data-stu-id="27bb2-127">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="27bb2-128">Para usar uma política de nomenclatura de propriedade JSON personalizada, crie uma classe derivada de <xref:System.Text.Json.JsonNamingPolicy> e substitua o <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> método, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-128">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

<span data-ttu-id="27bb2-129">Em seguida, defina a <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> propriedade como uma instância da sua classe de política de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="27bb2-129">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

<span data-ttu-id="27bb2-130">Aqui está uma classe de exemplo para serializar e a saída JSON:</span><span class="sxs-lookup"><span data-stu-id="27bb2-130">Here's an example class to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="27bb2-131">A política de nomenclatura de propriedade JSON:</span><span class="sxs-lookup"><span data-stu-id="27bb2-131">The JSON property naming policy:</span></span>

* <span data-ttu-id="27bb2-132">Aplica-se à serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="27bb2-132">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="27bb2-133">É substituído por `[JsonPropertyName]` atributos.</span><span class="sxs-lookup"><span data-stu-id="27bb2-133">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="27bb2-134">É por isso que o nome da propriedade JSON `Wind` no exemplo não é maiúscula.</span><span class="sxs-lookup"><span data-stu-id="27bb2-134">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

## <a name="camel-case-dictionary-keys"></a><span data-ttu-id="27bb2-135">Chaves de dicionário do camel case</span><span class="sxs-lookup"><span data-stu-id="27bb2-135">Camel case dictionary keys</span></span>

<span data-ttu-id="27bb2-136">Se uma propriedade de um objeto a ser serializado for do tipo `Dictionary<string,TValue>` , as `string` chaves poderão ser convertidas em camel case.</span><span class="sxs-lookup"><span data-stu-id="27bb2-136">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="27bb2-137">Para fazer isso, defina <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> como `JsonNamingPolicy.CamelCase` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-137">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

<span data-ttu-id="27bb2-138">Serializar um objeto com um dicionário chamado `TemperatureRanges` que tem pares chave-valor `"ColdMinTemp", 20` e `"HotMinTemp", 40` resultaria em uma saída JSON como o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-138">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="27bb2-139">A política de nomenclatura do camel case para chaves de dicionário se aplica somente à serialização.</span><span class="sxs-lookup"><span data-stu-id="27bb2-139">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="27bb2-140">Se você desserializar um dicionário, as chaves corresponderão ao arquivo JSON mesmo que você especifique `JsonNamingPolicy.CamelCase` para o `DictionaryKeyPolicy` .</span><span class="sxs-lookup"><span data-stu-id="27bb2-140">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

## <a name="enums-as-strings"></a><span data-ttu-id="27bb2-141">Enumerações como cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="27bb2-141">Enums as strings</span></span>

<span data-ttu-id="27bb2-142">Por padrão, as enumerações são serializadas como números.</span><span class="sxs-lookup"><span data-stu-id="27bb2-142">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="27bb2-143">Para serializar nomes de enumeração como cadeias de caracteres, use o <xref:System.Text.Json.Serialization.JsonStringEnumConverter> .</span><span class="sxs-lookup"><span data-stu-id="27bb2-143">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="27bb2-144">Por exemplo, suponha que você precise serializar a seguinte classe que tem uma enumeração:</span><span class="sxs-lookup"><span data-stu-id="27bb2-144">For example, suppose you need to serialize the following class that has an enum:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

<span data-ttu-id="27bb2-145">Se o resumo for `Hot` , por padrão, o JSON serializado terá o valor numérico 3:</span><span class="sxs-lookup"><span data-stu-id="27bb2-145">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="27bb2-146">O código de exemplo a seguir serializa os nomes de enumeração em vez dos valores numéricos e converte os nomes em camel case:</span><span class="sxs-lookup"><span data-stu-id="27bb2-146">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

<span data-ttu-id="27bb2-147">O JSON resultante é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-147">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="27bb2-148">Os nomes de cadeias de caracteres de enumeração também podem ser desserializados, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27bb2-148">Enum string names can be deserialized as well, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a><span data-ttu-id="27bb2-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="27bb2-149">See also</span></span>

* [<span data-ttu-id="27bb2-150">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="27bb2-150">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="27bb2-151">Criar uma instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="27bb2-151">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="27bb2-152">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="27bb2-152">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="27bb2-153">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="27bb2-153">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="27bb2-154">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="27bb2-154">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="27bb2-155">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="27bb2-155">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="27bb2-156">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="27bb2-156">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="27bb2-157">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="27bb2-157">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="27bb2-158">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="27bb2-158">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="27bb2-159">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="27bb2-159">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
