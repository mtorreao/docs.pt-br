---
title: Rastreamento analítico com ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4bb31eeac7c5d3c8c30f66090b07de9f8af4d5a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274615"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="f555f-102">Rastreamento analítico com ETW</span><span class="sxs-lookup"><span data-stu-id="f555f-102">Analytic Tracing with ETW</span></span>

<span data-ttu-id="f555f-103">O rastreamento analítico do Windows Communication Foundation (WCF) oferece uma maneira de capturar informações de diagnóstico durante a execução de um serviço WCF.</span><span class="sxs-lookup"><span data-stu-id="f555f-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="f555f-104">Os eventos de rastreamento analítico do WCF são emitidos em pontos-chave na pilha do WCF para permitir a solução de problemas de serviços WCF em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="f555f-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="f555f-105">O rastreamento analítico para serviços WCF tem um impacto mínimo sobre o desempenho de um servidor de produtos que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] Serviços WCF, pois esses eventos são emitidos com muita eficiência para uma sessão do ETW (rastreamento de eventos para Windows).</span><span class="sxs-lookup"><span data-stu-id="f555f-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f555f-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f555f-106">In This Section</span></span>  

 [<span data-ttu-id="f555f-107">Visão geral de rastreamento analítico</span><span class="sxs-lookup"><span data-stu-id="f555f-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="f555f-108">Discute como o rastreamento analítico do WCF funciona no [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f555f-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="f555f-109">Rastreamento analítico habilitado dinamicamente</span><span class="sxs-lookup"><span data-stu-id="f555f-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="f555f-110">Discute como habilitar ou desabilitar o rastreamento dinamicamente usando o ETW.</span><span class="sxs-lookup"><span data-stu-id="f555f-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="f555f-111">Configurando rastreamento de fluxo de mensagem</span><span class="sxs-lookup"><span data-stu-id="f555f-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="f555f-112">Descreve como configurar o rastreamento de fluxo de mensagens.</span><span class="sxs-lookup"><span data-stu-id="f555f-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="f555f-113">Referência de evento de rastreamento analítico</span><span class="sxs-lookup"><span data-stu-id="f555f-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="f555f-114">Mostra uma tabela de IDs de evento com seus níveis de evento, mensagens de evento e palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="f555f-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f555f-115">Veja também</span><span class="sxs-lookup"><span data-stu-id="f555f-115">See also</span></span>

- [<span data-ttu-id="f555f-116">Serviços e rastreamento de eventos WCF para Windows</span><span class="sxs-lookup"><span data-stu-id="f555f-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="f555f-117">Eventos de rastreamento no rastreamento de evento no Windows</span><span class="sxs-lookup"><span data-stu-id="f555f-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
