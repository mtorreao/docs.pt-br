---
title: Enumeração CLSID_RESOLUTION_FLAGS
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706158"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="da5c8-102">Enumeração CLSID_RESOLUTION_FLAGS</span><span class="sxs-lookup"><span data-stu-id="da5c8-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="da5c8-103">Contém valores que indicam como o Common Language Runtime (CLR) deve resolver um `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="da5c8-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da5c8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="da5c8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="da5c8-105">Membros</span><span class="sxs-lookup"><span data-stu-id="da5c8-105">Members</span></span>  
  
|<span data-ttu-id="da5c8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="da5c8-106">Member</span></span>|<span data-ttu-id="da5c8-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="da5c8-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="da5c8-108">Indica o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="da5c8-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="da5c8-109">Indica que o tempo de execução pesquisa o registro e aplica a política Shim.</span><span class="sxs-lookup"><span data-stu-id="da5c8-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da5c8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da5c8-110">Requirements</span></span>  

 <span data-ttu-id="da5c8-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da5c8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da5c8-112">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="da5c8-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da5c8-113">**.NET Framework versões:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da5c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5c8-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="da5c8-114">See also</span></span>

- [<span data-ttu-id="da5c8-115">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="da5c8-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
