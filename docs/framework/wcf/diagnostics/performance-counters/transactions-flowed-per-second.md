---
title: Fluxo de transações por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254136"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="c449e-102">Fluxo de transações por segundo</span><span class="sxs-lookup"><span data-stu-id="c449e-102">Transactions Flowed Per Second</span></span>

<span data-ttu-id="c449e-103">Nome do contador: transações fluidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c449e-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c449e-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="c449e-104">Description</span></span>  

 <span data-ttu-id="c449e-105">Número de transações fluidas para esta operação em um segundo.</span><span class="sxs-lookup"><span data-stu-id="c449e-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="c449e-106">Esse contador é incrementado sempre que uma ID de transação está presente em uma mensagem que é enviada para a operação.</span><span class="sxs-lookup"><span data-stu-id="c449e-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="c449e-107">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="c449e-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c449e-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="c449e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
