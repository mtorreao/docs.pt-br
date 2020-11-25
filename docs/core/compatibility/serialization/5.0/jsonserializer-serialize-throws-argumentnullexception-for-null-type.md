---
title: 'Alteração significativa: Serialize gera uma exceção quando o parâmetro de tipo é nulo'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os métodos de serialização JsonSerialize que têm um parâmetro de tipo agora lançam uma exceção sempre que NULL é passado para esse parâmetro.
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760503"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="c69e8-103">JsonSerializer. Serialize gera ArgumentNullException quando o parâmetro de tipo é nulo</span><span class="sxs-lookup"><span data-stu-id="c69e8-103">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="c69e8-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> e <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> sobrecargas que têm um parâmetro do tipo <xref:System.Type> agora lançam um <xref:System.ArgumentNullException> sempre que `null` é passado para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c69e8-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a parameter of type <xref:System.Type> now throw an <xref:System.ArgumentNullException> whenever `null` is passed for that parameter.</span></span>

## <a name="change-description"></a><span data-ttu-id="c69e8-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="c69e8-105">Change description</span></span>

<span data-ttu-id="c69e8-106">No .NET Core 3,1, as <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> sobrecargas que têm um <xref:System.Type> parâmetro geram um <xref:System.ArgumentNullException> quando `null` é passado para o `Type inputType` parâmetro, mas não se o `Object value` parâmetro também for `null` .</span><span class="sxs-lookup"><span data-stu-id="c69e8-106">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="c69e8-107">A partir do .NET 5,0, esses métodos *sempre* lançam um <xref:System.ArgumentNullException> quando `null` é passado para o <xref:System.Type> parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c69e8-107">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="c69e8-108">Comportamento no .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="c69e8-108">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="c69e8-109">Comportamento no .NET 5,0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="c69e8-109">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a><span data-ttu-id="c69e8-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="c69e8-110">Version introduced</span></span>

<span data-ttu-id="c69e8-111">5.0</span><span class="sxs-lookup"><span data-stu-id="c69e8-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c69e8-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="c69e8-112">Reason for change</span></span>

<span data-ttu-id="c69e8-113">A passagem `null` para o `Type inputType` parâmetro é inaceitável e sempre deve lançar um <xref:System.ArgumentNullException> .</span><span class="sxs-lookup"><span data-stu-id="c69e8-113">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c69e8-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="c69e8-114">Recommended action</span></span>

<span data-ttu-id="c69e8-115">Certifique-se de que você não está passando `null` para o `Type inputType` parâmetro desses métodos.</span><span class="sxs-lookup"><span data-stu-id="c69e8-115">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c69e8-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="c69e8-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
