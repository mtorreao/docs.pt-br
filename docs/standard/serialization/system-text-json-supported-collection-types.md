---
title: Tipos de coleção com suporte no System.Text.Json
description: Saiba quais tipos de coleção têm suporte para serialização pelas APIs no System.Text.Json namespace.
ms.date: 01/06/2021
no-loc:
- System.Text.Json
ms.topic: reference
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 48033689e844dd29c999395255b5a1565fa2996e
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970986"
---
# <a name="supported-collection-types-in-no-locsystemtextjson"></a><span data-ttu-id="91612-103">Tipos de coleção com suporte no System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="91612-103">Supported collection types in System.Text.Json</span></span>

<span data-ttu-id="91612-104">Este artigo fornece uma visão geral de quais coleções têm suporte para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="91612-104">This article gives an overview of which collections are supported for serialization and deserialization.</span></span> <span data-ttu-id="91612-105"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> oferece suporte a um tipo de coleção para serialização se:</span><span class="sxs-lookup"><span data-stu-id="91612-105"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> supports a collection type for serialization if it:</span></span>

* <span data-ttu-id="91612-106">Deriva de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="91612-106">Derives from <xref:System.Collections.IEnumerable>.</span></span>
* <span data-ttu-id="91612-107">Contém elementos que são serializáveis.</span><span class="sxs-lookup"><span data-stu-id="91612-107">Contains elements that are serializable.</span></span>

<span data-ttu-id="91612-108">O serializador chama o <xref:System.Collections.IEnumerable.GetEnumerator> método e grava os elementos.</span><span class="sxs-lookup"><span data-stu-id="91612-108">The serializer calls the <xref:System.Collections.IEnumerable.GetEnumerator> method, and writes the elements.</span></span>

<span data-ttu-id="91612-109">A desserialização é mais complicada e não tem suporte para alguns tipos de coleção.</span><span class="sxs-lookup"><span data-stu-id="91612-109">Deserialization is more complicated and is not supported for some collection types.</span></span>

<span data-ttu-id="91612-110">As seções a seguir são organizadas por namespace e mostram quais tipos têm suporte para serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="91612-110">The following sections are organized by namespace and show which types are supported for serialization and deserialization.</span></span>

## <a name="systemcollections-namespace"></a><span data-ttu-id="91612-111">Namespace System.Collections</span><span class="sxs-lookup"><span data-stu-id="91612-111">System.Collections namespace</span></span>

| <span data-ttu-id="91612-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-112">Type</span></span>                                      | <span data-ttu-id="91612-113">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-113">Serialization</span></span> | <span data-ttu-id="91612-114">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-114">Deserialization</span></span> |
|-------------------------------------------|---------------|-----------------|
| <xref:System.Collections.ArrayList>       | <span data-ttu-id="91612-115">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-115">✔️</span></span>           | <span data-ttu-id="91612-116">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-116">✔️</span></span>              |
| <xref:System.Collections.BitArray>        | <span data-ttu-id="91612-117">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-117">✔️</span></span>           | ❌              |
| <xref:System.Collections.DictionaryEntry> | <span data-ttu-id="91612-118">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-118">✔️</span></span>           | <span data-ttu-id="91612-119">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-119">✔️</span></span>              |
| <xref:System.Collections.Hashtable>       | <span data-ttu-id="91612-120">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-120">✔️</span></span>           | <span data-ttu-id="91612-121">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-121">✔️</span></span>              |
| <xref:System.Collections.Queue>           | <span data-ttu-id="91612-122">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-122">✔️</span></span>           | <span data-ttu-id="91612-123">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-123">✔️</span></span>              |
| <xref:System.Collections.SortedList>      | <span data-ttu-id="91612-124">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-124">✔️</span></span>           | <span data-ttu-id="91612-125">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-125">✔️</span></span>              |
| <xref:System.Collections.Stack>           | <span data-ttu-id="91612-126">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-126">✔️</span></span>           | <span data-ttu-id="91612-127">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-127">✔️</span></span>              |
| <xref:System.Collections.ICollection>     | <span data-ttu-id="91612-128">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-128">✔️</span></span>           | <span data-ttu-id="91612-129">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-129">✔️</span></span>              |
| <xref:System.Collections.IDictionary>     | <span data-ttu-id="91612-130">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-130">✔️</span></span>           | <span data-ttu-id="91612-131">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-131">✔️</span></span>              |
| <xref:System.Collections.IEnumerable>     | <span data-ttu-id="91612-132">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-132">✔️</span></span>           | <span data-ttu-id="91612-133">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-133">✔️</span></span>              |
| <xref:System.Collections.IList>           | <span data-ttu-id="91612-134">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-134">✔️</span></span>           | <span data-ttu-id="91612-135">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-135">✔️</span></span>              |

## <a name="systemcollectionsgeneric-namespace"></a><span data-ttu-id="91612-136">Namespace System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="91612-136">System.Collections.Generic namespace</span></span>

::: zone pivot="dotnet-5-0"

