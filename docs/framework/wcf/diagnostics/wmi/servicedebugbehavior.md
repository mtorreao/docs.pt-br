---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: dba4abd74cdddeb2b641feec5902413fe0704b1f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262288"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="d6533-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d6533-102">ServiceDebugBehavior</span></span>

<span data-ttu-id="d6533-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d6533-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6533-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d6533-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d6533-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d6533-105">Methods</span></span>  

 <span data-ttu-id="d6533-106">A classe ServiceDebugBehavior não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="d6533-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d6533-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="d6533-107">Properties</span></span>  

 <span data-ttu-id="d6533-108">A classe ServiceDebugBehavior tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="d6533-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="d6533-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d6533-109">HttpHelpPageEnabled</span></span>  

 <span data-ttu-id="d6533-110">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="d6533-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d6533-111">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d6533-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6533-112">Controla se o serviço publica seu WSDL no endereço controlado pelo `HttpGetUrl` atributo.</span><span class="sxs-lookup"><span data-stu-id="d6533-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="d6533-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d6533-113">HttpHelpPageUrl</span></span>  

 <span data-ttu-id="d6533-114">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d6533-114">Data type: string</span></span>  
  
 <span data-ttu-id="d6533-115">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d6533-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6533-116">Define o local no qual o serviço WSDL é publicado para recuperação usando HTTP.</span><span class="sxs-lookup"><span data-stu-id="d6533-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="d6533-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d6533-117">HttpsHelpPageEnabled</span></span>  

 <span data-ttu-id="d6533-118">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="d6533-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d6533-119">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d6533-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6533-120">Controla se o serviço publica seu WSDL sobre HTTPS no endereço controlado pelo `HttpsGetUrl` atributo.</span><span class="sxs-lookup"><span data-stu-id="d6533-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="d6533-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d6533-121">HttpsHelpPageUrl</span></span>  

 <span data-ttu-id="d6533-122">Tipo de dados: cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d6533-122">Data type: string</span></span>  
  
 <span data-ttu-id="d6533-123">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d6533-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6533-124">Define o local no qual o serviço WSDL é publicado para recuperação usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d6533-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="d6533-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="d6533-125">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="d6533-126">Tipo de dados: booliano</span><span class="sxs-lookup"><span data-stu-id="d6533-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d6533-127">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="d6533-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d6533-128">Especifica se as informações de exceção gerenciadas devem ser incluídas nos detalhes de falhas de SOAP retornadas aos clientes para fins de depuração.</span><span class="sxs-lookup"><span data-stu-id="d6533-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6533-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6533-129">Requirements</span></span>  
  
|<span data-ttu-id="d6533-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d6533-130">MOF</span></span>|<span data-ttu-id="d6533-131">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="d6533-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d6533-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="d6533-132">Namespace</span></span>|<span data-ttu-id="d6533-133">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6533-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6533-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="d6533-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
