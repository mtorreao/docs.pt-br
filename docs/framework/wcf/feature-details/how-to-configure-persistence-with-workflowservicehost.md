---
title: 'Como: configurar a persistência com WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 3d8b7183b11c138b8da1f04d9084f8b94b7dcaa6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257334"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="50621-102">Como: configurar a persistência com WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="50621-102">How to: Configure Persistence with WorkflowServiceHost</span></span>

<span data-ttu-id="50621-103">Este tópico descreve como configurar o recurso de repositório de instância do fluxo de trabalho SQL para habilitar a persistência para fluxos de trabalho hospedados no <xref:System.ServiceModel.Activities.WorkflowServiceHost> usando um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="50621-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="50621-104">Antes de usar o recurso de repositório de instância do fluxo de trabalho SQL, você deve criar um banco de dados SQL que é usado para manter instâncias de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="50621-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="50621-105">Para obter mais informações, consulte [como habilitar a persistência de SQL para fluxos de trabalho e serviços de fluxo de trabalho](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="50621-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="50621-106">Para configurar o repositório de instância do fluxo de trabalho SQL na configuração</span><span class="sxs-lookup"><span data-stu-id="50621-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="50621-107">As propriedades do armazenamento da instância do fluxo de trabalho SQL podem ser configuradas por meio do <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> , um comportamento de serviço que permite alterar as configurações por meio da configuração de XML.</span><span class="sxs-lookup"><span data-stu-id="50621-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="50621-108">O exemplo de configuração a seguir mostra como configurar o armazenamento de instância de fluxo de trabalho SQL usando o `sqlWorkflowInstanceStore` elemento de comportamento <> em um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="50621-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="50621-109">Para obter mais informações sobre como configurar o repositório de instância do fluxo de trabalho SQL, consulte [como habilitar a persistência de SQL para fluxos de trabalho e serviços de fluxo de trabalho](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="50621-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="50621-110">Para obter mais informações sobre as configurações individuais para o `sqlWorkflowInstanceStore` elemento de comportamento <>, consulte [repositório de instâncias de fluxo de trabalho SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="50621-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="50621-111">O Windows Server app Fabric fornece seu próprio armazenamento de persistência.</span><span class="sxs-lookup"><span data-stu-id="50621-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="50621-112">Para obter mais informações, consulte [persistência do Windows Server app Fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="50621-112">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="50621-113">O exemplo de configuração anterior usa configuração simplificada.</span><span class="sxs-lookup"><span data-stu-id="50621-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="50621-114">Para obter mais informações, consulte [configuração simplificada](../simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="50621-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="50621-115">Para configurar o repositório de instância do fluxo de trabalho SQL no código</span><span class="sxs-lookup"><span data-stu-id="50621-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="50621-116">As propriedades do armazenamento da instância do fluxo de trabalho SQL podem ser configuradas por meio do <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> , um comportamento de serviço que permite que você altere as configurações por meio de código.</span><span class="sxs-lookup"><span data-stu-id="50621-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="50621-117">O exemplo a seguir mostra como configurar o armazenamento de instância do fluxo de trabalho SQL usando o <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento Behavior em um código</span><span class="sxs-lookup"><span data-stu-id="50621-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="50621-118">Para obter mais informações sobre como configurar o repositório de instância do fluxo de trabalho SQL, consulte [como habilitar a persistência de SQL para fluxos de trabalho e serviços de fluxo de trabalho](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="50621-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="50621-119">Para obter mais informações sobre as configurações individuais do <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamento, consulte [repositório de instância de fluxo de trabalho SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="50621-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="50621-120">O Windows Server app Fabric fornece seu próprio armazenamento de persistência.</span><span class="sxs-lookup"><span data-stu-id="50621-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="50621-121">Para obter mais informações, consulte [persistência do Windows Server app Fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="50621-121">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="50621-122">O exemplo de configuração anterior usa configuração simplificada.</span><span class="sxs-lookup"><span data-stu-id="50621-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="50621-123">Para obter mais informações, consulte [configuração simplificada](../simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="50621-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="50621-124">Para obter um exemplo de como configurar a persistência programaticamente [, consulte Como habilitar a persistência para fluxos de trabalho e serviços de fluxo de trabalho](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="50621-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50621-125">Veja também</span><span class="sxs-lookup"><span data-stu-id="50621-125">See also</span></span>

- [<span data-ttu-id="50621-126">Serviços de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="50621-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="50621-127">Persistência de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="50621-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="50621-128">[Persistência da tela de aplicativo Windows Server](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="50621-128">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
