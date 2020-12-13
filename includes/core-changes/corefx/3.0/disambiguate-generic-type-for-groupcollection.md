---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366861"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a><span data-ttu-id="10daf-101">Passar GroupCollection para métodos de extensão assumindo IEnumerable \<T> requer ambiguidade</span><span class="sxs-lookup"><span data-stu-id="10daf-101">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>

<span data-ttu-id="10daf-102">Ao chamar um método de extensão que usa um `IEnumerable<T>` em um <xref:System.Text.RegularExpressions.GroupCollection> , você deve eliminar a ambiguidade do tipo usando uma conversão.</span><span class="sxs-lookup"><span data-stu-id="10daf-102">When calling an extension method that takes an `IEnumerable<T>` on a <xref:System.Text.RegularExpressions.GroupCollection>, you must disambiguate the type using a cast.</span></span>

#### <a name="change-description"></a><span data-ttu-id="10daf-103">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="10daf-103">Change description</span></span>

<span data-ttu-id="10daf-104">A partir do .NET Core 3,0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implementa `IEnumerable<KeyValuePair<String,Group>>` -se além dos outros tipos que ele implementa, incluindo `IEnumerable<Group>` .</span><span class="sxs-lookup"><span data-stu-id="10daf-104">Starting in .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implements `IEnumerable<KeyValuePair<String,Group>>` in addition to the other types it implements, including `IEnumerable<Group>`.</span></span> <span data-ttu-id="10daf-105">Isso resulta em ambiguidade ao chamar um método de extensão que usa um <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="10daf-105">This results in ambiguity when calling an extension method that takes an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="10daf-106">Se você chamar esse método de extensão em uma <xref:System.Text.RegularExpressions.GroupCollection> instância, por exemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType> você verá o seguinte erro do compilador:</span><span class="sxs-lookup"><span data-stu-id="10daf-106">If you call such an extension method on a <xref:System.Text.RegularExpressions.GroupCollection> instance, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, you'll see the following compiler error:</span></span>

<span data-ttu-id="10daf-107">**CS1061: ' GroupCollection ' não contém uma definição para ' count ' e nenhum método de extensão acessível ' count ' aceitando um primeiro argumento do tipo ' GroupCollection ' foi encontrado (está faltando uma diretiva using ou uma referência de assembly?)**</span><span class="sxs-lookup"><span data-stu-id="10daf-107">**CS1061: 'GroupCollection' does not contain a definition for 'Count' and no accessible extension method 'Count' accepting a first argument of type 'GroupCollection' could be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="10daf-108">Nas versões anteriores do .NET, não havia nenhuma ambiguidade e nenhum erro do compilador.</span><span class="sxs-lookup"><span data-stu-id="10daf-108">In previous versions of .NET, there was no ambiguity and no compiler error.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="10daf-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="10daf-109">Version introduced</span></span>

<span data-ttu-id="10daf-110">3.0</span><span class="sxs-lookup"><span data-stu-id="10daf-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="10daf-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="10daf-111">Reason for change</span></span>

<span data-ttu-id="10daf-112">Essa foi uma [alteração sem intenção](https://github.com/dotnet/corefx/pull/30077).</span><span class="sxs-lookup"><span data-stu-id="10daf-112">This was an [unintentional breaking change](https://github.com/dotnet/corefx/pull/30077).</span></span> <span data-ttu-id="10daf-113">Por ter sido assim por algum tempo, não planejamos revertê-la.</span><span class="sxs-lookup"><span data-stu-id="10daf-113">Because it has been like this for some time, we don't plan to revert it.</span></span> <span data-ttu-id="10daf-114">Além disso, essa alteração seria interrompida.</span><span class="sxs-lookup"><span data-stu-id="10daf-114">In addition, such a change would itself be breaking.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="10daf-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="10daf-115">Recommended action</span></span>

<span data-ttu-id="10daf-116">Para <xref:System.Text.RegularExpressions.GroupCollection> instâncias, desambiguar chamadas para métodos de extensão que aceitam um `IEnumerable<T>` com uma conversão.</span><span class="sxs-lookup"><span data-stu-id="10daf-116">For <xref:System.Text.RegularExpressions.GroupCollection> instances, disambiguate calls to extension methods that accept an `IEnumerable<T>` with a cast.</span></span>

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a><span data-ttu-id="10daf-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="10daf-117">Category</span></span>

<span data-ttu-id="10daf-118">Bibliotecas principais do .NET</span><span class="sxs-lookup"><span data-stu-id="10daf-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="10daf-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="10daf-119">Affected APIs</span></span>

<span data-ttu-id="10daf-120">Qualquer método de extensão que aceita um <xref:System.Collections.Generic.IEnumerable%601> é afetado.</span><span class="sxs-lookup"><span data-stu-id="10daf-120">Any extension method that accepts an <xref:System.Collections.Generic.IEnumerable%601> is affected.</span></span> <span data-ttu-id="10daf-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="10daf-121">For example:</span></span>

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- <span data-ttu-id="10daf-122">A maioria dos `System.Linq.Enumerable` métodos, por exemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="10daf-122">Most of the `System.Linq.Enumerable` methods, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span></span>
- <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName>
- <xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>

<!--

#### Affected APIs

- ``M:System.Collections.Immutable.ImmutableArray.ToImmutableArray``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary`
- `Overload:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet`
- ``M:System.Collections.Immutable.ImmutableList.ToImmutableList``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary`
- `Overload:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet`
- `Overload:System.Data.DataTableExtensions.CopyToDataTable`
- `Overload:System.Linq.Enumerable.Count`
- `Overload:System.Linq.ParallelEnumerable.AsParallel`
- `Overload:System.Linq.Queryable.AsQueryable`

-->
