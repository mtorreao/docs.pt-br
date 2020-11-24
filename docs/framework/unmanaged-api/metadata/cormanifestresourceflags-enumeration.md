---
title: Enumeração CorManifestResourceFlags
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
ms.openlocfilehash: f8334cb44042e21c086bc05c723e99b0c079fa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677057"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="30e93-102">Enumeração CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="30e93-102">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="30e93-103">Indica a visibilidade dos recursos codificados em um manifesto do assembly.</span><span class="sxs-lookup"><span data-stu-id="30e93-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e93-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30e93-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="30e93-105">Membros</span><span class="sxs-lookup"><span data-stu-id="30e93-105">Members</span></span>  
  
|<span data-ttu-id="30e93-106">Membro</span><span class="sxs-lookup"><span data-stu-id="30e93-106">Member</span></span>|<span data-ttu-id="30e93-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="30e93-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="30e93-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="30e93-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="30e93-109">Os recursos são públicos.</span><span class="sxs-lookup"><span data-stu-id="30e93-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="30e93-110">Os recursos são privados.</span><span class="sxs-lookup"><span data-stu-id="30e93-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30e93-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30e93-111">Requirements</span></span>  

 <span data-ttu-id="30e93-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e93-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e93-113">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="30e93-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="30e93-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30e93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e93-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="30e93-115">See also</span></span>

- [<span data-ttu-id="30e93-116">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="30e93-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
