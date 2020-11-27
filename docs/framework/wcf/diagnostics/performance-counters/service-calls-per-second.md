---
title: 'Serviço: chamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 7e702d402909c4a85a2cb42c837e0813c4d9f841
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252875"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="280ed-102">Serviço: chamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="280ed-102">Service: Calls Per Second</span></span>

<span data-ttu-id="280ed-103">Nome do contador: chamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="280ed-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="280ed-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="280ed-104">Description</span></span>  

 <span data-ttu-id="280ed-105">Número de chamadas para esse serviço em um segundo.</span><span class="sxs-lookup"><span data-stu-id="280ed-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="280ed-106">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="280ed-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="280ed-107">(N 1-N 0)/((D 1-D 0)/F) em que o numerador (N) representa o número de operações executadas durante o último intervalo de amostragem, o denominador (D) representa o número de tiques decorridos durante o último intervalo de amostragem e F é a frequência das tiques.</span><span class="sxs-lookup"><span data-stu-id="280ed-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
