---
title: Visão geral de serviços de fluxo de trabalho de hospedagem
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 150cb98ab3cef8231489219a16709344cbd19bd5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242962"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="1e430-102">Visão geral de serviços de fluxo de trabalho de hospedagem</span><span class="sxs-lookup"><span data-stu-id="1e430-102">Hosting Workflow Services Overview</span></span>

<span data-ttu-id="1e430-103">Os serviços de fluxo de trabalho devem ser hospedados para execução.</span><span class="sxs-lookup"><span data-stu-id="1e430-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="1e430-104">O <xref:System.ServiceModel.WorkflowServiceHost> é o host de fluxo de trabalho pronto para uso que dá suporte a várias instâncias, configurações e mensagens do WCF (embora os fluxos de trabalho não sejam obrigados a usar o sistema de mensagens para serem hospedados).</span><span class="sxs-lookup"><span data-stu-id="1e430-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="1e430-105">Ele também se integra com persistência, controle e controle de instância por meio de um conjunto de comportamentos de serviço.</span><span class="sxs-lookup"><span data-stu-id="1e430-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="1e430-106">Assim como o WCF <xref:System.ServiceModel.ServiceHost> , o <xref:System.ServiceModel.WorkflowServiceHost> pode ser hospedado internamente em qualquer aplicativo .net gerenciado ou hospedado na Web (como um arquivo. xamlx) no IIS/WAS.</span><span class="sxs-lookup"><span data-stu-id="1e430-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="1e430-107">Os tópicos nesta seção descrevem como hospedar um serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e430-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e430-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1e430-108">In This Section</span></span>  

 [<span data-ttu-id="1e430-109">Serviços de fluxo de trabalho de hospedagem</span><span class="sxs-lookup"><span data-stu-id="1e430-109">Hosting Workflow Services</span></span>](hosting-workflow-services.md)  
 <span data-ttu-id="1e430-110">Descreve os serviços de fluxo de trabalho de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="1e430-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="1e430-111">Internos do host de serviço de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1e430-111">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)  
 <span data-ttu-id="1e430-112">Descreve como o <xref:System.ServiceModel.WorkflowServiceHost> processa as mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="1e430-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="1e430-113">Extensibilidade de host de serviço do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1e430-113">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)  
 <span data-ttu-id="1e430-114">Descreve como estender a funcionalidade do host do serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e430-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="1e430-115">Ponto de extremidade de controle de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1e430-115">Workflow Control Endpoint</span></span>](workflow-control-endpoint.md)  
 <span data-ttu-id="1e430-116">Descreve como definir um ponto de extremidade que permite criar instâncias de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e430-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="1e430-117">Como: hospedar um serviço de fluxo de trabalho com o Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="1e430-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="1e430-118">Demonstra como hospedar um serviço de fluxo de trabalho existente no Windows Server app Fabric.</span><span class="sxs-lookup"><span data-stu-id="1e430-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="1e430-119">Configurando WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="1e430-119">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)  
 <span data-ttu-id="1e430-120">Descreve como controlar persistência, controle, ociosidade e comportamento de exceção sem tratamento.</span><span class="sxs-lookup"><span data-stu-id="1e430-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1e430-121">Referência</span><span class="sxs-lookup"><span data-stu-id="1e430-121">Reference</span></span>  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="1e430-122">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="1e430-122">Related Sections</span></span>  

 [<span data-ttu-id="1e430-123">Serviços de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1e430-123">Workflow Services</span></span>](workflow-services.md)
