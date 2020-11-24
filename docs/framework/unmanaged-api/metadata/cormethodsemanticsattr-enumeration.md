---
title: Enumeração CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 347b323951b0125ffa5f82626b2d9b235079492c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676940"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="f531c-102">Enumeração CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="f531c-102">CorMethodSemanticsAttr Enumeration</span></span>

<span data-ttu-id="f531c-103">Contém valores que descrevem a relação entre um método e uma propriedade ou evento associado.</span><span class="sxs-lookup"><span data-stu-id="f531c-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f531c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f531c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f531c-105">Membros</span><span class="sxs-lookup"><span data-stu-id="f531c-105">Members</span></span>  
  
|<span data-ttu-id="f531c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f531c-106">Member</span></span>|<span data-ttu-id="f531c-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f531c-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="f531c-108">Especifica que o método é um `set` acessador para uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="f531c-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="f531c-109">Especifica que o método é um `get` acessador para uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="f531c-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="f531c-110">Especifica que o método tem uma relação com uma propriedade ou um evento diferente daqueles definidos aqui.</span><span class="sxs-lookup"><span data-stu-id="f531c-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="f531c-111">Especifica que o método adiciona métodos de manipulador para um evento.</span><span class="sxs-lookup"><span data-stu-id="f531c-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="f531c-112">Especifica que o método Remove métodos de manipulador para um evento.</span><span class="sxs-lookup"><span data-stu-id="f531c-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="f531c-113">Especifica que o método gera um evento.</span><span class="sxs-lookup"><span data-stu-id="f531c-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f531c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f531c-114">Requirements</span></span>  

 <span data-ttu-id="f531c-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f531c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f531c-116">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f531c-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f531c-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f531c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f531c-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="f531c-118">See also</span></span>

- [<span data-ttu-id="f531c-119">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="f531c-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
