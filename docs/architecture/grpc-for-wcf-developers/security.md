---
title: Segurança em aplicativos gRPC – gRPC para desenvolvedores do WCF
description: Visão geral de autenticação e autorização de canal e chamada no gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: a5c16a4a4f7567e23bf4f9e3049fe116086daf12
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938085"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="18599-103">Segurança em aplicativos gRPC</span><span class="sxs-lookup"><span data-stu-id="18599-103">Security in gRPC applications</span></span>

<span data-ttu-id="18599-104">Em qualquer cenário do mundo real, a proteção de aplicativos e serviços é essencial.</span><span class="sxs-lookup"><span data-stu-id="18599-104">In any real-world scenario, securing applications and services are essential.</span></span> <span data-ttu-id="18599-105">A segurança abrange três áreas principais:</span><span class="sxs-lookup"><span data-stu-id="18599-105">Security covers three key areas:</span></span>

* <span data-ttu-id="18599-106">Criptografar o tráfego de rede para impedir que hackers mal-intencionados o interceptem.</span><span class="sxs-lookup"><span data-stu-id="18599-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="18599-107">Autenticar clientes e servidores para estabelecer identidade e confiança.</span><span class="sxs-lookup"><span data-stu-id="18599-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="18599-108">Autorizar clientes a controlar o acesso a sistemas e aplicar permissões com base na identidade.</span><span class="sxs-lookup"><span data-stu-id="18599-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="18599-109">A *autenticação* se preocupa com o estabelecimento da identidade de um cliente ou servidor.</span><span class="sxs-lookup"><span data-stu-id="18599-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="18599-110">A *autorização* está preocupada com a determinação se um cliente tem permissão para acessar um recurso ou emitir um comando.</span><span class="sxs-lookup"><span data-stu-id="18599-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="18599-111">Este capítulo abordará as instalações de autenticação e autorização no gRPC para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="18599-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="18599-112">Ele também discutirá a segurança de rede por meio de conexões criptografadas por TLS.</span><span class="sxs-lookup"><span data-stu-id="18599-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="18599-113">Autenticação e autorização do WCF</span><span class="sxs-lookup"><span data-stu-id="18599-113">WCF authentication and authorization</span></span>

<span data-ttu-id="18599-114">No Windows Communication Foundation (WCF), a autenticação e a autorização foram manipuladas de maneiras diferentes, dependendo dos transportes e das associações que estão sendo usadas.</span><span class="sxs-lookup"><span data-stu-id="18599-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="18599-115">O WCF dá suporte a vários padrões WS- \* Security.</span><span class="sxs-lookup"><span data-stu-id="18599-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="18599-116">Também há suporte para a autenticação do Windows para serviços HTTP em execução no IIS ou em serviços NetTCP entre sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="18599-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="18599-117">autenticação e autorização do gRPC</span><span class="sxs-lookup"><span data-stu-id="18599-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="18599-118">a autenticação e a autorização do gRPC funcionam em dois níveis:</span><span class="sxs-lookup"><span data-stu-id="18599-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="18599-119">A autenticação/autorização em nível de chamada geralmente é manipulada por meio de tokens que são aplicados nos metadados quando a chamada é feita.</span><span class="sxs-lookup"><span data-stu-id="18599-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="18599-120">A autenticação no nível do canal usa um certificado de cliente que é aplicado no nível de conexão.</span><span class="sxs-lookup"><span data-stu-id="18599-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="18599-121">Ele também pode incluir credenciais de autenticação/autorização em nível de chamada para serem aplicadas a cada chamada no canal automaticamente.</span><span class="sxs-lookup"><span data-stu-id="18599-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="18599-122">Você pode usar um ou ambos os mecanismos para ajudar a proteger seu serviço.</span><span class="sxs-lookup"><span data-stu-id="18599-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="18599-123">A implementação de ASP.NET Core do gRPC dá suporte à autenticação e autorização por meio da maioria dos mecanismos de ASP.NET Core padrão:</span><span class="sxs-lookup"><span data-stu-id="18599-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="18599-124">Chamar autenticação</span><span class="sxs-lookup"><span data-stu-id="18599-124">Call authentication</span></span>
  - <span data-ttu-id="18599-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="18599-125">Azure Active Directory</span></span>
  - <span data-ttu-id="18599-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="18599-126">IdentityServer</span></span>
  - <span data-ttu-id="18599-127">Token de portador JWT</span><span class="sxs-lookup"><span data-stu-id="18599-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="18599-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="18599-128">OAuth 2.0</span></span>
  - <span data-ttu-id="18599-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="18599-129">OpenID Connect</span></span>
  - <span data-ttu-id="18599-130">O certificado do provedor de identidade do Web Services Federation</span><span class="sxs-lookup"><span data-stu-id="18599-130">WS-Federation</span></span>
- <span data-ttu-id="18599-131">Autenticação de canal</span><span class="sxs-lookup"><span data-stu-id="18599-131">Channel authentication</span></span>
  - <span data-ttu-id="18599-132">Certificado do cliente</span><span class="sxs-lookup"><span data-stu-id="18599-132">Client certificate</span></span>

<span data-ttu-id="18599-133">Os métodos de autenticação de chamada são todos baseados em *tokens*.</span><span class="sxs-lookup"><span data-stu-id="18599-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="18599-134">A única diferença real é como os tokens são gerados e as bibliotecas que são usadas para validar os tokens no serviço de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="18599-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="18599-135">Para obter mais informações, consulte o artigo [autenticação e autorização](/aspnet/core/grpc/authn-and-authz) .</span><span class="sxs-lookup"><span data-stu-id="18599-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="18599-136">Quando você estiver usando o gRPC em uma conexão HTTP/2 criptografada por TLS, todo o tráfego entre clientes e servidores será criptografado, mesmo que você não use a autenticação no nível do canal.</span><span class="sxs-lookup"><span data-stu-id="18599-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="18599-137">Este capítulo mostrará como aplicar credenciais de chamada e credenciais de canal a um serviço gRPC.</span><span class="sxs-lookup"><span data-stu-id="18599-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="18599-138">Ele também mostrará como usar credenciais de um cliente .NET gRPC para se autenticar com o serviço.</span><span class="sxs-lookup"><span data-stu-id="18599-138">It will also show how to use credentials from a .NET gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="18599-139">[Anterior](client-libraries.md) 
> [Avançar](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="18599-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
