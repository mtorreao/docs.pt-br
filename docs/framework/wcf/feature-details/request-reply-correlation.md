---
title: Correlação resposta/solicitação
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: da7739af7368cd7ebb55ed0ea2511e10f0bcb3f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239062"
---
# <a name="request-reply-correlation"></a><span data-ttu-id="ec9ed-102">Correlação resposta/solicitação</span><span class="sxs-lookup"><span data-stu-id="ec9ed-102">Request-Reply Correlation</span></span>

<span data-ttu-id="ec9ed-103">A correlação de solicitação-resposta é usada com um <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par para implementar uma operação bidirecional em um serviço de fluxo de trabalho e com um <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que invoca uma operação bidirecional em outro serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="ec9ed-104">Ao invocar uma operação bidirecional em um serviço WCF, o serviço pode ser um serviço de Windows Communication Foundation (WCF) baseado em código imperativo tradicional ou pode ser um serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="ec9ed-105">Para usar a correlação de solicitação-resposta, é necessário usar uma associação bidirecional, como <xref:System.ServiceModel.BasicHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="ec9ed-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="ec9ed-106">Se invocar ou implementar uma operação bidirecional, as etapas de inicialização de correlação são semelhantes e são abordadas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="ec9ed-107">Usando a correlação em uma operação de Two-Way com Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="ec9ed-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  

 <span data-ttu-id="ec9ed-108">Um <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par é usado para implementar uma operação bidirecional em um serviço de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="ec9ed-109">O tempo de execução usa a correlação de solicitação-resposta para garantir que a resposta seja expedida para o chamador correto.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="ec9ed-110">Quando um fluxo de trabalho é hospedado usando <xref:System.ServiceModel.Activities.WorkflowServiceHost> , que é o caso dos serviços de fluxo de trabalho, a inicialização de correlação padrão é suficiente.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="ec9ed-111">Nesse cenário, um <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par é usado por um fluxo de trabalho e nenhuma configuração de correlação específica é necessária.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="ec9ed-112">Inicializando explicitamente Request-Reply correlação</span><span class="sxs-lookup"><span data-stu-id="ec9ed-112">Explicitly Initializing Request-Reply Correlation</span></span>  

 <span data-ttu-id="ec9ed-113">Se outras operações de duas vias estiverem em paralelo, a correlação deverá ser configurada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="ec9ed-114">Isso pode ser feito especificando um <xref:System.ServiceModel.Activities.CorrelationHandle> e <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> , ou colocando o <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> dentro de um <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="ec9ed-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="ec9ed-115">Neste exemplo, a correlação de solicitação-resposta é configurada em um <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="ec9ed-116">Em vez de configurar explicitamente a correlação, uma <xref:System.ServiceModel.Activities.CorrelationScope> atividade pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="ec9ed-117"><xref:System.ServiceModel.Activities.CorrelationScope> fornece um implícito <xref:System.ServiceModel.Activities.CorrelationHandle> para as atividades de mensagens que ele contém.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="ec9ed-118">Neste exemplo, um <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par está contido dentro de um <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="ec9ed-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="ec9ed-119">Nenhuma configuração de correlação explícita é necessária.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-119">No explicit correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 <span data-ttu-id="ec9ed-120">Se correlações adicionais forem necessárias, elas poderão ser configuradas usando a <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> propriedade das respectivas atividades de mensagens usando os tipos desejados `CorrelationInitializer` .</span><span class="sxs-lookup"><span data-stu-id="ec9ed-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="ec9ed-121">Usando a correlação em uma operação de Two-Way com Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="ec9ed-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  

 <span data-ttu-id="ec9ed-122">Embora a <xref:System.ServiceModel.Activities.Receive> atividade só possa ser usada em um serviço de fluxo de trabalho hospedado pelo <xref:System.ServiceModel.Activities.WorkflowServiceHost> , <xref:System.ServiceModel.Activities.Send> e o <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par pode ser usado em qualquer fluxo de trabalho que deve invocar um método em um serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="ec9ed-123">Se o fluxo de trabalho for hospedado usando <xref:System.ServiceModel.Activities.WorkflowServiceHost> , a correlação padrão descrita na seção anterior se aplicará, mas se não, a correlação deverá ser configurada explicitamente usando o desejado <xref:System.ServiceModel.Activities.CorrelationInitializer> e <xref:System.ServiceModel.Activities.CorrelationHandle> , ou usando o gerenciamento de identificador implícito do <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="ec9ed-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="ec9ed-124">Ao usar **Adicionar referência de serviço** em um serviço com operações bidirecionais, são geradas atividades que encapsulam uma <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> atividade de par internamente com a correlação de solicitação/resposta especificada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="ec9ed-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
