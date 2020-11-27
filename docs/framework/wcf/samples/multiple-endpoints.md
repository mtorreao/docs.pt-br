---
title: Vários pontos de extremidade
ms.date: 03/30/2017
helpviewer_keywords:
- Multiple EndPoints
ms.assetid: 8f0c2e1f-9aee-41c2-8301-c72b7f664412
ms.openlocfilehash: 92c329ff922b5e4fc025245dac596c6abebc2716
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260143"
---
# <a name="multiple-endpoints"></a><span data-ttu-id="ffeeb-102">Vários pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="ffeeb-102">Multiple Endpoints</span></span>

<span data-ttu-id="ffeeb-103">O exemplo de vários pontos de extremidade demonstra como configurar vários pontos de extremidade em um serviço e como comunicar-se com cada um dos clientes.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-103">The Multiple Endpoints sample demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span> <span data-ttu-id="ffeeb-104">Este exemplo é baseado na [introdução](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ffeeb-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="ffeeb-105">A configuração de serviço foi modificada para definir dois pontos de extremidade que dão suporte ao `ICalculator` contrato, mas cada um em um endereço diferente usando uma associação diferente.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-105">The service configuration has been modified to define two endpoints that support the `ICalculator` contract, but each at a different address using a different binding.</span></span> <span data-ttu-id="ffeeb-106">A configuração do cliente e o código foram modificados para se comunicar com os dois pontos de extremidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-106">The client configuration and code have been modified to communicate with both of the service endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ffeeb-107">O procedimento de instalação e as instruções de Build para este exemplo estão localizados no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ffeeb-108">O arquivo de Web.config de serviço foi modificado para definir dois pontos de extremidade, cada um com suporte para o mesmo `ICalculator` contrato, mas em endereços diferentes usando associações diferentes.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-108">The service Web.config file has been modified to define two endpoints, each supporting the same `ICalculator` contract, but at different addresses using different bindings.</span></span> <span data-ttu-id="ffeeb-109">O primeiro ponto de extremidade é definido no endereço base usando uma `basicHttpBinding` associação, que não tem segurança habilitada.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-109">The first endpoint is defined at the base address using a `basicHttpBinding` binding, which does not have security enabled.</span></span> <span data-ttu-id="ffeeb-110">O segundo ponto de extremidade é definido em {BaseAddress}/Secure usando uma `wsHttpBinding` associação, que é segura por padrão, usando WS-Security com a autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-110">The second endpoint is defined at {baseaddress}/secure using a `wsHttpBinding` binding, which is secure by default, using WS-Security with Windows authentication.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- This endpoint is exposed at the base address provided by host:  
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- secure endpoint exposed at {base address}/secure:  
       http://localhost/servicemodelsamples/service.svc/secure -->  
  <endpoint address="secure"  
            binding="wsHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="ffeeb-111">Os dois pontos de extremidade também são configurados no cliente.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-111">Both endpoints are also configured on the client.</span></span> <span data-ttu-id="ffeeb-112">Esses pontos de extremidade recebem nomes para que o chamador possa passar o nome do ponto de extremidades desejado para o construtor do cliente.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-112">These endpoints are given names so that the caller can pass the desired endpoint name into the constructor of the client.</span></span>  
  
```xml  
<client>  
  <!-- Passing "basic" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="basic"  
            address="http://localhost/servicemodelsamples/service.svc"
            binding="basicHttpBinding"
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- Passing "secure" into the constructor of the CalculatorClient  
       class selects this endpoint.-->  
  <endpoint name="secure"  
            address="http://localhost/servicemodelsamples/service.svc/secure"
            binding="wsHttpBinding"
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
```  
  
 <span data-ttu-id="ffeeb-113">O cliente usa os dois pontos de extremidade, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-113">The client uses both endpoints as shown in the following code.</span></span>  
  
```csharp  
static void Main()  
{  
    // Create a client to the basic endpoint configuration.  
    CalculatorClient client = new CalculatorClient("basic");  
    Console.WriteLine("Communicate with basic endpoint.");  
    // call operations  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    // Create a client to the secure endpoint configuration.  
    client = new CalculatorClient("secure");  
    Console.WriteLine("Communicate with secure endpoint.");  
    // Call operations.  
    DoCalculations(client);  
  
    // Close the client and release resources.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="ffeeb-114">Quando você executa o cliente, as interações com ambos os pontos de extremidade são exibidas.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-114">When you run the client, interactions with both endpoints are displayed.</span></span>  
  
```console
Communicate with basic endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Communicate with secure endpoint.  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ffeeb-115">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="ffeeb-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ffeeb-116">Verifique se você executou o [procedimento de configuração única para os exemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffeeb-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ffeeb-117">Para criar a edição C# ou Visual Basic .NET da solução, siga as instruções em [criando os exemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffeeb-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ffeeb-118">Para executar o exemplo em uma configuração de computador único ou cruzado, siga as instruções em [executando os exemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ffeeb-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ffeeb-119">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ffeeb-120">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ffeeb-121">Se esse diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos de Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para baixar todos os Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffeeb-122">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="ffeeb-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpoints`  
