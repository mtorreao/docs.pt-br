---
title: Como ignorar Propriedades com System.Text.Json
description: Saiba como ignorar Propriedades ao serializar com o System.Text.Json no .net.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439885"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a><span data-ttu-id="9763f-103">Como ignorar Propriedades com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="9763f-103">How to ignore properties with System.Text.Json</span></span>

<span data-ttu-id="9763f-104">Ao serializar objetos C# para JavaScript Object Notation (JSON), por padrão, todas as propriedades públicas são serializadas.</span><span class="sxs-lookup"><span data-stu-id="9763f-104">When serializing C# objects to JavaScript Object Notation (JSON), by default, all public properties are serialized.</span></span> <span data-ttu-id="9763f-105">Se não quiser que algumas delas apareçam no JSON resultante, você terá várias opções.</span><span class="sxs-lookup"><span data-stu-id="9763f-105">If you don't want some of them to appear in the resulting JSON, you have several options.</span></span> <span data-ttu-id="9763f-106">Neste artigo, você aprenderá a ignorar Propriedades com base em vários critérios:</span><span class="sxs-lookup"><span data-stu-id="9763f-106">In this article you learn how to ignore properties based on various criteria:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="9763f-107">Propriedades individuais</span><span class="sxs-lookup"><span data-stu-id="9763f-107">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="9763f-108">Todas as propriedades somente leitura</span><span class="sxs-lookup"><span data-stu-id="9763f-108">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="9763f-109">Todas as propriedades de valor nulo</span><span class="sxs-lookup"><span data-stu-id="9763f-109">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="9763f-110">Todas as propriedades de valor padrão</span><span class="sxs-lookup"><span data-stu-id="9763f-110">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="9763f-111">Propriedades individuais</span><span class="sxs-lookup"><span data-stu-id="9763f-111">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="9763f-112">Todas as propriedades somente leitura</span><span class="sxs-lookup"><span data-stu-id="9763f-112">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="9763f-113">Todas as propriedades de valor nulo</span><span class="sxs-lookup"><span data-stu-id="9763f-113">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a><span data-ttu-id="9763f-114">Ignorar propriedades individuais</span><span class="sxs-lookup"><span data-stu-id="9763f-114">Ignore individual properties</span></span>

<span data-ttu-id="9763f-115">Para ignorar as propriedades individuais, use o atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="9763f-115">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="9763f-116">Aqui está um tipo de exemplo para serializar e a saída JSON:</span><span class="sxs-lookup"><span data-stu-id="9763f-116">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9763f-117">Você pode especificar a exclusão condicional definindo a propriedade do atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) `Condition` .</span><span class="sxs-lookup"><span data-stu-id="9763f-117">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="9763f-118">A <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enumeração fornece as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9763f-118">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="9763f-119">`Always` -A propriedade é sempre ignorada.</span><span class="sxs-lookup"><span data-stu-id="9763f-119">`Always` - The property is always ignored.</span></span> <span data-ttu-id="9763f-120">Se não `Condition` for especificado, essa opção será assumida.</span><span class="sxs-lookup"><span data-stu-id="9763f-120">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="9763f-121">`Never` -A propriedade é sempre serializada e desserializada, independentemente das `DefaultIgnoreCondition` `IgnoreReadOnlyProperties` `IgnoreReadOnlyFields` configurações globais, e.</span><span class="sxs-lookup"><span data-stu-id="9763f-121">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="9763f-122">`WhenWritingDefault` -A propriedade será ignorada na serialização se for um tipo de referência `null` , um tipo de valor Anulável `null` ou um tipo de valor `default` .</span><span class="sxs-lookup"><span data-stu-id="9763f-122">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null`, a nullable value type `null`, or a value type `default`.</span></span>
* <span data-ttu-id="9763f-123">`WhenWritingNull` -A propriedade será ignorada na serialização se for um tipo de referência `null` ou um tipo de valor Anulável `null` .</span><span class="sxs-lookup"><span data-stu-id="9763f-123">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`, or a nullable value type `null`.</span></span>

