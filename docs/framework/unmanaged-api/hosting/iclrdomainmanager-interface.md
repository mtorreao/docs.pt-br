---
title: Interface ICLRDomainManager
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681165"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="c04ab-102">Interface ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="c04ab-102">ICLRDomainManager Interface</span></span>

<span data-ttu-id="c04ab-103">Permite que o host especifique o Gerenciador de domínio de aplicativo que será usado para inicializar o domínio de aplicativo padrão e para especificar as propriedades de inicialização.</span><span class="sxs-lookup"><span data-stu-id="c04ab-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c04ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c04ab-104">Methods</span></span>  
  
|<span data-ttu-id="c04ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="c04ab-105">Method</span></span>|<span data-ttu-id="c04ab-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="c04ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c04ab-107">Método SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="c04ab-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="c04ab-108">Especifica o tipo, derivado da <xref:System.AppDomainManager?displayProperty=nameWithType> classe, do Gerenciador de domínio de aplicativo que será usado para inicializar o domínio de aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="c04ab-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="c04ab-109">Método SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="c04ab-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="c04ab-110">Define as propriedades que serão usadas para inicializar o domínio de aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="c04ab-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c04ab-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="c04ab-111">Remarks</span></span>  

 <span data-ttu-id="c04ab-112">Para obter uma instância dessa interface, chame o método [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) com o tipo de Gerenciador IID `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="c04ab-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c04ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c04ab-113">Requirements</span></span>  

 <span data-ttu-id="c04ab-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c04ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c04ab-115">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="c04ab-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c04ab-116">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c04ab-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c04ab-117">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c04ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04ab-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="c04ab-118">See also</span></span>

- [<span data-ttu-id="c04ab-119">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="c04ab-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c04ab-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="c04ab-120">Hosting</span></span>](index.md)
