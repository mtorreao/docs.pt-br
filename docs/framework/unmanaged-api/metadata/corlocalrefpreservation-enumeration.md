---
title: Enumeração CorLocalRefPreservation
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 49b0298f4fa776c93f89ac380ce65568b493379b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677109"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="bec61-102">Enumeração CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="bec61-102">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="bec61-103">Contém valores de sinalizador para o tratamento de referências locais.</span><span class="sxs-lookup"><span data-stu-id="bec61-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec61-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bec61-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="bec61-105">Membros</span><span class="sxs-lookup"><span data-stu-id="bec61-105">Members</span></span>  
  
|<span data-ttu-id="bec61-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bec61-106">Member</span></span>|<span data-ttu-id="bec61-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="bec61-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="bec61-108">Não preservar referências locais.</span><span class="sxs-lookup"><span data-stu-id="bec61-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="bec61-109">Preserve referências de tipo local.</span><span class="sxs-lookup"><span data-stu-id="bec61-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="bec61-110">Preserve referências de membro local.</span><span class="sxs-lookup"><span data-stu-id="bec61-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bec61-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bec61-111">Requirements</span></span>  

 <span data-ttu-id="bec61-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bec61-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bec61-113">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="bec61-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bec61-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bec61-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec61-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="bec61-115">See also</span></span>

- [<span data-ttu-id="bec61-116">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="bec61-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
