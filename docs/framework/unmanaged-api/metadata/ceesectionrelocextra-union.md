---
title: CeeSectionRelocExtra União
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d5f61aa9b4a65a5f33e64aa4441370c3f7ca5b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732717"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="fb4dc-102">CeeSectionRelocExtra União</span><span class="sxs-lookup"><span data-stu-id="fb4dc-102">CeeSectionRelocExtra Union</span></span>

<span data-ttu-id="fb4dc-103">Representa um deslocamento de endereço que é usado pela interface [ICeeGen](iceegen-interface.md) para realocar uma seção.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb4dc-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fb4dc-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="fb4dc-105">Membros</span><span class="sxs-lookup"><span data-stu-id="fb4dc-105">Members</span></span>  
  
|<span data-ttu-id="fb4dc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="fb4dc-106">Member</span></span>|<span data-ttu-id="fb4dc-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="fb4dc-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="fb4dc-108">O ajuste de endereço superior para a seção.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb4dc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb4dc-109">Requirements</span></span>  

 <span data-ttu-id="fb4dc-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb4dc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb4dc-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb4dc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb4dc-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb4dc-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb4dc-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb4dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4dc-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="fb4dc-114">See also</span></span>

- [<span data-ttu-id="fb4dc-115">Uniões de metadados</span><span class="sxs-lookup"><span data-stu-id="fb4dc-115">Metadata Unions</span></span>](metadata-unions.md)
