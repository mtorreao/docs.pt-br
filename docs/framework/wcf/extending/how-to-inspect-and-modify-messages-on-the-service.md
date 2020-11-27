---
title: 'Como: inspecionar e modificar mensagens do serviço'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 8d1ce6ef00462adb38e3d59c3d9bd35694c4dbe9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249053"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="a3b21-102">Como: inspecionar e modificar mensagens do serviço</span><span class="sxs-lookup"><span data-stu-id="a3b21-102">How to: Inspect and Modify Messages on the Service</span></span>

<span data-ttu-id="a3b21-103">Você pode inspecionar ou modificar as mensagens de entrada ou saída em um cliente Windows Communication Foundation (WCF) implementando uma <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> e inserindo-a no tempo de execução do serviço.</span><span class="sxs-lookup"><span data-stu-id="a3b21-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="a3b21-104">Para obter mais informações, consulte [estendendo expatchers](extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="a3b21-104">For more information, see [Extending Dispatchers](extending-dispatchers.md).</span></span> <span data-ttu-id="a3b21-105">O recurso equivalente no serviço é o <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a3b21-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="a3b21-106">Para inspecionar ou modificar mensagens</span><span class="sxs-lookup"><span data-stu-id="a3b21-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="a3b21-107">Implemente a interface <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3b21-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="a3b21-108">Implemente <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> uma <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> interface, ou, <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> dependendo do escopo no qual você deseja inserir facilmente seu inspetor de mensagem de serviço.</span><span class="sxs-lookup"><span data-stu-id="a3b21-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="a3b21-109">Insira seu comportamento antes de chamar o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> método no <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a3b21-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a3b21-110">Para obter detalhes, consulte [Configurando e estendendo o tempo de execução com comportamentos](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="a3b21-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3b21-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a3b21-111">Example</span></span>  

 <span data-ttu-id="a3b21-112">Os exemplos de código a seguir mostram, em ordem:</span><span class="sxs-lookup"><span data-stu-id="a3b21-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="a3b21-113">Uma implementação do Inspetor de serviço.</span><span class="sxs-lookup"><span data-stu-id="a3b21-113">A service inspector implementation.</span></span>  
  
- <span data-ttu-id="a3b21-114">Um comportamento de serviço que insere o Inspetor.</span><span class="sxs-lookup"><span data-stu-id="a3b21-114">A service behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="a3b21-115">Um arquivo de configuração que carrega e executa o comportamento em um aplicativo de serviço.</span><span class="sxs-lookup"><span data-stu-id="a3b21-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a3b21-116">Veja também</span><span class="sxs-lookup"><span data-stu-id="a3b21-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="a3b21-117">Configurando e estendendo o runtime com comportamentos</span><span class="sxs-lookup"><span data-stu-id="a3b21-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
