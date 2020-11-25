---
title: Como usar SpinWait para implementar uma operação bifásica de espera
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: e5d58067f70706294308952b9f7cfbf69fa89a58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728479"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="961f9-102">Como usar SpinWait para implementar uma operação bifásica de espera</span><span class="sxs-lookup"><span data-stu-id="961f9-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>

<span data-ttu-id="961f9-103">O exemplo a seguir mostra como usar um objeto <xref:System.Threading.SpinWait?displayProperty=nameWithType> para implementar uma operação de espera de duas fases.</span><span class="sxs-lookup"><span data-stu-id="961f9-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="961f9-104">Na primeira fase, o objeto de sincronização, um `Latch`, gira por alguns ciclos enquanto verifica se o bloqueio ficou disponível.</span><span class="sxs-lookup"><span data-stu-id="961f9-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="961f9-105">Na segunda fase, se o bloqueio ficar disponível, o método `Wait` retorna sem usar <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para executar sua espera; caso contrário, `Wait` executa a espera.</span><span class="sxs-lookup"><span data-stu-id="961f9-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="961f9-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="961f9-106">Example</span></span>  

 <span data-ttu-id="961f9-107">Este exemplo mostra uma implementação muito básica de uma primitivo de sincronização de Trava.</span><span class="sxs-lookup"><span data-stu-id="961f9-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="961f9-108">Você pode usar essa estrutura de dados quando houver a expectativa de tempos de espera muito curtos.</span><span class="sxs-lookup"><span data-stu-id="961f9-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="961f9-109">Este exemplo é para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="961f9-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="961f9-110">Se você precisar de funcionalidade do tipo trava em seu programa, considere o uso de <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="961f9-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="961f9-111">A trava usa o objeto <xref:System.Threading.SpinWait> para executar somente no local até que a próxima chamada a `SpinOnce` faça com que <xref:System.Threading.SpinWait> gere a fração de tempo do thread.</span><span class="sxs-lookup"><span data-stu-id="961f9-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="961f9-112">Nesse ponto, a trava causa sua própria alternância de contexto chamando <xref:System.Threading.WaitHandle.WaitOne%2A> no <xref:System.Threading.ManualResetEvent>, e passando o restante do valor de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="961f9-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="961f9-113">A saída do log mostra com que frequência a trava conseguiu aumentar o desempenho adquirindo o bloqueio sem usar o <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="961f9-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961f9-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="961f9-114">See also</span></span>

- [<span data-ttu-id="961f9-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="961f9-115">SpinWait</span></span>](spinwait.md)
- [<span data-ttu-id="961f9-116">Threading de objetos e recursos</span><span class="sxs-lookup"><span data-stu-id="961f9-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)
