---
title: Enumeração EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724319"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="00675-102">Enumeração EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="00675-102">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="00675-103">Permite que o host forneça o tempo de execução com informações sobre a inicialização de um domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="00675-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00675-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="00675-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="00675-105">Membros</span><span class="sxs-lookup"><span data-stu-id="00675-105">Members</span></span>  
  
|<span data-ttu-id="00675-106">Membro</span><span class="sxs-lookup"><span data-stu-id="00675-106">Member</span></span>|<span data-ttu-id="00675-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="00675-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="00675-108">Sem sinalizadores.</span><span class="sxs-lookup"><span data-stu-id="00675-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="00675-109">Informa ao Common Language Runtime (CLR) que o host não fará alterações no estado de segurança do domínio do aplicativo no <xref:System.AppDomainManager.InitializeNewDomain%2A> método.</span><span class="sxs-lookup"><span data-stu-id="00675-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00675-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="00675-110">Remarks</span></span>  

 <span data-ttu-id="00675-111">O método [ICLRDomainManager:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) usa um parâmetro do tipo `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="00675-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00675-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00675-112">Requirements</span></span>  

 <span data-ttu-id="00675-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00675-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00675-114">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00675-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00675-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00675-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00675-116">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00675-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00675-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="00675-117">See also</span></span>

- [<span data-ttu-id="00675-118">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="00675-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="00675-119">Método SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="00675-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
