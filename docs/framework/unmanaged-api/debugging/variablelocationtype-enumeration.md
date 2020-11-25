---
title: Enumeração VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725255"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="225ab-102">Enumeração VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="225ab-102">VariableLocationType Enumeration</span></span>

<span data-ttu-id="225ab-103">Indica o tipo de local nativo de uma variável.</span><span class="sxs-lookup"><span data-stu-id="225ab-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="225ab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="225ab-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="225ab-105">Membros</span><span class="sxs-lookup"><span data-stu-id="225ab-105">Members</span></span>  
  
|<span data-ttu-id="225ab-106">Membro</span><span class="sxs-lookup"><span data-stu-id="225ab-106">Member</span></span>|<span data-ttu-id="225ab-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="225ab-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="225ab-108">A variável está em um registro.</span><span class="sxs-lookup"><span data-stu-id="225ab-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="225ab-109">A variável está em um local de memória relativa ao registro.</span><span class="sxs-lookup"><span data-stu-id="225ab-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="225ab-110">A variável não é armazenada em um local de memória de registro ou de registro relativo.</span><span class="sxs-lookup"><span data-stu-id="225ab-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="225ab-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="225ab-111">Remarks</span></span>  

 <span data-ttu-id="225ab-112">Um membro da `VariableLocationType` enumeração é retornado pelo método [ICorDebugVariableHome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="225ab-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="225ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="225ab-113">Requirements</span></span>  

 <span data-ttu-id="225ab-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="225ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="225ab-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="225ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="225ab-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="225ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="225ab-117">**.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="225ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225ab-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="225ab-118">See also</span></span>

- [<span data-ttu-id="225ab-119">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="225ab-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
