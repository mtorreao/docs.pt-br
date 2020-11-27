---
title: Adulteração
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249794"
---
# <a name="tampering"></a><span data-ttu-id="c24ea-102">Adulteração</span><span class="sxs-lookup"><span data-stu-id="c24ea-102">Tampering</span></span>

<span data-ttu-id="c24ea-103">A *violação* é o ato de alterar uma mensagem ou a entrega de uma mensagem, e usar a mensagem alterada para uma finalidade diferente da que foi pretendida.</span><span class="sxs-lookup"><span data-stu-id="c24ea-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="c24ea-104">Não desabilitar WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="c24ea-104">Do Not Disable WS-Addressing</span></span>  

 <span data-ttu-id="c24ea-105">A especificação de WS-Addressing fornece cabeçalhos de endereço em cada mensagem, permitindo que um destinatário da mensagem Verifique o remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c24ea-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="c24ea-106">Você pode desabilitar esse recurso definindo a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="c24ea-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="c24ea-107">Quando o modo de segurança é definido como Message e, se WS-Addressing estiver desabilitado, um invasor poderá receber uma solicitação de um cliente e enviá-lo para outro serviço, e o segundo serviço não terá como detectar se a mensagem veio do cliente original.</span><span class="sxs-lookup"><span data-stu-id="c24ea-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="c24ea-108">Na verdade, o primeiro serviço pode fingir que é um cliente ao conversar com o segundo serviço.</span><span class="sxs-lookup"><span data-stu-id="c24ea-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="c24ea-109">Para atenuar isso, nunca defina a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> e evite o uso de <xref:System.ServiceModel.Channels.MessageVersion> , como a <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> propriedade estática, que define a <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> propriedade como <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> .</span><span class="sxs-lookup"><span data-stu-id="c24ea-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24ea-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="c24ea-110">See also</span></span>

- [<span data-ttu-id="c24ea-111">Considerações sobre segurança</span><span class="sxs-lookup"><span data-stu-id="c24ea-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="c24ea-112">Divulgação de Informações Confidenciais</span><span class="sxs-lookup"><span data-stu-id="c24ea-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="c24ea-113">Elevação de Privilégio</span><span class="sxs-lookup"><span data-stu-id="c24ea-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="c24ea-114">Negação de Serviço</span><span class="sxs-lookup"><span data-stu-id="c24ea-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="c24ea-115">Cenários sem suporte</span><span class="sxs-lookup"><span data-stu-id="c24ea-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="c24ea-116">Ataques por repetição</span><span class="sxs-lookup"><span data-stu-id="c24ea-116">Replay Attacks</span></span>](replay-attacks.md)
