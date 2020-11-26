---
title: 'Serviço: chamadas de segurança não autorizadas por segundo'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: db9e333f740f19e4f82ea0f1306a11e6c21ba996
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236917"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="5cda4-102">Serviço: chamadas de segurança não autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5cda4-102">Service: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="5cda4-103">Nome do contador: chamadas de segurança não autorizadas por segundo</span><span class="sxs-lookup"><span data-stu-id="5cda4-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5cda4-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="5cda4-104">Description</span></span>  

 <span data-ttu-id="5cda4-105">Número de mensagens de entrada em um segundo, que são de um usuário válido e protegidas corretamente, mas o usuário não está autorizado a realizar tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="5cda4-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="5cda4-106">Esse contador é incrementado quando o <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> método retorna `false` .</span><span class="sxs-lookup"><span data-stu-id="5cda4-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="5cda4-107">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir.</span><span class="sxs-lookup"><span data-stu-id="5cda4-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5cda4-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="5cda4-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
