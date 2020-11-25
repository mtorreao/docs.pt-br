---
title: Enumeração CorSetENC
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705976"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="8c189-102">Enumeração CorSetENC</span><span class="sxs-lookup"><span data-stu-id="8c189-102">CorSetENC Enumeration</span></span>

<span data-ttu-id="8c189-103">Contém valores usados para influenciar o comportamento durante a geração de metadados.</span><span class="sxs-lookup"><span data-stu-id="8c189-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c189-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c189-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="8c189-105">Membros</span><span class="sxs-lookup"><span data-stu-id="8c189-105">Members</span></span>  
  
|<span data-ttu-id="8c189-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8c189-106">Member</span></span>|<span data-ttu-id="8c189-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8c189-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="8c189-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8c189-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="8c189-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8c189-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="8c189-110">Indica que, enquanto os metadados podem ser atualizados, os tokens não podem ser movidos.</span><span class="sxs-lookup"><span data-stu-id="8c189-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="8c189-111">Indica que os tokens podem ser movidos durante as atualizações.</span><span class="sxs-lookup"><span data-stu-id="8c189-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="8c189-112">Indica que as atualizações podem consistir apenas em adições.</span><span class="sxs-lookup"><span data-stu-id="8c189-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="8c189-113">Tokens não podem ser movidos.</span><span class="sxs-lookup"><span data-stu-id="8c189-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="8c189-114">Indica que a compilação é incremental.</span><span class="sxs-lookup"><span data-stu-id="8c189-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="8c189-115">Indica que somente os metadados alterados devem ser salvos.</span><span class="sxs-lookup"><span data-stu-id="8c189-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="8c189-116">Inclui `MDUpdateENC` o `MDUpdateFull` e o `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="8c189-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c189-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c189-117">Requirements</span></span>  

 <span data-ttu-id="8c189-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c189-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c189-119">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="8c189-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8c189-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c189-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c189-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c189-121">See also</span></span>

- [<span data-ttu-id="8c189-122">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="8c189-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
