---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273250"
---
# <a name="serviceappdomain"></a><span data-ttu-id="709e4-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="709e4-102">ServiceAppDomain</span></span>

<span data-ttu-id="709e4-103">Mapeia um serviço para um domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="709e4-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="709e4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="709e4-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="709e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="709e4-105">Methods</span></span>  

 <span data-ttu-id="709e4-106">A classe imappdomain não define nenhum método.</span><span class="sxs-lookup"><span data-stu-id="709e4-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="709e4-107">Propriedades</span><span class="sxs-lookup"><span data-stu-id="709e4-107">Properties</span></span>  

 <span data-ttu-id="709e4-108">A classe imappdomain tem as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="709e4-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="709e4-109">ref</span><span class="sxs-lookup"><span data-stu-id="709e4-109">ref</span></span>  

 <span data-ttu-id="709e4-110">Tipo de dados: serviço</span><span class="sxs-lookup"><span data-stu-id="709e4-110">Data type: Service</span></span>  
<span data-ttu-id="709e4-111">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="709e4-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="709e4-112">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="709e4-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="709e4-113">O serviço deste domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="709e4-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="709e4-114">ref</span><span class="sxs-lookup"><span data-stu-id="709e4-114">ref</span></span>  

 <span data-ttu-id="709e4-115">Tipo de dados: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="709e4-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="709e4-116">Qualificadores: Chave</span><span class="sxs-lookup"><span data-stu-id="709e4-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="709e4-117">Tipo de acesso: Somente leitura</span><span class="sxs-lookup"><span data-stu-id="709e4-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="709e4-118">Contém as propriedades do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="709e4-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="709e4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="709e4-119">Requirements</span></span>  
  
|<span data-ttu-id="709e4-120">MOF</span><span class="sxs-lookup"><span data-stu-id="709e4-120">MOF</span></span>|<span data-ttu-id="709e4-121">Declarado em ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="709e4-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="709e4-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="709e4-122">Namespace</span></span>|<span data-ttu-id="709e4-123">Definido em root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="709e4-123">Defined in root\ServiceModel</span></span>|
