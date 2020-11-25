---
title: Estrutura COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724163"
---
# <a name="cor_native_link-structure"></a><span data-ttu-id="26e6a-102">Estrutura COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="26e6a-102">COR_NATIVE_LINK Structure</span></span>

<span data-ttu-id="26e6a-103">Contém informações que são usadas para vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="26e6a-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e6a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26e6a-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="26e6a-105">Membros</span><span class="sxs-lookup"><span data-stu-id="26e6a-105">Members</span></span>  
  
|<span data-ttu-id="26e6a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="26e6a-106">Member</span></span>|<span data-ttu-id="26e6a-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="26e6a-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="26e6a-108">O tipo a ser vinculado em código nativo.</span><span class="sxs-lookup"><span data-stu-id="26e6a-108">The type to be linked in native code.</span></span> <span data-ttu-id="26e6a-109">Esse valor é um dos valores de [CorNativeLinkType](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="26e6a-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="26e6a-110">Sinalizadores usados pelo vinculador ao vincular código nativo.</span><span class="sxs-lookup"><span data-stu-id="26e6a-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="26e6a-111">Esse valor é um dos valores de [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="26e6a-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="26e6a-112">O token de metadados de MemberRef que representa o ponto de entrada.</span><span class="sxs-lookup"><span data-stu-id="26e6a-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="26e6a-113">O formato é `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="26e6a-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26e6a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e6a-114">Requirements</span></span>  

 <span data-ttu-id="26e6a-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e6a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e6a-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="26e6a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26e6a-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26e6a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="26e6a-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e6a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e6a-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="26e6a-119">See also</span></span>

- [<span data-ttu-id="26e6a-120">Estruturas de metadados</span><span class="sxs-lookup"><span data-stu-id="26e6a-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="26e6a-121">Enumeração CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="26e6a-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="26e6a-122">Enumeração CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="26e6a-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)