<span data-ttu-id="9763f-124">O exemplo a seguir ilustra o uso da Propriedade do atributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) `Condition` :</span><span class="sxs-lookup"><span data-stu-id="9763f-124">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a><span data-ttu-id="9763f-125">Ignorar todas as propriedades somente leitura</span><span class="sxs-lookup"><span data-stu-id="9763f-125">Ignore all read-only properties</span></span>

<span data-ttu-id="9763f-126">Uma propriedade será somente leitura se ela contiver um getter público, mas não um setter público.</span><span class="sxs-lookup"><span data-stu-id="9763f-126">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="9763f-127">Para ignorar todas as propriedades somente leitura ao serializar, defina <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> como `true` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9763f-127">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

<span data-ttu-id="9763f-128">Aqui está um tipo de exemplo para serializar e a saída JSON:</span><span class="sxs-lookup"><span data-stu-id="9763f-128">Here's an example type to serialize and JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="9763f-129">Essa opção se aplica somente à serialização.</span><span class="sxs-lookup"><span data-stu-id="9763f-129">This option applies only to serialization.</span></span> <span data-ttu-id="9763f-130">Durante a desserialização, as propriedades somente leitura são ignoradas por padrão.</span><span class="sxs-lookup"><span data-stu-id="9763f-130">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9763f-131">Essa opção se aplica somente a propriedades.</span><span class="sxs-lookup"><span data-stu-id="9763f-131">This option applies only to properties.</span></span> <span data-ttu-id="9763f-132">Para ignorar campos somente leitura ao [serializar campos](system-text-json-how-to.md#include-fields), use a <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> configuração global.</span><span class="sxs-lookup"><span data-stu-id="9763f-132">To ignore read-only fields when [serializing fields](system-text-json-how-to.md#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

## <a name="ignore-all-null-value-properties"></a><span data-ttu-id="9763f-133">Ignorar todas as propriedades de valor nulo</span><span class="sxs-lookup"><span data-stu-id="9763f-133">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9763f-134">Para ignorar todas as propriedades de valor nulo, defina a <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> propriedade como <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull> , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9763f-134">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9763f-135">Para ignorar todas as propriedades de valor nulo ao serializar, defina a <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> propriedade como `true` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9763f-135">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

<span data-ttu-id="9763f-136">Aqui está um objeto de exemplo para serializar e a saída JSON:</span><span class="sxs-lookup"><span data-stu-id="9763f-136">Here's an example object to serialize and JSON output:</span></span>

| <span data-ttu-id="9763f-137">Propriedade</span><span class="sxs-lookup"><span data-stu-id="9763f-137">Property</span></span>             | <span data-ttu-id="9763f-138">Valor</span><span class="sxs-lookup"><span data-stu-id="9763f-138">Value</span></span>                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a><span data-ttu-id="9763f-139">Ignorar todas as propriedades de valor padrão</span><span class="sxs-lookup"><span data-stu-id="9763f-139">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="9763f-140">Para evitar a serialização de valores padrão em Propriedades de tipo de valor, defina a <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> propriedade como <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9763f-140">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="9763f-141">A <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> configuração também impede a serialização de tipo de referência de valor nulo e propriedades de tipo de valor anulável.</span><span class="sxs-lookup"><span data-stu-id="9763f-141">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> setting also prevents serialization of null-value reference type and nullable value type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="9763f-142">Não há uma maneira interna de impedir a serialização de propriedades com padrões de tipo de valor no `System.Text.Json` .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="9763f-142">There is no built-in way to prevent serialization of properties with value type defaults in `System.Text.Json` in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="9763f-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="9763f-143">See also</span></span>

* [<span data-ttu-id="9763f-144">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="9763f-144">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="9763f-145">Criar instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="9763f-145">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="9763f-146">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="9763f-146">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="9763f-147">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="9763f-147">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="9763f-148">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="9763f-148">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="9763f-149">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="9763f-149">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="9763f-150">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="9763f-150">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="9763f-151">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="9763f-151">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="9763f-152">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="9763f-152">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="9763f-153">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="9763f-153">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
