---
title: Segurança de transporte
description: Use essas referências para entender os mecanismos de segurança de transporte em WFC, como eles são implementados e suas opções.
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
ms.openlocfilehash: cecb1ec263d993e9d669d73245fad1a49fe041fd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251705"
---
# <a name="transport-security"></a><span data-ttu-id="bb4f4-103">Segurança de transporte</span><span class="sxs-lookup"><span data-stu-id="bb4f4-103">Transport Security</span></span>

<span data-ttu-id="bb4f4-104">A segurança de transporte no Windows Communication Foundation (WCF) depende da Associação selecionada.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-104">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="bb4f4-105">O transporte que a associação implementa determina o mecanismo de segurança real.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-105">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="bb4f4-106">Os tópicos nesta seção explicam os mecanismos que são implementados e suas opções.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-106">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb4f4-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bb4f4-107">In This Section</span></span>  

 [<span data-ttu-id="bb4f4-108">Visão geral de segurança de transporte</span><span class="sxs-lookup"><span data-stu-id="bb4f4-108">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="bb4f4-109">Explica os conceitos básicos da segurança de transporte no WCF.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-109">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="bb4f4-110">Segurança de transporte de HTTP</span><span class="sxs-lookup"><span data-stu-id="bb4f4-110">HTTP Transport Security</span></span>](http-transport-security.md)  
 <span data-ttu-id="bb4f4-111">Explica como o WCF implementa protocolo SSL (SSL ou HTTPS).</span><span class="sxs-lookup"><span data-stu-id="bb4f4-111">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="bb4f4-112">Noções básicas de autenticação HTTP</span><span class="sxs-lookup"><span data-stu-id="bb4f4-112">Understanding HTTP Authentication</span></span>](understanding-http-authentication.md)  
 <span data-ttu-id="bb4f4-113">Descreve os esquemas de autenticação HTTP, como Basic, Digest, NTLM (NT LAN Manager) e outros.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-113">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="bb4f4-114">Utilizando Personificação com segurança de transporte</span><span class="sxs-lookup"><span data-stu-id="bb4f4-114">Using Impersonation with Transport Security</span></span>](using-impersonation-with-transport-security.md)  
 <span data-ttu-id="bb4f4-115">Explica os cinco níveis de representação que são possíveis com o modo de segurança de transporte.</span><span class="sxs-lookup"><span data-stu-id="bb4f4-115">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="bb4f4-116">Como: configurar uma porta com um certificado SSL</span><span class="sxs-lookup"><span data-stu-id="bb4f4-116">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="bb4f4-117">Percorre as noções básicas de configuração de uma porta em um computador com um certificado X. 509 para segurança SSL (transporte).</span><span class="sxs-lookup"><span data-stu-id="bb4f4-117">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bb4f4-118">Referência</span><span class="sxs-lookup"><span data-stu-id="bb4f4-118">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="bb4f4-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="bb4f4-119">Related Sections</span></span>  

 [<span data-ttu-id="bb4f4-120">Protegendo serviços e clientes</span><span class="sxs-lookup"><span data-stu-id="bb4f4-120">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb4f4-121">Veja também</span><span class="sxs-lookup"><span data-stu-id="bb4f4-121">See also</span></span>

- [<span data-ttu-id="bb4f4-122">Programação de segurança do WCF</span><span class="sxs-lookup"><span data-stu-id="bb4f4-122">Programming WCF Security</span></span>](programming-wcf-security.md)
