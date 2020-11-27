---
title: Chamadas com falha por segundo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285454"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="7352c-102">Chamadas com falha por segundo</span><span class="sxs-lookup"><span data-stu-id="7352c-102">Calls Failed Per Second</span></span>

<span data-ttu-id="7352c-103">Nome do contador: chamadas com falha por segundo</span><span class="sxs-lookup"><span data-stu-id="7352c-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="7352c-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="7352c-104">Description</span></span>  

 <span data-ttu-id="7352c-105">Número de chamadas com exceções sem tratamento nesta operação em um segundo.</span><span class="sxs-lookup"><span data-stu-id="7352c-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="7352c-106">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="7352c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7352c-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="7352c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="7352c-108">Esse contador é incrementado toda vez que há uma exceção sem tratamento nesta operação.</span><span class="sxs-lookup"><span data-stu-id="7352c-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7352c-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="7352c-109">See also</span></span>

- [<span data-ttu-id="7352c-110">Especificando e lidando com falhas em contratos e serviços</span><span class="sxs-lookup"><span data-stu-id="7352c-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
