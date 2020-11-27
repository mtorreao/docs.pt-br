---
title: Contadores de desempenho de serviço
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: f3e3a798bf04f24aaea03b5d70762d52b67a82f0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252823"
---
# <a name="service-performance-counters"></a><span data-ttu-id="18b0f-102">Contadores de desempenho de serviço</span><span class="sxs-lookup"><span data-stu-id="18b0f-102">Service Performance Counters</span></span>

<span data-ttu-id="18b0f-103">Os contadores de desempenho de serviço medem o comportamento do serviço como um todo e podem ser usados para diagnosticar o desempenho do serviço inteiro.</span><span class="sxs-lookup"><span data-stu-id="18b0f-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="18b0f-104">Eles podem ser encontrados no `ServiceModelService 4.0.0.0` objeto de desempenho ao exibir com o monitor de desempenho (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="18b0f-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="18b0f-105">As instâncias são nomeadas usando o seguinte padrão:</span><span class="sxs-lookup"><span data-stu-id="18b0f-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="18b0f-106">Há um limite no comprimento do nome de uma instância do contador de desempenho.</span><span class="sxs-lookup"><span data-stu-id="18b0f-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="18b0f-107">Quando um nome de instância de contador de Windows Communication Foundation (WCF) excede o comprimento máximo, o WCF substitui uma parte do nome da instância por um valor de hash.</span><span class="sxs-lookup"><span data-stu-id="18b0f-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b0f-108">Veja também</span><span class="sxs-lookup"><span data-stu-id="18b0f-108">See also</span></span>

- [<span data-ttu-id="18b0f-109">Contadores de desempenho</span><span class="sxs-lookup"><span data-stu-id="18b0f-109">Performance Counters</span></span>](index.md)
