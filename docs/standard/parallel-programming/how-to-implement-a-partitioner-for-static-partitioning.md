---
title: 'Como: implementar um particionador para particionamento estático'
ms.date: 03/30/2017
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 1593f1bc3c17f162b20f8bd9f645d51393f2198c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817126"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="0a272-102">Como: implementar um particionador para particionamento estático</span><span class="sxs-lookup"><span data-stu-id="0a272-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="0a272-103">O exemplo a seguir mostra uma maneira de implementar um particionador personalizado simples para PLINQ que executa o particionamento estático.</span><span class="sxs-lookup"><span data-stu-id="0a272-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="0a272-104">Como o particionador não oferece suporte a partições dinâmicas, não é consumido de <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a272-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0a272-105">Esse particionador específico pode fornecer a agilização sobre o particionador de intervalo padrão para fontes de dados para as quais cada elemento requer um volume crescente de tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="0a272-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a272-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0a272-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="0a272-107">As partições neste exemplo baseiam-se na suposição de um aumento linear no tempo de processamento para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="0a272-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="0a272-108">No mundo real, pode ser difícil de prever os tempos de processamento dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="0a272-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="0a272-109">Se você estiver usando um particionador estático com uma fonte de dados específica, poderá otimizar a fórmula de particionamento para a fonte, adicionar lógica de balanceamento de carga ou usar uma abordagem de particionamento de parte, conforme demonstrado em [Como implementar as partições dinâmicas](how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="0a272-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a272-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="0a272-110">See also</span></span>

- [<span data-ttu-id="0a272-111">Particionadores personalizados para PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="0a272-111">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
