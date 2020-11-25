---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031954"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="e4b30-101">As propriedades UriBuilder não precedem mais os caracteres à esquerda</span><span class="sxs-lookup"><span data-stu-id="e4b30-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="e4b30-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> Não precede mais um caractere à esquerda `#` e <xref:System.UriBuilder.Query?displayProperty=nameWithType> não precede mais um caractere à esquerda `?` quando já existe um.</span><span class="sxs-lookup"><span data-stu-id="e4b30-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e4b30-103">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="e4b30-103">Change description</span></span>

<span data-ttu-id="e4b30-104">Em .NET Framework, as <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> <xref:System.UriBuilder.Query?displayProperty=nameWithType> Propriedades e sempre precedem um `#` `?` caractere ou, respectivamente, ao valor que está sendo armazenado.</span><span class="sxs-lookup"><span data-stu-id="e4b30-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="e4b30-105">Esse comportamento pode resultar em vários `#` `?` caracteres ou no valor armazenado se a cadeia de caracteres já contiver um desses caracteres à esquerda.</span><span class="sxs-lookup"><span data-stu-id="e4b30-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="e4b30-106">Por exemplo, o valor de <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> pode se tornar `##main` .</span><span class="sxs-lookup"><span data-stu-id="e4b30-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="e4b30-107">A partir do .NET Core 1,0, essas propriedades não precedem mais os `#` `?` caracteres ou ao valor armazenado, se já houver um presente no início da cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e4b30-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e4b30-108">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="e4b30-108">Version introduced</span></span>

<span data-ttu-id="e4b30-109">1.0</span><span class="sxs-lookup"><span data-stu-id="e4b30-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e4b30-110">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="e4b30-110">Recommended action</span></span>

<span data-ttu-id="e4b30-111">Você não precisa mais remover explicitamente nenhum desses caracteres à esquerda ao definir os valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e4b30-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="e4b30-112">Isso é especialmente útil quando você está acrescentando valores, porque você não precisa mais remover o à esquerda `#` ou `?` cada vez que você acrescenta.</span><span class="sxs-lookup"><span data-stu-id="e4b30-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="e4b30-113">Por exemplo, o trecho de código a seguir mostra a diferença de comportamento entre .NET Framework e o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4b30-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="e4b30-114">Em .NET Framework, a saída é `????one=1&two=2&three=3&four=4` .</span><span class="sxs-lookup"><span data-stu-id="e4b30-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="e4b30-115">No .NET Core, a saída é `?one=1&two=2&three=3&four=4` .</span><span class="sxs-lookup"><span data-stu-id="e4b30-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="e4b30-116">Categoria</span><span class="sxs-lookup"><span data-stu-id="e4b30-116">Category</span></span>

<span data-ttu-id="e4b30-117">Bibliotecas principais do .NET</span><span class="sxs-lookup"><span data-stu-id="e4b30-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e4b30-118">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="e4b30-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
