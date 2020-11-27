---
title: 'Melhores práticas: intermediários'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 57be78681147dfc5bc37701a76c1347040f5da1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277888"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="b8f7d-102">Melhores práticas: intermediários</span><span class="sxs-lookup"><span data-stu-id="b8f7d-102">Best Practices: Intermediaries</span></span>

<span data-ttu-id="b8f7d-103">Deve-se ter cuidado para lidar corretamente com falhas ao chamar intermediários para garantir que os canais do lado do serviço no intermediário sejam fechados corretamente.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="b8f7d-104">Considere este cenário.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-104">Consider the following scenario.</span></span> <span data-ttu-id="b8f7d-105">Um cliente faz uma chamada para um intermediário que chama um serviço de back-end.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="b8f7d-106">O serviço de back-end não define nenhum contrato de falha, portanto, qualquer falha gerada desse serviço será tratada como uma falha não tipada.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="b8f7d-107">O serviço de back-end gera um <xref:System.ApplicationException> e o WCF anula corretamente o canal do lado do serviço.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="b8f7d-108"><xref:System.ApplicationException>Em seguida, as superfícies como uma <xref:System.ServiceModel.FaultException> que são geradas para o intermediário.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="b8f7d-109">O intermediário relança o <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="b8f7d-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="b8f7d-110">O WCF interpreta isso como uma falha não tipada do intermediário e a encaminha para o cliente.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="b8f7d-111">Após o recebimento da falha, tanto o intermediário quanto o cliente falham em seus canais do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="b8f7d-112">No entanto, o canal do lado do serviço do intermediário permanece aberto porque o WCF não sabe que a falha é fatal.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="b8f7d-113">A prática recomendada neste cenário é detectar se a falha proveniente do serviço é fatal e, nesse caso, o intermediário deve falhar em seu canal do lado do serviço, conforme mostrado no trecho de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8f7d-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8f7d-114">Veja também</span><span class="sxs-lookup"><span data-stu-id="b8f7d-114">See also</span></span>

- [<span data-ttu-id="b8f7d-115">Tratamento de erros do WCF</span><span class="sxs-lookup"><span data-stu-id="b8f7d-115">WCF Error Handling</span></span>](wcf-error-handling.md)
- [<span data-ttu-id="b8f7d-116">Especificando e lidando com falhas em contratos e serviços</span><span class="sxs-lookup"><span data-stu-id="b8f7d-116">Specifying and Handling Faults in Contracts and Services</span></span>](specifying-and-handling-faults-in-contracts-and-services.md)
