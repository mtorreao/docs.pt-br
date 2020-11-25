---
title: Enumeração CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: 1d1b0cbb8be33f285b63e7353da973455e0fd752
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718846"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="1ec72-102">Enumeração CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="1ec72-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>

<span data-ttu-id="1ec72-103">Contém valores de sinalizador que indicam as condições sob as quais uma mensagem de erro deve ser gerada quando os metadados são emitidos fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ec72-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1ec72-104">Syntax</span></span>  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="1ec72-105">Membros</span><span class="sxs-lookup"><span data-stu-id="1ec72-105">Members</span></span>  
  
|<span data-ttu-id="1ec72-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1ec72-106">Member</span></span>|<span data-ttu-id="1ec72-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1ec72-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="1ec72-108">Indica o comportamento padrão, que não gera mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="1ec72-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="1ec72-109">Indica que o compilador não deve gerar mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="1ec72-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="1ec72-110">Indica que o compilador deve gerar uma mensagem de erro quando um campo, propriedade, evento, método ou parâmetro for emitido fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="1ec72-111">Indica que o compilador deve gerar uma mensagem de erro quando um método é emitido fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="1ec72-112">Indica que o compilador deve gerar uma mensagem de erro quando um campo é emitido fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="1ec72-113">Indica que o compilador deve gerar uma mensagem de erro quando um parâmetro é emitido fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="1ec72-114">Indica que o compilador deve gerar uma mensagem de erro quando uma propriedade é emitida fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="1ec72-115">Indica que o compilador deve gerar uma mensagem de erro quando um evento é emitido fora de ordem.</span><span class="sxs-lookup"><span data-stu-id="1ec72-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ec72-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ec72-116">Requirements</span></span>  

 <span data-ttu-id="1ec72-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ec72-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ec72-118">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="1ec72-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1ec72-119">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ec72-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec72-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="1ec72-120">See also</span></span>

- [<span data-ttu-id="1ec72-121">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="1ec72-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
