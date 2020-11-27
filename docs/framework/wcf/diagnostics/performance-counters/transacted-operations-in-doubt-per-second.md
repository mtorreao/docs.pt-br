---
title: Operações Transacionadas em Dúvida por Segundo
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: 9162809ec467f282674e0ab21f7ce5e4d2222da4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249976"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="aec89-102">Operações Transacionadas em Dúvida por Segundo</span><span class="sxs-lookup"><span data-stu-id="aec89-102">Transacted Operations In Doubt Per Second</span></span>

<span data-ttu-id="aec89-103">Nome do contador: operações transacionadas em dúvida por segundo.</span><span class="sxs-lookup"><span data-stu-id="aec89-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="aec89-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="aec89-104">Description</span></span>  

 <span data-ttu-id="aec89-105">Número de operações transacionais com um resultado incerto nesse serviço em um segundo.</span><span class="sxs-lookup"><span data-stu-id="aec89-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="aec89-106">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="aec89-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="aec89-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="aec89-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
