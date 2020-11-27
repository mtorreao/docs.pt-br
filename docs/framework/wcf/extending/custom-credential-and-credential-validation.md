---
title: Credencial personalizada e validação de credencial
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 5f2909bb088a5f3d3203fe3c9e24b2df3450aa3f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257822"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="37310-102">Credencial personalizada e validação de credencial</span><span class="sxs-lookup"><span data-stu-id="37310-102">Custom Credential and Credential Validation</span></span>

<span data-ttu-id="37310-103">A segurança no Windows Communication Foundation (WCF) é baseada na troca de credenciais entre serviços e clientes.</span><span class="sxs-lookup"><span data-stu-id="37310-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="37310-104">A maioria dos cenários de segurança pode ser satisfeita usando tipos de credenciais comuns, como Windows (Kerberos), nome de usuário e senhas e certificados.</span><span class="sxs-lookup"><span data-stu-id="37310-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="37310-105">No entanto, se um novo tipo de credencial for necessário, os tópicos nesta seção explicam como tratar e validar novos tipos.</span><span class="sxs-lookup"><span data-stu-id="37310-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37310-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="37310-106">In This Section</span></span>  

 [<span data-ttu-id="37310-107">Como: criar um serviço que utiliza um validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="37310-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="37310-108">Explica como personalizar a validação do WCF herdando da <xref:System.IdentityModel.Selectors.X509CertificateValidator> classe.</span><span class="sxs-lookup"><span data-stu-id="37310-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="37310-109">Passo a passo: criar credenciais de serviço e cliente personalizados</span><span class="sxs-lookup"><span data-stu-id="37310-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="37310-110">Demonstra como estender as <xref:System.ServiceModel.Description.ClientCredentials> classes e <xref:System.ServiceModel.Description.ServiceCredentials> para acomodar novos tipos de credencial.</span><span class="sxs-lookup"><span data-stu-id="37310-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="37310-111">Isso é primeiro em uma série de tópicos que permitem a criação de tipos de credenciais personalizados.</span><span class="sxs-lookup"><span data-stu-id="37310-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="37310-112">Como: criar um provedor de token de segurança personalizado</span><span class="sxs-lookup"><span data-stu-id="37310-112">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="37310-113">Explica como criar um provedor de token de segurança para lidar com novos tipos de credenciais e retornar novos tokens para a credencial.</span><span class="sxs-lookup"><span data-stu-id="37310-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="37310-114">Este é o segundo tópico da série.</span><span class="sxs-lookup"><span data-stu-id="37310-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="37310-115">Como: criar um autenticador de token de segurança personalizado</span><span class="sxs-lookup"><span data-stu-id="37310-115">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="37310-116">Explica como criar um autenticador personalizado para autenticar um novo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="37310-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="37310-117">Este é o terceiro tópico da série.</span><span class="sxs-lookup"><span data-stu-id="37310-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="37310-118">Referência</span><span class="sxs-lookup"><span data-stu-id="37310-118">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="37310-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="37310-119">Related Sections</span></span>  

 [<span data-ttu-id="37310-120">Autenticação</span><span class="sxs-lookup"><span data-stu-id="37310-120">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="37310-121">Federação e tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="37310-121">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="37310-122">Autorização</span><span class="sxs-lookup"><span data-stu-id="37310-122">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="37310-123">Veja também</span><span class="sxs-lookup"><span data-stu-id="37310-123">See also</span></span>

- [<span data-ttu-id="37310-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="37310-124">Security</span></span>](../feature-details/security.md)
