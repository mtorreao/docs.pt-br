---
title: 'Como: especificar uma associação de cliente no código'
description: Saiba como especificar a associação para um cliente WCF imperativamente no código. O cliente acessa um serviço neste exemplo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: f9a56c631d841fe60923c05a19bdec9db989ac60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236566"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="464de-104">Como: especificar uma associação de cliente no código</span><span class="sxs-lookup"><span data-stu-id="464de-104">How to: Specify a Client Binding in Code</span></span>

<span data-ttu-id="464de-105">Neste exemplo, um cliente é criado para usar um serviço de calculadora e a associação para esse cliente é especificada imperativamente no código.</span><span class="sxs-lookup"><span data-stu-id="464de-105">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="464de-106">O cliente acessa o `CalculatorService` , que implementa a `ICalculator` interface, e o serviço e o cliente usam a <xref:System.ServiceModel.BasicHttpBinding> classe.</span><span class="sxs-lookup"><span data-stu-id="464de-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="464de-107">Este procedimento pressupõe que o serviço de calculadora está em execução.</span><span class="sxs-lookup"><span data-stu-id="464de-107">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="464de-108">Para obter informações sobre como criar o serviço, consulte [como especificar uma associação de serviço na configuração](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="464de-108">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="464de-109">Ele também usa a [ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) fornece para gerar automaticamente os componentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="464de-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="464de-110">A ferramenta gera o código do cliente para acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="464de-110">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="464de-111">O cliente é criado em duas partes.</span><span class="sxs-lookup"><span data-stu-id="464de-111">The client is built in two parts.</span></span> <span data-ttu-id="464de-112">Svcutil.exe gera o `ClientCalculator` que implementa a `ICalculator` interface.</span><span class="sxs-lookup"><span data-stu-id="464de-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="464de-113">Esse aplicativo cliente é então construído pela construção de uma instância do `ClientCalculator` e, em seguida, pela especificação da associação e do endereço do serviço no código.</span><span class="sxs-lookup"><span data-stu-id="464de-113">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="464de-114">Para a cópia de origem deste exemplo, consulte o exemplo de [BasicBinding](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="464de-114">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="464de-115">Para especificar uma associação personalizada no código</span><span class="sxs-lookup"><span data-stu-id="464de-115">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="464de-116">Use Svcutil.exe da linha de comando para gerar código de metadados de serviço.</span><span class="sxs-lookup"><span data-stu-id="464de-116">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="464de-117">O cliente gerado contém a `ICalculator` interface que define o contrato de serviço que a implementação do cliente deve satisfazer.</span><span class="sxs-lookup"><span data-stu-id="464de-117">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="464de-118">O cliente gerado também contém a implementação do `ClientCalculator` .</span><span class="sxs-lookup"><span data-stu-id="464de-118">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="464de-119">Crie uma instância do `ClientCalculator` que usa a <xref:System.ServiceModel.BasicHttpBinding> classe em um aplicativo cliente e, em seguida, chame as operações de serviço no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="464de-119">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="464de-120">Compile e execute o cliente.</span><span class="sxs-lookup"><span data-stu-id="464de-120">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464de-121">Veja também</span><span class="sxs-lookup"><span data-stu-id="464de-121">See also</span></span>

- [<span data-ttu-id="464de-122">Usando associações para configurar serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="464de-122">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
