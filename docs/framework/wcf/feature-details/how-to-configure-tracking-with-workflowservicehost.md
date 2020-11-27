---
title: 'Como: configurar o acompanhamento com WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: cf30ace90f86e282d72c4da5f2c3707905360aeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257347"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="a2bb5-102">Como: configurar o acompanhamento com WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="a2bb5-102">How to: Configure Tracking with WorkflowServiceHost</span></span>

<span data-ttu-id="a2bb5-103">Este tópico explica como configurar o acompanhamento de um [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] fluxo de trabalho hospedado no <xref:System.ServiceModel.Activities.WorkflowServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="a2bb5-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a2bb5-104">Ele é configurado por meio de um arquivo de Web.config especificando um comportamento de serviço.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="a2bb5-105">Configurar o controle na configuração</span><span class="sxs-lookup"><span data-stu-id="a2bb5-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="a2bb5-106">Adicione o <xref:System.Activities.Tracking.EtwTrackingParticipant> usando o `behavior` elemento <> em um arquivo de configuração, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a2bb5-107">O exemplo de configuração anterior está usando uma configuração simplificada.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="a2bb5-108">Para obter mais informações, consulte [configuração simplificada](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb5-108">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="a2bb5-109">O exemplo de configuração anterior adiciona um <xref:System.Activities.Tracking.EtwTrackingParticipant> e especifica um nome de perfil de controle.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="a2bb5-110">Os perfis de rastreamento são criados em um `trackingProfile` elemento <> dentro de um `tracking` elemento> <.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="a2bb5-111">O perfil de controle contém consultas de acompanhamento que permitem que um participante de controle assine eventos de fluxo de trabalho emitidos quando o estado de uma instância de fluxo de trabalho é alterado no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a2bb5-112">O exemplo a seguir mostra como criar um perfil de controle.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-112">The following example shows how to create a tracking profile.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <tracking>
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>
       </tracking>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="a2bb5-113">Para obter mais informações sobre perfis de rastreamento, consulte [perfis de rastreamento](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb5-113">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="a2bb5-114">Para obter mais informações sobre o rastreamento em geral, consulte rastreamento [e acompanhamento de fluxo de trabalho](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb5-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="a2bb5-115">Configurar o acompanhamento no código</span><span class="sxs-lookup"><span data-stu-id="a2bb5-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="a2bb5-116">Adicione o <xref:System.Activities.Tracking.EtwTrackingParticipant> usando o <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> comportamento no código, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="a2bb5-117">O exemplo de código anterior adiciona um <xref:System.Activities.Tracking.EtwTrackingParticipant> e especifica um nome de perfil de controle.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="a2bb5-118">Os perfis de rastreamento são criados em um `trackingProfile` elemento <> dentro de um `tracking` elemento <>, conforme mostrado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="a2bb5-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="a2bb5-119">Para obter mais informações sobre perfis de rastreamento, consulte [perfis de rastreamento](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb5-119">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="a2bb5-120">Para obter mais informações sobre o rastreamento em geral, consulte rastreamento [e acompanhamento de fluxo de trabalho](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="a2bb5-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="a2bb5-121">Para obter um exemplo de como configurar o acompanhamento programaticamente, consulte [Configurando o acompanhamento de um fluxo](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a2bb5-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2bb5-122">Veja também</span><span class="sxs-lookup"><span data-stu-id="a2bb5-122">See also</span></span>

- [<span data-ttu-id="a2bb5-123">Configuração simplificada para serviços do WCF</span><span class="sxs-lookup"><span data-stu-id="a2bb5-123">Simplified Configuration for WCF Services</span></span>](../samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="a2bb5-124">Serviços de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a2bb5-124">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="a2bb5-125">Controlando perfis</span><span class="sxs-lookup"><span data-stu-id="a2bb5-125">Tracking Profiles</span></span>](../../windows-workflow-foundation/tracking-profiles.md)
