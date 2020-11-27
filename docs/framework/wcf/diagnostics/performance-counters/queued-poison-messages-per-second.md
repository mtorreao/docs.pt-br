---
title: Mensagens suspeitas na fila por segundo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276224"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="5db0e-102">Mensagens suspeitas na fila por segundo</span><span class="sxs-lookup"><span data-stu-id="5db0e-102">Queued Poison Messages Per Second</span></span>

<span data-ttu-id="5db0e-103">Nome do contador: mensagens suspeitas enfileiradas por segundo.</span><span class="sxs-lookup"><span data-stu-id="5db0e-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5db0e-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="5db0e-104">Description</span></span>  

 <span data-ttu-id="5db0e-105">Número de mensagens marcadas como inviabilizada pelo transporte em fila neste serviço em um segundo.</span><span class="sxs-lookup"><span data-stu-id="5db0e-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="5db0e-106">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="5db0e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5db0e-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="5db0e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
