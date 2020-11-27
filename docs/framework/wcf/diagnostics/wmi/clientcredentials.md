---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c63e1b3de464b306f46e2f0935b1208d7262925a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274186"
---
# <a name="clientcredentials"></a><span data-ttu-id="c9be6-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="c9be6-102">ClientCredentials</span></span>

<span data-ttu-id="c9be6-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="c9be6-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9be6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c9be6-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c9be6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c9be6-105">Methods</span></span>  

 <span data-ttu-id="c9be6-106">A classe ClientCredentials não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="c9be6-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c9be6-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="c9be6-107">Properties</span></span>  

 <span data-ttu-id="c9be6-108">A classe ClientCredentials tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c9be6-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="c9be6-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c9be6-109">ClientCertificate</span></span>  

 <span data-ttu-id="c9be6-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-110">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-112">O certificado X. 509 que o cliente usa para se autenticar no serviço.</span><span class="sxs-lookup"><span data-stu-id="c9be6-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="c9be6-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="c9be6-113">HttpDigest</span></span>  

 <span data-ttu-id="c9be6-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-114">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-116">A credencial de Resumo de http atual.</span><span class="sxs-lookup"><span data-stu-id="c9be6-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="c9be6-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="c9be6-117">IssuedToken</span></span>  

 <span data-ttu-id="c9be6-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-118">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-120">O endereço do ponto de extremidade e a associação usados para contatar o serviço de token de segurança local.</span><span class="sxs-lookup"><span data-stu-id="c9be6-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="c9be6-121">Par</span><span class="sxs-lookup"><span data-stu-id="c9be6-121">Peer</span></span>  

 <span data-ttu-id="c9be6-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-122">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-124">As credenciais que o nó par usa para se autenticar em outros nós na malha.</span><span class="sxs-lookup"><span data-stu-id="c9be6-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="c9be6-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="c9be6-125">ServiceCertificate</span></span>  

 <span data-ttu-id="c9be6-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-126">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-128">O certificado X. 509 do serviço.</span><span class="sxs-lookup"><span data-stu-id="c9be6-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="c9be6-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="c9be6-129">SupportInteractive</span></span>  

 <span data-ttu-id="c9be6-130">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="c9be6-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="c9be6-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-132">Um valor booliano que especifica se a credencial dá suporte à negociação interativa.</span><span class="sxs-lookup"><span data-stu-id="c9be6-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="c9be6-133">UserName</span><span class="sxs-lookup"><span data-stu-id="c9be6-133">UserName</span></span>  

 <span data-ttu-id="c9be6-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-134">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-136">O nome de usuário e a senha que o cliente usa para se autenticar no serviço.</span><span class="sxs-lookup"><span data-stu-id="c9be6-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="c9be6-137">Windows</span><span class="sxs-lookup"><span data-stu-id="c9be6-137">Windows</span></span>  

 <span data-ttu-id="c9be6-138">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c9be6-138">Data type: string</span></span>  
  
 <span data-ttu-id="c9be6-139">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c9be6-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9be6-140">As credenciais do Windows que o cliente usa para se autenticar no serviço.</span><span class="sxs-lookup"><span data-stu-id="c9be6-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9be6-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9be6-141">Requirements</span></span>  
  
|<span data-ttu-id="c9be6-142">MOF</span><span class="sxs-lookup"><span data-stu-id="c9be6-142">MOF</span></span>|<span data-ttu-id="c9be6-143">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="c9be6-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c9be6-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="c9be6-144">Namespace</span></span>|<span data-ttu-id="c9be6-145">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c9be6-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9be6-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="c9be6-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
