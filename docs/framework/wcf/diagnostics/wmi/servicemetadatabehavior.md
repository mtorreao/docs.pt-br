---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262275"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="232a1-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="232a1-102">ServiceMetadataBehavior</span></span>

<span data-ttu-id="232a1-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="232a1-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232a1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="232a1-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="232a1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="232a1-105">Methods</span></span>  

 <span data-ttu-id="232a1-106">A classe ServiceMetadataBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="232a1-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="232a1-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="232a1-107">Properties</span></span>  

 <span data-ttu-id="232a1-108">A classe ServiceMetadataBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="232a1-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="232a1-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="232a1-109">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="232a1-110">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="232a1-110">Data type: string</span></span>  
  
 <span data-ttu-id="232a1-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="232a1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="232a1-112">Define o local para o qual o serviço redireciona solicitações de metadados.</span><span class="sxs-lookup"><span data-stu-id="232a1-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="232a1-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="232a1-113">HttpGetEnabled</span></span>  

 <span data-ttu-id="232a1-114">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="232a1-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="232a1-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="232a1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="232a1-116">Controla se o serviço publica seu WSDL no endereço controlado pelo `HttpGetUrl` atributo.</span><span class="sxs-lookup"><span data-stu-id="232a1-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="232a1-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="232a1-117">HttpGetUrl</span></span>  

 <span data-ttu-id="232a1-118">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="232a1-118">Data type: string</span></span>  
  
 <span data-ttu-id="232a1-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="232a1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="232a1-120">Define o local no qual o serviço WSDL é publicado para recuperação usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="232a1-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="232a1-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="232a1-121">HttpsGetEnabled</span></span>  

 <span data-ttu-id="232a1-122">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="232a1-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="232a1-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="232a1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="232a1-124">Controla se o serviço publica seu WSDL sobre HTTPS no endereço controlado pelo `HttpsGetUrl` atributo.</span><span class="sxs-lookup"><span data-stu-id="232a1-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="232a1-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="232a1-125">HttpsGetUrl</span></span>  

 <span data-ttu-id="232a1-126">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="232a1-126">Data type: string</span></span>  
  
 <span data-ttu-id="232a1-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="232a1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="232a1-128">Define o local no qual o serviço WSDL é publicado para recuperação usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="232a1-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232a1-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="232a1-129">Requirements</span></span>  
  
|<span data-ttu-id="232a1-130">MOF</span><span class="sxs-lookup"><span data-stu-id="232a1-130">MOF</span></span>|<span data-ttu-id="232a1-131">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="232a1-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="232a1-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="232a1-132">Namespace</span></span>|<span data-ttu-id="232a1-133">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="232a1-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="232a1-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="232a1-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
