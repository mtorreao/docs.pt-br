---
title: Rastreamento
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 10b9be028710cdda378aeef0ca235a00aa451e08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243905"
---
# <a name="tracing"></a><span data-ttu-id="962dc-102">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="962dc-102">Tracing</span></span>

<span data-ttu-id="962dc-103">O Windows Communication Foundation (WCF) fornece dados de diagnóstico e instrumentação de aplicativos para monitoramento e análise de falhas.</span><span class="sxs-lookup"><span data-stu-id="962dc-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="962dc-104">Você pode usar o rastreamento em vez de um depurador para entender como um aplicativo está se comportando, ou por que ele falha.</span><span class="sxs-lookup"><span data-stu-id="962dc-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="962dc-105">Você também pode correlacionar as falhas e o processamento entre os componentes para fornecer uma experiência de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="962dc-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="962dc-106">O WCF gera os seguintes dados para o rastreamento de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="962dc-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
- <span data-ttu-id="962dc-107">Rastreamentos de etapas de processo em todos os componentes dos aplicativos, como chamadas de operação, exceções de código, avisos e outros eventos de processamento significativos. "</span><span class="sxs-lookup"><span data-stu-id="962dc-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
- <span data-ttu-id="962dc-108">Eventos de erro do Windows quando o recurso de rastreamento não funciona.</span><span class="sxs-lookup"><span data-stu-id="962dc-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="962dc-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="962dc-109">In This Section</span></span>  

 [<span data-ttu-id="962dc-110">Configurando o rastreamento</span><span class="sxs-lookup"><span data-stu-id="962dc-110">Configuring Tracing</span></span>](configuring-tracing.md)  
  
 <span data-ttu-id="962dc-111">Este tópico descreve como você pode configurar o rastreamento em diferentes níveis para se adequar à sua necessidade específica.</span><span class="sxs-lookup"><span data-stu-id="962dc-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="962dc-112">Rastreamento ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="962dc-112">End-to-End Tracing</span></span>](end-to-end-tracing.md)  
  
 <span data-ttu-id="962dc-113">Esta seção descreve como você pode usar o rastreamento de atividade e a propagação para correlação de ponta a ponta para auxiliar na depuração.</span><span class="sxs-lookup"><span data-stu-id="962dc-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="962dc-114">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="962dc-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="962dc-115">Esta seção descreve como você pode usar o rastreamento para depurar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="962dc-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="962dc-116">Preocupações de segurança e dicas úteis para rastreamento</span><span class="sxs-lookup"><span data-stu-id="962dc-116">Security Concerns and Useful Tips for Tracing</span></span>](security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="962dc-117">Este tópico descreve como você pode proteger informações confidenciais de serem expostas, bem como dicas úteis ao usar o webhost.</span><span class="sxs-lookup"><span data-stu-id="962dc-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="962dc-118">Referência de rastreamentos</span><span class="sxs-lookup"><span data-stu-id="962dc-118">Traces Reference</span></span>](traces-reference.md)  
  
 <span data-ttu-id="962dc-119">Este tópico lista todos os rastreamentos gerados pelo WCF.</span><span class="sxs-lookup"><span data-stu-id="962dc-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962dc-120">Veja também</span><span class="sxs-lookup"><span data-stu-id="962dc-120">See also</span></span>

- [<span data-ttu-id="962dc-121">Ferramenta Visualizador de Rastreamento de Serviço (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="962dc-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
