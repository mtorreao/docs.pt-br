---
title: Enumeração CorNativeLinkFlags
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: ef9b177bee0651b6b8ea994610315ce93524e8e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676927"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="d49c9-102">Enumeração CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="d49c9-102">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="d49c9-103">Fornece valores de sinalizador usados pelo vinculador ao vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="d49c9-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d49c9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d49c9-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d49c9-105">Membros</span><span class="sxs-lookup"><span data-stu-id="d49c9-105">Members</span></span>  
  
|<span data-ttu-id="d49c9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d49c9-106">Member</span></span>|<span data-ttu-id="d49c9-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d49c9-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="d49c9-108">Indica que não há sinalizadores.</span><span class="sxs-lookup"><span data-stu-id="d49c9-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="d49c9-109">Indica uma `setLastError` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="d49c9-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="d49c9-110">Indica uma `nomangle` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="d49c9-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="d49c9-111">Não usado.</span><span class="sxs-lookup"><span data-stu-id="d49c9-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d49c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d49c9-112">Requirements</span></span>  

 <span data-ttu-id="d49c9-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d49c9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d49c9-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d49c9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d49c9-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d49c9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d49c9-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d49c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d49c9-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="d49c9-117">See also</span></span>

- [<span data-ttu-id="d49c9-118">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="d49c9-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
