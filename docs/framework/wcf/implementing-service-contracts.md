---
title: Implementando contratos de serviço
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 121922e3de62653babdac084d6bd226f7263e33c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262730"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="640ad-102">Implementando contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="640ad-102">Implementing Service Contracts</span></span>

<span data-ttu-id="640ad-103">Um serviço é uma classe que expõe a funcionalidade disponível para clientes em um ou mais pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="640ad-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="640ad-104">Para criar um serviço, escreva uma classe que implemente um contrato de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="640ad-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="640ad-105">É possível fazer isso de duas formas.</span><span class="sxs-lookup"><span data-stu-id="640ad-105">You can do this in one of two ways.</span></span> <span data-ttu-id="640ad-106">Você pode definir o contrato separadamente como uma interface e, em seguida, criar uma classe que implementa essa interface.</span><span class="sxs-lookup"><span data-stu-id="640ad-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="640ad-107">Como alternativa, você pode criar a classe e o contrato diretamente colocando o <xref:System.ServiceModel.ServiceContractAttribute> atributo na própria classe e o <xref:System.ServiceModel.OperationContractAttribute> atributo nos métodos disponíveis para os clientes do serviço.</span><span class="sxs-lookup"><span data-stu-id="640ad-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="640ad-108">Criando uma classe de serviço</span><span class="sxs-lookup"><span data-stu-id="640ad-108">Creating a service class</span></span>  

 <span data-ttu-id="640ad-109">Veja a seguir um exemplo de um serviço que implementa um `IMath` contrato que foi definido separadamente.</span><span class="sxs-lookup"><span data-stu-id="640ad-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="640ad-110">Como alternativa, um serviço pode expor um contrato diretamente.</span><span class="sxs-lookup"><span data-stu-id="640ad-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="640ad-111">Veja a seguir um exemplo de uma classe de serviço que define e implementa um `MathService` contrato.</span><span class="sxs-lookup"><span data-stu-id="640ad-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="640ad-112">Observe que os serviços anteriores expõem contratos diferentes porque os nomes de contrato são diferentes.</span><span class="sxs-lookup"><span data-stu-id="640ad-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="640ad-113">No primeiro caso, o contrato exposto é denominado " `IMath` " enquanto, no segundo caso, o contrato é denominado " `MathService` ".</span><span class="sxs-lookup"><span data-stu-id="640ad-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="640ad-114">Você pode definir algumas coisas nos níveis de implementação de serviço e operação, como simultaneidade e instanciação.</span><span class="sxs-lookup"><span data-stu-id="640ad-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="640ad-115">Para obter mais informações, consulte [projetando e implementando serviços](designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="640ad-115">For more information, see [Designing and Implementing Services](designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="640ad-116">Depois de implementar um contrato de serviço, você deve criar um ou mais pontos de extremidade para o serviço.</span><span class="sxs-lookup"><span data-stu-id="640ad-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="640ad-117">Para obter mais informações, consulte [visão geral da criação de ponto de extremidade](endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="640ad-117">For more information, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="640ad-118">Para obter mais informações sobre como executar um serviço, consulte [serviços de hospedagem](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="640ad-118">For more information about how to run a service, see [Hosting Services](hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640ad-119">Veja também</span><span class="sxs-lookup"><span data-stu-id="640ad-119">See also</span></span>

- [<span data-ttu-id="640ad-120">Serviços de implantação e projeção</span><span class="sxs-lookup"><span data-stu-id="640ad-120">Designing and Implementing Services</span></span>](designing-and-implementing-services.md)
- [<span data-ttu-id="640ad-121">Como: criar um serviço com uma classe de contrato</span><span class="sxs-lookup"><span data-stu-id="640ad-121">How to: Create a Service with a Contract Class</span></span>](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [<span data-ttu-id="640ad-122">Como: criar um serviço com interface de contrato</span><span class="sxs-lookup"><span data-stu-id="640ad-122">How to: Create a Service with a Contract Interface</span></span>](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [<span data-ttu-id="640ad-123">Especificando comportamento de tempo de execução de serviço</span><span class="sxs-lookup"><span data-stu-id="640ad-123">Specifying Service Run-Time Behavior</span></span>](specifying-service-run-time-behavior.md)
