---
title: Considerações de segurança no WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 796098258601ec5fa208fd8a8060b28c3eeeb4d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276016"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="5aee9-102">Considerações de segurança no WCF</span><span class="sxs-lookup"><span data-stu-id="5aee9-102">Security Considerations in WCF</span></span>

<span data-ttu-id="5aee9-103">Os tópicos nesta seção listam vários itens relacionados à segurança a serem considerados ao criar um aplicativo Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5aee9-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5aee9-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5aee9-104">In This Section</span></span>  

 [<span data-ttu-id="5aee9-105">Divulgação de Informações Confidenciais</span><span class="sxs-lookup"><span data-stu-id="5aee9-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="5aee9-106">Discute as várias maneiras pelas quais as informações podem ser divulgadas ou atacadas e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5aee9-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5aee9-107">Elevação de Privilégio</span><span class="sxs-lookup"><span data-stu-id="5aee9-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="5aee9-108">Discute os efeitos de dar a um invasor permissões de autorização além daquelas inicialmente concedidas e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5aee9-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5aee9-109">Negação de Serviço</span><span class="sxs-lookup"><span data-stu-id="5aee9-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="5aee9-110">Discute o que acontece quando um sistema não consegue processar mensagens adequadamente e como atenuá-la.</span><span class="sxs-lookup"><span data-stu-id="5aee9-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="5aee9-111">Adulteração</span><span class="sxs-lookup"><span data-stu-id="5aee9-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="5aee9-112">Discute a alteração de mensagens ou a entrega de mensagens e como atenuá-la.</span><span class="sxs-lookup"><span data-stu-id="5aee9-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="5aee9-113">Ataques por repetição</span><span class="sxs-lookup"><span data-stu-id="5aee9-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="5aee9-114">Discute o que acontece quando um invasor copia um fluxo de mensagens entre duas partes e repete o fluxo para uma ou mais das partes e como mitigar isso.</span><span class="sxs-lookup"><span data-stu-id="5aee9-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="5aee9-115">Considerações de segurança para sessões seguras</span><span class="sxs-lookup"><span data-stu-id="5aee9-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="5aee9-116">Discute os itens a seguir que afetam a segurança ao implementar sessões seguras.</span><span class="sxs-lookup"><span data-stu-id="5aee9-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="5aee9-117">Cenários sem suporte</span><span class="sxs-lookup"><span data-stu-id="5aee9-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="5aee9-118">Lista vários cenários que não dão suporte a um aspecto específico de segurança e que devem ser evitados ou considerados.</span><span class="sxs-lookup"><span data-stu-id="5aee9-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5aee9-119">Referência</span><span class="sxs-lookup"><span data-stu-id="5aee9-119">Reference</span></span>  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="5aee9-120">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="5aee9-120">Related Sections</span></span>  

 [<span data-ttu-id="5aee9-121">Orientação de segurança e práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="5aee9-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="5aee9-122">Veja também</span><span class="sxs-lookup"><span data-stu-id="5aee9-122">See also</span></span>

- [<span data-ttu-id="5aee9-123">Segurança</span><span class="sxs-lookup"><span data-stu-id="5aee9-123">Security</span></span>](security.md)