| <span data-ttu-id="91612-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-137">Type</span></span>                                                      | <span data-ttu-id="91612-138">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-138">Serialization</span></span> | <span data-ttu-id="91612-139">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-139">Deserialization</span></span> |
|-----------------------------------------------------------|---------------|-----------------|
| <span data-ttu-id="91612-140"><xref:System.Collections.Generic.Dictionary%602> \*</span><span class="sxs-lookup"><span data-stu-id="91612-140"><xref:System.Collections.Generic.Dictionary%602> \*</span></span>       | <span data-ttu-id="91612-141">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-141">✔️</span></span>           | <span data-ttu-id="91612-142">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-142">✔️</span></span>              |
| <xref:System.Collections.Generic.HashSet%601>             | <span data-ttu-id="91612-143">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-143">✔️</span></span>           | <span data-ttu-id="91612-144">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-144">✔️</span></span>              |
| <xref:System.Collections.Generic.KeyValuePair%602>        | <span data-ttu-id="91612-145">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-145">✔️</span></span>           | <span data-ttu-id="91612-146">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-146">✔️</span></span>              |
| <xref:System.Collections.Generic.LinkedList%601>          | <span data-ttu-id="91612-147">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-147">✔️</span></span>           | <span data-ttu-id="91612-148">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-148">✔️</span></span>              |
| <xref:System.Collections.Generic.LinkedListNode%601>      | <span data-ttu-id="91612-149">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-149">✔️</span></span>           | ❌              |
| <xref:System.Collections.Generic.List%601>                | <span data-ttu-id="91612-150">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-150">✔️</span></span>           | <span data-ttu-id="91612-151">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-151">✔️</span></span>              |
| <xref:System.Collections.Generic.Queue%601>               | <span data-ttu-id="91612-152">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-152">✔️</span></span>           | <span data-ttu-id="91612-153">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-153">✔️</span></span>              |
| <span data-ttu-id="91612-154"><xref:System.Collections.Generic.SortedDictionary%602> \*</span><span class="sxs-lookup"><span data-stu-id="91612-154"><xref:System.Collections.Generic.SortedDictionary%602> \*</span></span> | <span data-ttu-id="91612-155">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-155">✔️</span></span>           | <span data-ttu-id="91612-156">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-156">✔️</span></span>              |
| <span data-ttu-id="91612-157"><xref:System.Collections.Generic.SortedList%602> \*</span><span class="sxs-lookup"><span data-stu-id="91612-157"><xref:System.Collections.Generic.SortedList%602> \*</span></span>       | <span data-ttu-id="91612-158">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-158">✔️</span></span>           | <span data-ttu-id="91612-159">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-159">✔️</span></span>              |
| <xref:System.Collections.Generic.SortedSet%601>           | <span data-ttu-id="91612-160">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-160">✔️</span></span>           | <span data-ttu-id="91612-161">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-161">✔️</span></span>              |
| <xref:System.Collections.Generic.Stack%601>               | <span data-ttu-id="91612-162">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-162">✔️</span></span>           | <span data-ttu-id="91612-163">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-163">✔️</span></span>              |
| <xref:System.Collections.Generic.IAsyncEnumerable%601>    | ❌           | ❌              |
| <xref:System.Collections.Generic.ICollection%601>         | <span data-ttu-id="91612-164">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-164">✔️</span></span>           | <span data-ttu-id="91612-165">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-165">✔️</span></span>              |
| <span data-ttu-id="91612-166"><xref:System.Collections.Generic.IDictionary%602> \*</span><span class="sxs-lookup"><span data-stu-id="91612-166"><xref:System.Collections.Generic.IDictionary%602> \*</span></span>      | <span data-ttu-id="91612-167">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-167">✔️</span></span>           | <span data-ttu-id="91612-168">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-168">✔️</span></span>              |
| <xref:System.Collections.Generic.IEnumerable%601>         | <span data-ttu-id="91612-169">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-169">✔️</span></span>           | <span data-ttu-id="91612-170">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-170">✔️</span></span>              |
| <xref:System.Collections.Generic.IList%601>               | <span data-ttu-id="91612-171">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-171">✔️</span></span>           | <span data-ttu-id="91612-172">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-172">✔️</span></span>              |
| <xref:System.Collections.Generic.IReadOnlyCollection%601> | <span data-ttu-id="91612-173">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-173">✔️</span></span>           | <span data-ttu-id="91612-174">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-174">✔️</span></span>              |
| <span data-ttu-id="91612-175"><xref:System.Collections.Generic.IReadOnlyDictionary%602> \*</span><span class="sxs-lookup"><span data-stu-id="91612-175"><xref:System.Collections.Generic.IReadOnlyDictionary%602> \*</span></span> | <span data-ttu-id="91612-176">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-176">✔️</span></span>        | <span data-ttu-id="91612-177">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-177">✔️</span></span>              |
| <xref:System.Collections.Generic.IReadOnlyList%601>       | <span data-ttu-id="91612-178">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-178">✔️</span></span>           | <span data-ttu-id="91612-179">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-179">✔️</span></span>              |
| <xref:System.Collections.Generic.ISet%601>                | <span data-ttu-id="91612-180">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-180">✔️</span></span>           | <span data-ttu-id="91612-181">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-181">✔️</span></span>              |

::: zone-end

::: zone pivot="dotnet-core-3-1"

