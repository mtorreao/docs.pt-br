---
title: 'Alteração significativa: as opções PropertyNamingPolicy, PropertyNameCaseInsensitive e Encoder são respeitadas para pares de chave-valor'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que as opções PropertyNamingPolicy, PropertyNameCaseInsensitive e Encoder são respeitadas ao serializar e desserializar os nomes de propriedade de chave e valor de uma instância de par chave-valor.
ms.date: 10/18/2020
ms.openlocfilehash: 5d75cb7feea32cc4b942e5261c5b609e00a5082c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760502"
---
# <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="7b9b7-103">As opções PropertyNamingPolicy, PropertyNameCaseInsensitive e Encoder são respeitadas ao serializar e desserializar pares chave-valor</span><span class="sxs-lookup"><span data-stu-id="7b9b7-103">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="7b9b7-104"><xref:System.Text.Json.JsonSerializer> Agora respeita as <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> Opções e <xref:System.Text.Json.JsonSerializerOptions.Encoder> ao serializar os <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> nomes de propriedade e de uma <xref:System.Collections.Generic.KeyValuePair%602> instância do.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-104"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="7b9b7-105">Além disso, <xref:System.Text.Json.JsonSerializer> honra as <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opções e ao desserializar <xref:System.Collections.Generic.KeyValuePair%602> instâncias.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-105">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

## <a name="change-description"></a><span data-ttu-id="7b9b7-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="7b9b7-106">Change description</span></span>

### <a name="serialization"></a><span data-ttu-id="7b9b7-107">Serialização</span><span class="sxs-lookup"><span data-stu-id="7b9b7-107">Serialization</span></span>

<span data-ttu-id="7b9b7-108">Nas versões do .NET Core 3. x e nas versões 4.6.0-4.7.2 do [System.Text.Jsno pacote NuGet](https://www.nuget.org/packages/System.Text.Json), as propriedades das <xref:System.Collections.Generic.KeyValuePair%602> instâncias são sempre serializadas como "chave" e "valor" exatamente, independentemente de qualquer <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> opção e.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-108">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="7b9b7-109">O exemplo de código a seguir mostra como as <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> Propriedades e *não* são camel-case após a serialização, mesmo que a política de nomenclatura de propriedade especificada determine isso.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="7b9b7-110">A partir do .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> as <xref:System.Text.Json.JsonSerializerOptions.Encoder> Opções e são respeitadas ao serializar <xref:System.Collections.Generic.KeyValuePair%602> instâncias.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-110">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="7b9b7-111">O exemplo de código a seguir mostra como as <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> Propriedades e são camel-case após a serialização, de acordo com a política de nomenclatura de propriedade especificada.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-111">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

### <a name="deserialization"></a><span data-ttu-id="7b9b7-112">Desserialização</span><span class="sxs-lookup"><span data-stu-id="7b9b7-112">Deserialization</span></span>

<span data-ttu-id="7b9b7-113">Nas versões do .NET Core 3. x e nas versões 4.7. x do [System.Text.Jsno pacote NuGet](https://www.nuget.org/packages/System.Text.Json), um <xref:System.Text.Json.JsonException> é gerado quando os nomes de propriedade JSON não são precisamente `Key` e `Value` , por exemplo, se não começam com uma letra maiúscula.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-113">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="7b9b7-114">A exceção é lançada mesmo que uma política de nomenclatura de propriedade especificada permita expressamente.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-114">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="7b9b7-115">A partir do .NET 5,0, <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> as <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> Opções e são respeitadas ao desserializar usando <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="7b9b7-115">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="7b9b7-116">Por exemplo, o trecho de código a seguir mostra a desserialização bem-sucedida de nomes de propriedade e letras minúsculas <xref:System.Collections.Generic.KeyValuePair%602.Key> <xref:System.Collections.Generic.KeyValuePair%602.Value> porque a política de nomenclatura de propriedade especificada permite.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-116">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="7b9b7-117">Para acomodar as cargas que foram serializadas com versões anteriores, "chave" e "valor" são especiais para corresponder ao desserializar.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-117">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="7b9b7-118">Embora os <xref:System.Collections.Generic.KeyValuePair%602.Key> nomes de <xref:System.Collections.Generic.KeyValuePair%602.Value> propriedade e não sejam camel-case de acordo com a <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> opção in no exemplo de código a seguir, eles são desserializados com êxito.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-118">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

## <a name="version-introduced"></a><span data-ttu-id="7b9b7-119">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="7b9b7-119">Version introduced</span></span>

<span data-ttu-id="7b9b7-120">5.0</span><span class="sxs-lookup"><span data-stu-id="7b9b7-120">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7b9b7-121">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="7b9b7-121">Reason for change</span></span>

<span data-ttu-id="7b9b7-122">Comentários de clientes substanciais indicaram que o <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> deve ser respeitado.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-122">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="7b9b7-123">Para fins de integridade, <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> as <xref:System.Text.Json.JsonSerializerOptions.Encoder> Opções e também são respeitadas, para que as <xref:System.Collections.Generic.KeyValuePair%602> instâncias sejam tratadas da mesma forma que qualquer outro objeto CLR antigo (POCO).</span><span class="sxs-lookup"><span data-stu-id="7b9b7-123">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7b9b7-124">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="7b9b7-124">Recommended action</span></span>

<span data-ttu-id="7b9b7-125">Se essa alteração for prejudicial para você, você poderá usar um [conversor personalizado](../../../../standard/serialization/system-text-json-converters-how-to.md) que implementa a semântica desejada.</span><span class="sxs-lookup"><span data-stu-id="7b9b7-125">If this change is disruptive to you, you can use a [custom converter](../../../../standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7b9b7-126">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="7b9b7-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
