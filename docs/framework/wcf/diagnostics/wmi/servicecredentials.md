---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262301"
---
# <a name="servicecredentials"></a><span data-ttu-id="a9eec-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="a9eec-102">ServiceCredentials</span></span>

<span data-ttu-id="a9eec-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="a9eec-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9eec-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a9eec-104">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a9eec-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9eec-105">Methods</span></span>  

 <span data-ttu-id="a9eec-106">A classe ServiceCredentials não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="a9eec-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a9eec-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a9eec-107">Properties</span></span>  

 <span data-ttu-id="a9eec-108">A classe ServiceCredentials tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="a9eec-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="a9eec-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="a9eec-109">ClientCertificate</span></span>  

 <span data-ttu-id="a9eec-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-110">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-112">As configurações de autenticação e provisionamento de certificado do cliente para este serviço.</span><span class="sxs-lookup"><span data-stu-id="a9eec-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="a9eec-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="a9eec-113">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="a9eec-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-114">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-116">As configurações de autenticação de token emitidas atuais para este serviço.</span><span class="sxs-lookup"><span data-stu-id="a9eec-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="a9eec-117">Par</span><span class="sxs-lookup"><span data-stu-id="a9eec-117">Peer</span></span>  

 <span data-ttu-id="a9eec-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-118">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-120">As configurações atuais de autenticação e provisionamento de credencial a serem usadas por pontos de extremidade de transporte pares.</span><span class="sxs-lookup"><span data-stu-id="a9eec-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="a9eec-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="a9eec-121">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="a9eec-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-122">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-124">Especifica as configurações atuais de conversa segura.</span><span class="sxs-lookup"><span data-stu-id="a9eec-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="a9eec-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="a9eec-125">ServiceCertificate</span></span>  

 <span data-ttu-id="a9eec-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-126">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-128">O certificado associado a este serviço.</span><span class="sxs-lookup"><span data-stu-id="a9eec-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="a9eec-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="a9eec-129">UserNameAuthentication</span></span>  

 <span data-ttu-id="a9eec-130">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-130">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-131">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-132">As configurações de nome de usuário/senha para este serviço.</span><span class="sxs-lookup"><span data-stu-id="a9eec-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="a9eec-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="a9eec-133">WindowsAuthentication</span></span>  

 <span data-ttu-id="a9eec-134">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a9eec-134">Data type: string</span></span>  
  
 <span data-ttu-id="a9eec-135">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a9eec-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a9eec-136">As configurações de autenticação do Windows para este serviço.</span><span class="sxs-lookup"><span data-stu-id="a9eec-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9eec-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9eec-137">Requirements</span></span>  
  
|<span data-ttu-id="a9eec-138">MOF</span><span class="sxs-lookup"><span data-stu-id="a9eec-138">MOF</span></span>|<span data-ttu-id="a9eec-139">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="a9eec-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a9eec-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="a9eec-140">Namespace</span></span>|<span data-ttu-id="a9eec-141">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a9eec-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9eec-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9eec-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
