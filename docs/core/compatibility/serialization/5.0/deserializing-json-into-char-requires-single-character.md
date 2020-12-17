---
title: 'Alteração significativa: o caractere de desserialização requer uma cadeia de caracteres de caractere único'
description: Saiba mais sobre a alteração significativa no .NET 5,0, em que System.Text.Jsrequer uma cadeia de caracteres de caractere único no JSON ao desserializar para um destino Char.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633865"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a><span data-ttu-id="f0fda-103">System.Text.Json requer uma cadeia de caracteres de caractere único para desserializar um Char</span><span class="sxs-lookup"><span data-stu-id="f0fda-103">System.Text.Json requires single-char string to deserialize a char</span></span>

<span data-ttu-id="f0fda-104">Para desserializar com êxito um <xref:System.Char> using <xref:System.Text.Json> , a cadeia de caracteres JSON deve conter um único caractere.</span><span class="sxs-lookup"><span data-stu-id="f0fda-104">To successfully deserialize a <xref:System.Char> using <xref:System.Text.Json>, the JSON string must contain a single character.</span></span>

## <a name="change-description"></a><span data-ttu-id="f0fda-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="f0fda-105">Change description</span></span>

<span data-ttu-id="f0fda-106">Nas versões anteriores do .NET, uma `char` cadeia de caracteres múltipla no JSON é desserializada com êxito para uma `char` propriedade ou campo.</span><span class="sxs-lookup"><span data-stu-id="f0fda-106">In previous .NET versions, a multi-`char` string in the JSON is successfully deserialized to a `char` property or field.</span></span> <span data-ttu-id="f0fda-107">Somente a primeira `char` da cadeia de caracteres é usada, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f0fda-107">Only the first `char` of the string is used, as in the following example:</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

<span data-ttu-id="f0fda-108">No .NET 5,0 e posterior, qualquer coisa que não seja uma `char` cadeia de caracteres única faz com que a <xref:System.Text.Json.JsonException> seja gerada quando o destino de desserialização for um `char` .</span><span class="sxs-lookup"><span data-stu-id="f0fda-108">In .NET 5.0 and later, anything other than a single-`char` string causes a <xref:System.Text.Json.JsonException> to be thrown when the deserialization target is a `char`.</span></span> <span data-ttu-id="f0fda-109">A cadeia de caracteres de exemplo a seguir é desserializada com êxito em todas as versões do .NET:</span><span class="sxs-lookup"><span data-stu-id="f0fda-109">The following example string is successfully deserialized in all .NET versions:</span></span>

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="f0fda-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="f0fda-110">Version introduced</span></span>

<span data-ttu-id="f0fda-111">5.0</span><span class="sxs-lookup"><span data-stu-id="f0fda-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f0fda-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="f0fda-112">Reason for change</span></span>

<span data-ttu-id="f0fda-113">A análise para desserialização deve ter sucesso apenas quando a carga fornecida é válida para o tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f0fda-113">Parsing for deserialization should only succeed when the provided payload is valid for the target type.</span></span> <span data-ttu-id="f0fda-114">Para um `char` tipo, a única carga válida é uma cadeia de `char` caracteres única.</span><span class="sxs-lookup"><span data-stu-id="f0fda-114">For a `char` type, the only valid payload is a single-`char` string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f0fda-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="f0fda-115">Recommended action</span></span>

<span data-ttu-id="f0fda-116">Quando você desserializar JSON em um `char` destino, certifique-se de que a cadeia de caracteres consiste em um único `char` .</span><span class="sxs-lookup"><span data-stu-id="f0fda-116">When you deserialize JSON into a `char` target, make sure the string consists of a single `char`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f0fda-117">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="f0fda-117">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