| <span data-ttu-id="91612-182">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-182">Type</span></span>                                                                                            | <span data-ttu-id="91612-183">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-183">Serialization</span></span> | <span data-ttu-id="91612-184">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-184">Deserialization</span></span> |
|-------------------------------------------------------------------------------------------------|---------------|-----------------|
| <span data-ttu-id="91612-185">[Dicionário \<string, TValue> ](xref:System.Collections.Generic.Dictionary%602) do\*</span><span class="sxs-lookup"><span data-stu-id="91612-185">[Dictionary\<string, TValue>](xref:System.Collections.Generic.Dictionary%602) \*</span></span>                | <span data-ttu-id="91612-186">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-186">✔️</span></span>           | <span data-ttu-id="91612-187">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-187">✔️</span></span>              |
| <xref:System.Collections.Generic.HashSet%601>                                                   | <span data-ttu-id="91612-188">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-188">✔️</span></span>           | <span data-ttu-id="91612-189">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-189">✔️</span></span>              |
| <xref:System.Collections.Generic.KeyValuePair%602>                                              | <span data-ttu-id="91612-190">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-190">✔️</span></span>           | <span data-ttu-id="91612-191">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-191">✔️</span></span>              |
| <xref:System.Collections.Generic.LinkedList%601>                                                | <span data-ttu-id="91612-192">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-192">✔️</span></span>           | <span data-ttu-id="91612-193">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-193">✔️</span></span>              |
| <xref:System.Collections.Generic.LinkedListNode%601>                                            | <span data-ttu-id="91612-194">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-194">✔️</span></span>           | ❌              |
| <xref:System.Collections.Generic.List%601>                                                      | <span data-ttu-id="91612-195">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-195">✔️</span></span>           | <span data-ttu-id="91612-196">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-196">✔️</span></span>              |
| <xref:System.Collections.Generic.Queue%601>                                                     | <span data-ttu-id="91612-197">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-197">✔️</span></span>           | <span data-ttu-id="91612-198">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-198">✔️</span></span>              |
| <span data-ttu-id="91612-199">[SortedDictionary \<string, TValue> ](xref:System.Collections.Generic.SortedDictionary%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-199">[SortedDictionary\<string, TValue>](xref:System.Collections.Generic.SortedDictionary%602) \*</span></span>    | <span data-ttu-id="91612-200">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-200">✔️</span></span>           | <span data-ttu-id="91612-201">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-201">✔️</span></span>              |
| <span data-ttu-id="91612-202">[ \<string, TValue> Classificadolist](xref:System.Collections.Generic.SortedList%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-202">[SortedList\<string, TValue>](xref:System.Collections.Generic.SortedList%602) \*</span></span>                | <span data-ttu-id="91612-203">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-203">✔️</span></span>           | <span data-ttu-id="91612-204">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-204">✔️</span></span>              |
| <xref:System.Collections.Generic.SortedSet%601>                                                 | <span data-ttu-id="91612-205">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-205">✔️</span></span>           | <span data-ttu-id="91612-206">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-206">✔️</span></span>              |
| <xref:System.Collections.Generic.Stack%601>                                                     | <span data-ttu-id="91612-207">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-207">✔️</span></span>           | <span data-ttu-id="91612-208">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-208">✔️</span></span>              |
| <xref:System.Collections.Generic.IAsyncEnumerable%601>                                          | ❌           | ❌              |
| <xref:System.Collections.Generic.ICollection%601>                                               | <span data-ttu-id="91612-209">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-209">✔️</span></span>           | <span data-ttu-id="91612-210">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-210">✔️</span></span>              |
| <span data-ttu-id="91612-211">[IDictionary\<string, TValue> ](xref:System.Collections.Generic.IDictionary%602) \*</span><span class="sxs-lookup"><span data-stu-id="91612-211">[IDictionary\<string, TValue>](xref:System.Collections.Generic.IDictionary%602) \*</span></span>              | <span data-ttu-id="91612-212">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-212">✔️</span></span>           | <span data-ttu-id="91612-213">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-213">✔️</span></span>              |
| <xref:System.Collections.Generic.IEnumerable%601>                                               | <span data-ttu-id="91612-214">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-214">✔️</span></span>           | <span data-ttu-id="91612-215">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-215">✔️</span></span>              |
| <xref:System.Collections.Generic.IList%601>                                                     | <span data-ttu-id="91612-216">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-216">✔️</span></span>           | <span data-ttu-id="91612-217">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-217">✔️</span></span>              |
| <xref:System.Collections.Generic.IReadOnlyCollection%601>                                       | <span data-ttu-id="91612-218">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-218">✔️</span></span>           | <span data-ttu-id="91612-219">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-219">✔️</span></span>              |
| <span data-ttu-id="91612-220">[IReadOnlyDictionary \<string, TValue> ](xref:System.Collections.Generic.IReadOnlyDictionary%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-220">[IReadOnlyDictionary\<string, TValue>](xref:System.Collections.Generic.IReadOnlyDictionary%602) \*</span></span> | <span data-ttu-id="91612-221">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-221">✔️</span></span>        | <span data-ttu-id="91612-222">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-222">✔️</span></span>              |
| <xref:System.Collections.Generic.IReadOnlyList%601>                                             | <span data-ttu-id="91612-223">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-223">✔️</span></span>           | <span data-ttu-id="91612-224">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-224">✔️</span></span>              |
| <xref:System.Collections.Generic.ISet%601>                                                      | <span data-ttu-id="91612-225">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-225">✔️</span></span>           | <span data-ttu-id="91612-226">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-226">✔️</span></span>              |

::: zone-end

<span data-ttu-id="91612-227">\* Consulte [tipos de chave com suporte](#supported-key-types).</span><span class="sxs-lookup"><span data-stu-id="91612-227">\* See [Supported key types](#supported-key-types).</span></span>

## <a name="systemcollectionsimmutable-namespace"></a><span data-ttu-id="91612-228">Namespace System. Collections. imutável</span><span class="sxs-lookup"><span data-stu-id="91612-228">System.Collections.Immutable namespace</span></span>

::: zone pivot="dotnet-5-0"

| <span data-ttu-id="91612-229">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-229">Type</span></span>                                                              | <span data-ttu-id="91612-230">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-230">Serialization</span></span> | <span data-ttu-id="91612-231">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-231">Deserialization</span></span> |
|-------------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.Immutable.ImmutableArray%601>            | <span data-ttu-id="91612-232">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-232">✔️</span></span>           | <span data-ttu-id="91612-233">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-233">✔️</span></span>              |
| <span data-ttu-id="91612-234"><xref:System.Collections.Immutable.ImmutableDictionary%602> \*\*</span><span class="sxs-lookup"><span data-stu-id="91612-234"><xref:System.Collections.Immutable.ImmutableDictionary%602> \*\*</span></span>  | <span data-ttu-id="91612-235">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-235">✔️</span></span>           | <span data-ttu-id="91612-236">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-236">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableHashSet%601>          | <span data-ttu-id="91612-237">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-237">✔️</span></span>           | <span data-ttu-id="91612-238">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-238">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableList%601>            | <span data-ttu-id="91612-239">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-239">✔️</span></span>           | <span data-ttu-id="91612-240">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-240">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableQueue%601>            | <span data-ttu-id="91612-241">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-241">✔️</span></span>           | <span data-ttu-id="91612-242">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-242">✔️</span></span>              |
| <span data-ttu-id="91612-243"><xref:System.Collections.Immutable.ImmutableSortedDictionary%602> \*\*</span><span class="sxs-lookup"><span data-stu-id="91612-243"><xref:System.Collections.Immutable.ImmutableSortedDictionary%602> \*\*</span></span> | <span data-ttu-id="91612-244">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-244">✔️</span></span>      | <span data-ttu-id="91612-245">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-245">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableSortedSet%601>        | <span data-ttu-id="91612-246">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-246">✔️</span></span>           | <span data-ttu-id="91612-247">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-247">✔️</span></span>              |
| <span data-ttu-id="91612-248"><xref:System.Collections.Immutable.ImmutableStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-248"><xref:System.Collections.Immutable.ImmutableStack%601> \*</span></span>         | <span data-ttu-id="91612-249">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-249">✔️</span></span>           | <span data-ttu-id="91612-250">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-250">✔️</span></span>              |
| <span data-ttu-id="91612-251"><xref:System.Collections.Immutable.IImmutableDictionary%602> \*\*</span><span class="sxs-lookup"><span data-stu-id="91612-251"><xref:System.Collections.Immutable.IImmutableDictionary%602> \*\*</span></span> | <span data-ttu-id="91612-252">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-252">✔️</span></span>           | <span data-ttu-id="91612-253">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-253">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableList%601>            | <span data-ttu-id="91612-254">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-254">✔️</span></span>           | <span data-ttu-id="91612-255">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-255">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableQueue%601>           | <span data-ttu-id="91612-256">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-256">✔️</span></span>           | <span data-ttu-id="91612-257">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-257">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableSet%601>             | <span data-ttu-id="91612-258">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-258">✔️</span></span>           | <span data-ttu-id="91612-259">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-259">✔️</span></span>              |
| <span data-ttu-id="91612-260"><xref:System.Collections.Immutable.IImmutableStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-260"><xref:System.Collections.Immutable.IImmutableStack%601> \*</span></span>        | <span data-ttu-id="91612-261">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-261">✔️</span></span>           | <span data-ttu-id="91612-262">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-262">✔️</span></span>              |

::: zone-end

::: zone pivot="dotnet-core-3-1"

| <span data-ttu-id="91612-263">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-263">Type</span></span>                                                                                                          | <span data-ttu-id="91612-264">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-264">Serialization</span></span> | <span data-ttu-id="91612-265">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-265">Deserialization</span></span> |
|---------------------------------------------------------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.Immutable.ImmutableArray%601>                                                        | <span data-ttu-id="91612-266">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-266">✔️</span></span>           | <span data-ttu-id="91612-267">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-267">✔️</span></span>              |
| <span data-ttu-id="91612-268">[ImmutableDictionary \<string, TValue> ](xref:System.Collections.Immutable.ImmutableDictionary%602)\*\*</span><span class="sxs-lookup"><span data-stu-id="91612-268">[ImmutableDictionary\<string, TValue>](xref:System.Collections.Immutable.ImmutableDictionary%602) \*\*</span></span>        | <span data-ttu-id="91612-269">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-269">✔️</span></span>           | <span data-ttu-id="91612-270">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-270">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableHashSet%601>                                                      | <span data-ttu-id="91612-271">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-271">✔️</span></span>           | <span data-ttu-id="91612-272">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-272">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableList%601>                                                        | <span data-ttu-id="91612-273">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-273">✔️</span></span>           | <span data-ttu-id="91612-274">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-274">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableQueue%601>                                                        | <span data-ttu-id="91612-275">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-275">✔️</span></span>           | <span data-ttu-id="91612-276">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-276">✔️</span></span>              |
| <span data-ttu-id="91612-277">[ImmutableSortedDictionary \<string, TValue> ](xref:System.Collections.Immutable.ImmutableSortedDictionary%602)\*\*</span><span class="sxs-lookup"><span data-stu-id="91612-277">[ImmutableSortedDictionary\<string, TValue>](xref:System.Collections.Immutable.ImmutableSortedDictionary%602) \*\*</span></span>| <span data-ttu-id="91612-278">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-278">✔️</span></span>       | <span data-ttu-id="91612-279">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-279">✔️</span></span>              |
| <xref:System.Collections.Immutable.ImmutableSortedSet%601>                                                    | <span data-ttu-id="91612-280">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-280">✔️</span></span>           | <span data-ttu-id="91612-281">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-281">✔️</span></span>              |
| <span data-ttu-id="91612-282"><xref:System.Collections.Immutable.ImmutableStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-282"><xref:System.Collections.Immutable.ImmutableStack%601> \*</span></span>                                                     | <span data-ttu-id="91612-283">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-283">✔️</span></span>           | <span data-ttu-id="91612-284">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-284">✔️</span></span>              |
| <span data-ttu-id="91612-285">[IImmutableDictionary \<string, TValue> ](xref:System.Collections.Immutable.IImmutableDictionary%602)\*\*</span><span class="sxs-lookup"><span data-stu-id="91612-285">[IImmutableDictionary\<string, TValue>](xref:System.Collections.Immutable.IImmutableDictionary%602) \*\*</span></span>      | <span data-ttu-id="91612-286">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-286">✔️</span></span>           | <span data-ttu-id="91612-287">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-287">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableList%601>                                                        | <span data-ttu-id="91612-288">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-288">✔️</span></span>           | <span data-ttu-id="91612-289">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-289">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableQueue%601>                                                       | <span data-ttu-id="91612-290">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-290">✔️</span></span>           | <span data-ttu-id="91612-291">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-291">✔️</span></span>              |
| <xref:System.Collections.Immutable.IImmutableSet%601>                                                         | <span data-ttu-id="91612-292">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-292">✔️</span></span>           | <span data-ttu-id="91612-293">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-293">✔️</span></span>              |
| <span data-ttu-id="91612-294"><xref:System.Collections.Immutable.IImmutableStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-294"><xref:System.Collections.Immutable.IImmutableStack%601> \*</span></span>                                                    | <span data-ttu-id="91612-295">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-295">✔️</span></span>           | <span data-ttu-id="91612-296">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-296">✔️</span></span>              |

::: zone-end

<span data-ttu-id="91612-297">\*Consulte [dar suporte à viagem de \<T> ida e volta para a pilha](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="91612-297">\* See [Support round trip for Stack\<T>](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span></span>

<span data-ttu-id="91612-298">\*\* Consulte [tipos de chave com suporte](#supported-key-types).</span><span class="sxs-lookup"><span data-stu-id="91612-298">\*\* See [Supported key types](#supported-key-types).</span></span>

## <a name="systemcollectionsspecialized-namespace"></a><span data-ttu-id="91612-299">Namespace System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="91612-299">System.Collections.Specialized namespace</span></span>

| <span data-ttu-id="91612-300">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-300">Type</span></span>                                                      | <span data-ttu-id="91612-301">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-301">Serialization</span></span> | <span data-ttu-id="91612-302">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-302">Deserialization</span></span> |
|-----------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.Specialized.BitVector32>         | <span data-ttu-id="91612-303">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-303">✔️</span></span>           | ❌\*            |
| <xref:System.Collections.Specialized.HybridDictionary>    | <span data-ttu-id="91612-304">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-304">✔️</span></span>           | <span data-ttu-id="91612-305">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-305">✔️</span></span>              |
| <xref:System.Collections.Specialized.IOrderedDictionary>  | <span data-ttu-id="91612-306">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-306">✔️</span></span>           | ❌              |
| <xref:System.Collections.Specialized.ListDictionary>      | <span data-ttu-id="91612-307">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-307">✔️</span></span>           | <span data-ttu-id="91612-308">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-308">✔️</span></span>              |
| <xref:System.Collections.Specialized.StringCollection>    | <span data-ttu-id="91612-309">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-309">✔️</span></span>           | ❌              |
| <xref:System.Collections.Specialized.StringDictionary>    | <span data-ttu-id="91612-310">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-310">✔️</span></span>           | ❌              |
| <xref:System.Collections.Specialized.NameValueCollection> | <span data-ttu-id="91612-311">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-311">✔️</span></span>           | ❌              |

<span data-ttu-id="91612-312">\* Quando <xref:System.Collections.Specialized.BitVector32> é desserializado, a <xref:System.Collections.Specialized.BitVector32.Data> propriedade é ignorada porque não tem um setter público.</span><span class="sxs-lookup"><span data-stu-id="91612-312">\* When <xref:System.Collections.Specialized.BitVector32> is deserialized, the <xref:System.Collections.Specialized.BitVector32.Data> property is skipped because it doesn't have a public setter.</span></span> <span data-ttu-id="91612-313">Nenhuma exceção é gerada.</span><span class="sxs-lookup"><span data-stu-id="91612-313">No exception is thrown.</span></span>

## <a name="systemcollectionsconcurrent-namespace"></a><span data-ttu-id="91612-314">Namespace System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="91612-314">System.Collections.Concurrent namespace</span></span>

::: zone pivot="dotnet-5-0"

| <span data-ttu-id="91612-315">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-315">Type</span></span>                                                          | <span data-ttu-id="91612-316">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-316">Serialization</span></span> | <span data-ttu-id="91612-317">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-317">Deserialization</span></span> |
|---------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.Concurrent.BlockingCollection%601>   | <span data-ttu-id="91612-318">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-318">✔️</span></span>           | ❌              |
| <xref:System.Collections.Concurrent.ConcurrentBag%601>        | <span data-ttu-id="91612-319">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-319">✔️</span></span>           | ❌              |
| <span data-ttu-id="91612-320"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> \*\*</span><span class="sxs-lookup"><span data-stu-id="91612-320"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> \*\*</span></span> | <span data-ttu-id="91612-321">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-321">✔️</span></span>      | <span data-ttu-id="91612-322">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-322">✔️</span></span>              |
| <xref:System.Collections.Concurrent.ConcurrentQueue%601>      | <span data-ttu-id="91612-323">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-323">✔️</span></span>           | <span data-ttu-id="91612-324">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-324">✔️</span></span>              |
| <span data-ttu-id="91612-325"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-325"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span></span>   | <span data-ttu-id="91612-326">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-326">✔️</span></span>           | <span data-ttu-id="91612-327">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-327">✔️</span></span>              |

::: zone-end

::: zone pivot="dotnet-core-3-1"

| <span data-ttu-id="91612-328">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-328">Type</span></span>                                                        | <span data-ttu-id="91612-329">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-329">Serialization</span></span> | <span data-ttu-id="91612-330">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-330">Deserialization</span></span> |
|-------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.Concurrent.BlockingCollection%601> | <span data-ttu-id="91612-331">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-331">✔️</span></span>           | ❌              |
| <xref:System.Collections.Concurrent.ConcurrentBag%601>      | <span data-ttu-id="91612-332">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-332">✔️</span></span>           | ❌              |
| <span data-ttu-id="91612-333">[ConcurrentDictionary \<string, TValue> ](xref:System.Collections.Concurrent.ConcurrentDictionary%602)\*\*</span><span class="sxs-lookup"><span data-stu-id="91612-333">[ConcurrentDictionary\<string, TValue>](xref:System.Collections.Concurrent.ConcurrentDictionary%602) \*\*</span></span> |<span data-ttu-id="91612-334">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-334">✔️</span></span>|<span data-ttu-id="91612-335">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-335">✔️</span></span>|
| <xref:System.Collections.Concurrent.ConcurrentQueue%601>    | <span data-ttu-id="91612-336">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-336">✔️</span></span>           | <span data-ttu-id="91612-337">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-337">✔️</span></span>              |
| <span data-ttu-id="91612-338"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-338"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span></span> | <span data-ttu-id="91612-339">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-339">✔️</span></span>           | <span data-ttu-id="91612-340">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-340">✔️</span></span>              |

::: zone-end

<span data-ttu-id="91612-341">\*Consulte [dar suporte à viagem de \<T> ida e volta para a pilha](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="91612-341">\* See [Support round trip for Stack\<T>](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span></span>

<span data-ttu-id="91612-342">\*\* Consulte [tipos de chave com suporte](#supported-key-types).</span><span class="sxs-lookup"><span data-stu-id="91612-342">\*\* See [Supported key types](#supported-key-types).</span></span>

## <a name="systemcollectionsobjectmodel-namespace"></a><span data-ttu-id="91612-343">Namespace System.Collections.ObjectModel</span><span class="sxs-lookup"><span data-stu-id="91612-343">System.Collections.ObjectModel namespace</span></span>

::: zone pivot="dotnet-5-0"

| <span data-ttu-id="91612-344">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-344">Type</span></span>                                                           | <span data-ttu-id="91612-345">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-345">Serialization</span></span> | <span data-ttu-id="91612-346">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-346">Deserialization</span></span> |
|----------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.ObjectModel.Collection%601>           | <span data-ttu-id="91612-347">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-347">✔️</span></span>            | <span data-ttu-id="91612-348">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-348">✔️</span></span>             |
| <span data-ttu-id="91612-349">[ \<string, TValue> Chaveid](xref:System.Collections.ObjectModel.KeyedCollection%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-349">[KeyedCollection\<string, TValue>](xref:System.Collections.ObjectModel.KeyedCollection%602) \*</span></span> |<span data-ttu-id="91612-350">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-350">✔️</span></span>|❌|
| <xref:System.Collections.ObjectModel.ObservableCollection%601> | <span data-ttu-id="91612-351">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-351">✔️</span></span>            | <span data-ttu-id="91612-352">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-352">✔️</span></span>             |
| <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>   | <span data-ttu-id="91612-353">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-353">✔️</span></span>            | ❌             |
| <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602>   | <span data-ttu-id="91612-354">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-354">✔️</span></span>            | ❌             |
| <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601> | <span data-ttu-id="91612-355">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-355">✔️</span></span>    | ❌             |

<span data-ttu-id="91612-356">\* Não há `string` suporte para chaves.</span><span class="sxs-lookup"><span data-stu-id="91612-356">\* Non-`string` keys are not supported.</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"

| <span data-ttu-id="91612-357">Tipo</span><span class="sxs-lookup"><span data-stu-id="91612-357">Type</span></span>                                                           | <span data-ttu-id="91612-358">Serialização</span><span class="sxs-lookup"><span data-stu-id="91612-358">Serialization</span></span> | <span data-ttu-id="91612-359">Desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-359">Deserialization</span></span> |
|----------------------------------------------------------------|---------------|-----------------|
| <xref:System.Collections.ObjectModel.Collection%601>           | <span data-ttu-id="91612-360">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-360">✔️</span></span>            | <span data-ttu-id="91612-361">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-361">✔️</span></span>             |
| <span data-ttu-id="91612-362">[ \<string, TValue> Chaveid](xref:System.Collections.ObjectModel.KeyedCollection%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-362">[KeyedCollection\<string, TValue>](xref:System.Collections.ObjectModel.KeyedCollection%602) \*</span></span> |<span data-ttu-id="91612-363">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-363">✔️</span></span>|❌|
| <xref:System.Collections.ObjectModel.ObservableCollection%601> | <span data-ttu-id="91612-364">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-364">✔️</span></span>            | <span data-ttu-id="91612-365">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-365">✔️</span></span>             |
| <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>   | <span data-ttu-id="91612-366">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-366">✔️</span></span>            | ❌             |
| <span data-ttu-id="91612-367">[ReadOnlyDictionary \<string, TValue> ](xref:System.Collections.ObjectModel.ReadOnlyDictionary%602)\*</span><span class="sxs-lookup"><span data-stu-id="91612-367">[ReadOnlyDictionary\<string, TValue>](xref:System.Collections.ObjectModel.ReadOnlyDictionary%602) \*</span></span> |<span data-ttu-id="91612-368">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-368">✔️</span></span>|❌|
| <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601>| <span data-ttu-id="91612-369">✔️</span><span class="sxs-lookup"><span data-stu-id="91612-369">✔️</span></span>     | ❌             |

<span data-ttu-id="91612-370">\* Consulte [tipos de chave com suporte](#supported-key-types).</span><span class="sxs-lookup"><span data-stu-id="91612-370">\* See [Supported key types](#supported-key-types).</span></span>

::: zone-end

## <a name="custom-collections"></a><span data-ttu-id="91612-371">Coleções personalizadas</span><span class="sxs-lookup"><span data-stu-id="91612-371">Custom collections</span></span>

<span data-ttu-id="91612-372">Qualquer tipo de coleção que não esteja em um dos namespaces anteriores é considerado uma coleção personalizada.</span><span class="sxs-lookup"><span data-stu-id="91612-372">Any collection type that isn't in one of the preceding namespaces is considered a custom collection.</span></span> <span data-ttu-id="91612-373">Esses tipos incluem tipos definidos pelo usuário e tipos definidos por ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="91612-373">Such types include user-defined types and types defined by ASP.NET Core.</span></span> <span data-ttu-id="91612-374">Por exemplo, <xref:Microsoft.Extensions.Primitives?displayProperty=fullName> está nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="91612-374">For example, <xref:Microsoft.Extensions.Primitives?displayProperty=fullName> is in this group.</span></span>

<span data-ttu-id="91612-375">Todas as coleções personalizadas (tudo que deriva de `IEnumerable` ) têm suporte para serialização, contanto que seus tipos de elementos tenham suporte.</span><span class="sxs-lookup"><span data-stu-id="91612-375">All custom collections (everything that derives from `IEnumerable`) are supported for serialization, as long as their element types are supported.</span></span>

### <a name="custom-collections-with-deserialization-support"></a><span data-ttu-id="91612-376">Coleções personalizadas com suporte à desserialização</span><span class="sxs-lookup"><span data-stu-id="91612-376">Custom collections with deserialization support</span></span>

<span data-ttu-id="91612-377">Uma coleção personalizada tem suporte para desserialização se:</span><span class="sxs-lookup"><span data-stu-id="91612-377">A custom collection is supported for deserialization if it:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="91612-378">Não é uma interface ou abstrata.</span><span class="sxs-lookup"><span data-stu-id="91612-378">Isn't an interface or abstract.</span></span>
* <span data-ttu-id="91612-379">Tem um construtor sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="91612-379">Has a parameterless constructor.</span></span>
* <span data-ttu-id="91612-380">Contém tipos de elementos que são suportados pelo <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="91612-380">Contains element types that are supported by <xref:System.Text.Json.JsonSerializer>.</span></span>
* <span data-ttu-id="91612-381">Implementa ou herda uma ou mais das seguintes interfaces ou classes:</span><span class="sxs-lookup"><span data-stu-id="91612-381">Implements or inherits one or more of the following interfaces or classes:</span></span>
  * <xref:System.Collections.Concurrent.ConcurrentQueue%601>
  * <span data-ttu-id="91612-382"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-382"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span></span>
  * <xref:System.Collections.Generic.ICollection%601>
  * <xref:System.Collections.IDictionary>
  * <span data-ttu-id="91612-383"><xref:System.Collections.Generic.IDictionary%602> \*\*</span><span class="sxs-lookup"><span data-stu-id="91612-383"><xref:System.Collections.Generic.IDictionary%602> \*\*</span></span>
  * <xref:System.Collections.IList>
  * <xref:System.Collections.Generic.IList%601>
  * <xref:System.Collections.Queue>
  * <xref:System.Collections.Generic.Queue%601>
  * <span data-ttu-id="91612-384"><xref:System.Collections.Stack> \*</span><span class="sxs-lookup"><span data-stu-id="91612-384"><xref:System.Collections.Stack> \*</span></span>
  * <span data-ttu-id="91612-385"><xref:System.Collections.Generic.Stack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-385"><xref:System.Collections.Generic.Stack%601> \*</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="91612-386">Não é uma interface ou abstrata.</span><span class="sxs-lookup"><span data-stu-id="91612-386">Isn't an interface or abstract.</span></span>
* <span data-ttu-id="91612-387">Tem um construtor sem parâmetros.</span><span class="sxs-lookup"><span data-stu-id="91612-387">Has a parameterless constructor.</span></span>
* <span data-ttu-id="91612-388">Contém tipos de elementos que são suportados pelo <xref:System.Text.Json.JsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="91612-388">Contains element types that are supported by <xref:System.Text.Json.JsonSerializer>.</span></span>
* <span data-ttu-id="91612-389">Implementa ou herda uma ou mais das seguintes interfaces ou classes:</span><span class="sxs-lookup"><span data-stu-id="91612-389">Implements or inherits one or more of the following interfaces or classes:</span></span>
  * <xref:System.Collections.Concurrent.ConcurrentQueue%601>
  * <span data-ttu-id="91612-390"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-390"><xref:System.Collections.Concurrent.ConcurrentStack%601> \*</span></span>
  * <xref:System.Collections.Generic.ICollection%601>
  * <xref:System.Collections.IDictionary>
  * <span data-ttu-id="91612-391">[IDictionary\<string, TValue>](xref:System.Collections.Generic.IDictionary%602) \* \*</span><span class="sxs-lookup"><span data-stu-id="91612-391">[IDictionary\<string, TValue>](xref:System.Collections.Generic.IDictionary%602) \*\*</span></span>
  * <xref:System.Collections.IList>
  * <xref:System.Collections.Generic.IList%601>
  * <xref:System.Collections.Queue>
  * <xref:System.Collections.Generic.Queue%601>
  * <span data-ttu-id="91612-392"><xref:System.Collections.Stack> \*</span><span class="sxs-lookup"><span data-stu-id="91612-392"><xref:System.Collections.Stack> \*</span></span>
  * <span data-ttu-id="91612-393"><xref:System.Collections.Generic.Stack%601> \*</span><span class="sxs-lookup"><span data-stu-id="91612-393"><xref:System.Collections.Generic.Stack%601> \*</span></span>

::: zone-end

  <span data-ttu-id="91612-394">\*Consulte [dar suporte à viagem de \<T> ida e volta para a pilha](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="91612-394">\* See [Support round trip for Stack\<T>](system-text-json-converters-how-to.md#support-round-trip-for-stackt).</span></span>

  <span data-ttu-id="91612-395">\*\* Consulte [tipos de chave com suporte](#supported-key-types).</span><span class="sxs-lookup"><span data-stu-id="91612-395">\*\* See [Supported key types](#supported-key-types).</span></span>

### <a name="custom-collections-with-known-issues"></a><span data-ttu-id="91612-396">Coleções personalizadas com problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="91612-396">Custom collections with known issues</span></span>

<span data-ttu-id="91612-397">Há problemas conhecidos com as seguintes coleções personalizadas:</span><span class="sxs-lookup"><span data-stu-id="91612-397">There are known issues with the following custom collections:</span></span>

- <span data-ttu-id="91612-398"><xref:System.Dynamic.ExpandoObject>: Consulte [dotnet/tempo de execução # 29690](https://github.com/dotnet/runtime/issues/29690).</span><span class="sxs-lookup"><span data-stu-id="91612-398"><xref:System.Dynamic.ExpandoObject>: See [dotnet/runtime#29690](https://github.com/dotnet/runtime/issues/29690).</span></span>
- <span data-ttu-id="91612-399"><xref:System.Dynamic.DynamicObject>: Consulte [dotnet/tempo de execução # 1808](https://github.com/dotnet/runtime/issues/1808).</span><span class="sxs-lookup"><span data-stu-id="91612-399"><xref:System.Dynamic.DynamicObject>: See [dotnet/runtime#1808](https://github.com/dotnet/runtime/issues/1808).</span></span>
- <span data-ttu-id="91612-400"><xref:System.Data.DataTable>: Consulte [dotnet/docs # 21366](https://github.com/dotnet/docs/issues/21366).</span><span class="sxs-lookup"><span data-stu-id="91612-400"><xref:System.Data.DataTable>: See [dotnet/docs#21366](https://github.com/dotnet/docs/issues/21366).</span></span>
- <span data-ttu-id="91612-401"><xref:Microsoft.AspNetCore.Http.FormFile?displayProperty=fullName>: Consulte [dotnet/tempo de execução # 1559](https://github.com/dotnet/runtime/issues/1559).</span><span class="sxs-lookup"><span data-stu-id="91612-401"><xref:Microsoft.AspNetCore.Http.FormFile?displayProperty=fullName>: See [dotnet/runtime#1559](https://github.com/dotnet/runtime/issues/1559).</span></span>
- <span data-ttu-id="91612-402"><xref:Microsoft.AspNetCore.Http.IFormCollection?displayProperty=fullName>: Consulte [dotnet/tempo de execução # 1559](https://github.com/dotnet/runtime/issues/1559).</span><span class="sxs-lookup"><span data-stu-id="91612-402"><xref:Microsoft.AspNetCore.Http.IFormCollection?displayProperty=fullName>: See [dotnet/runtime#1559](https://github.com/dotnet/runtime/issues/1559).</span></span>

<span data-ttu-id="91612-403">Para obter mais informações sobre problemas conhecidos, consulte os [problemas em System.Text.Json aberto em ](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json).</span><span class="sxs-lookup"><span data-stu-id="91612-403">For more information about known issues, see the [open issues in System.Text.Json](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json).</span></span>

## <a name="supported-key-types"></a><span data-ttu-id="91612-404">Tipos de chave com suporte</span><span class="sxs-lookup"><span data-stu-id="91612-404">Supported key types</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="91612-405">Os tipos com suporte para as chaves de `Dictionary` e `SortedList` tipos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="91612-405">Supported types for the keys of `Dictionary` and `SortedList` types include the following:</span></span>

* `Boolean`
* `Byte`
* `DateTime`
* `DateTimeOffset`
* `Decimal`
* `Double`
* `Enum`
* `Guid`
* `Int16`
* `Int32`
* `Int64`
* <span data-ttu-id="91612-406">`Object` (Somente na serialização e se o tipo de tempo de execução for um dos tipos com suporte nesta lista.)</span><span class="sxs-lookup"><span data-stu-id="91612-406">`Object` (Only on serialization and if the runtime type is one of the supported types in this list.)</span></span>
* `SByte`
* `Single`
* `String`
* `UInt16`
* `UInt32`
* `UInt64`

::: zone-end

::: zone pivot="dotnet-core-3-1"

<span data-ttu-id="91612-407">\*\* Não `string` há suporte para os tipos e não-chaves `Dictionary` `SortedList` no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="91612-407">\*\* Non-`string` keys for `Dictionary` and `SortedList` types are not supported in .NET Core 3.1.</span></span>

::: zone-end

## <a name="see-also"></a><span data-ttu-id="91612-408">Veja também</span><span class="sxs-lookup"><span data-stu-id="91612-408">See also</span></span>

* [<span data-ttu-id="91612-409">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="91612-409">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="91612-410">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="91612-410">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="91612-411">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="91612-411">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="91612-412">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="91612-412">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="91612-413">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="91612-413">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="91612-414">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="91612-414">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="91612-415">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="91612-415">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="91612-416">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="91612-416">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="91612-417">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="91612-417">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="91612-418">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="91612-418">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="91612-419">Migrar do Newtonsoft.Jspara o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="91612-419">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="91612-420">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="91612-420">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="91612-421">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="91612-421">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="91612-422">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="91612-422">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="91612-423">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="91612-423">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="91612-424">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="91612-424">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="91612-425">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="91612-425">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
