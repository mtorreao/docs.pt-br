---
title: 'Ponto de extremidade: fluxo de transações por segundo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: b814d7ca9e286426289c611b3a6bf5a52c1b2335
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256424"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="1ec7a-102">Ponto de extremidade: fluxo de transações por segundo</span><span class="sxs-lookup"><span data-stu-id="1ec7a-102">Endpoint: Transactions Flowed Per Second</span></span>

<span data-ttu-id="1ec7a-103">Nome do contador: transações fluidas por segundo.</span><span class="sxs-lookup"><span data-stu-id="1ec7a-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1ec7a-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ec7a-104">Description</span></span>  

 <span data-ttu-id="1ec7a-105">Número de transações fluidas para operações neste ponto de extremidade em um segundo.</span><span class="sxs-lookup"><span data-stu-id="1ec7a-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="1ec7a-106">Esse contador é incrementado sempre que uma ID de transação está presente em uma mensagem enviada ao ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="1ec7a-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="1ec7a-107">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ec7a-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1ec7a-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="1ec7a-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
