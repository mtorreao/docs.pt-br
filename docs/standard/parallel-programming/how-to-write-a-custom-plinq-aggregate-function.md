---
title: 'Como: Escrever uma função de agregação PLINQ personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
ms.openlocfilehash: d04f90e9c763c8ddba5ba07b650ffb878869ff3a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825462"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="42ac3-102">Como: Escrever uma função de agregação PLINQ personalizada</span><span class="sxs-lookup"><span data-stu-id="42ac3-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="42ac3-103">Este exemplo mostra como usar o método <xref:System.Linq.ParallelEnumerable.Aggregate%2A> para aplicar uma função de agregação personalizada a uma sequência de origem.</span><span class="sxs-lookup"><span data-stu-id="42ac3-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="42ac3-104">Este exemplo tem como objetivo demonstrar o uso e pode não executar tão rápido quanto a consulta LINQ to Objects sequencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="42ac3-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="42ac3-105">Para saber mais sobre agilização, confira [Noções básicas sobre agilização no PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="42ac3-105">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42ac3-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="42ac3-106">Example</span></span>  
 <span data-ttu-id="42ac3-107">O exemplo a seguir calcula o desvio padrão de uma sequência de números inteiros.</span><span class="sxs-lookup"><span data-stu-id="42ac3-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="42ac3-108">Este exemplo usa uma sobrecarga do operador de consulta padrão de agregação que é exclusivo ao PLINQ.</span><span class="sxs-lookup"><span data-stu-id="42ac3-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="42ac3-109">Essa sobrecarga usa um <xref:System.Func%603?displayProperty=nameWithType> adicional como o terceiro parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="42ac3-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="42ac3-110">Este delegado combina os resultados de todos os threads antes de executar o cálculo final nos resultados agregados.</span><span class="sxs-lookup"><span data-stu-id="42ac3-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="42ac3-111">Neste exemplo, somamos todos os threads.</span><span class="sxs-lookup"><span data-stu-id="42ac3-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="42ac3-112">Observe que quando um corpo da expressão lambda é composto por uma única expressão, o valor de retorno do delegado <xref:System.Func%602?displayProperty=nameWithType> é o valor da expressão.</span><span class="sxs-lookup"><span data-stu-id="42ac3-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ac3-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="42ac3-113">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="42ac3-114">LINQ paralelo (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="42ac3-114">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
