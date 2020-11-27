---
title: 'Ponto de extremidade: mensagens confiáveis do sistema de mensagens descartadas por segundo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: b8c0f91b2de5d023232756159a50236574308954
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290836"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="84e6c-102">Ponto de extremidade: mensagens confiáveis do sistema de mensagens descartadas por segundo</span><span class="sxs-lookup"><span data-stu-id="84e6c-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>

<span data-ttu-id="84e6c-103">Nome do contador: sessões de mensagens confiáveis eliminadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="84e6c-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="84e6c-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="84e6c-104">Description</span></span>  

 <span data-ttu-id="84e6c-105">Número total de mensagens de mensagens confiáveis que foram descartadas neste ponto de extremidade em um segundo.</span><span class="sxs-lookup"><span data-stu-id="84e6c-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="84e6c-106">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="84e6c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="84e6c-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="84e6c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
