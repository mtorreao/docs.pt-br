---
title: 'Método ICorDebugVariableHome:: getregister'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711748"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="27464-102">Método ICorDebugVariableHome:: getregister</span><span class="sxs-lookup"><span data-stu-id="27464-102">ICorDebugVariableHome::GetRegister Method</span></span>

<span data-ttu-id="27464-103">Obtém o registro que contém uma variável com um tipo de local de `VLT_REGISTER` e o registro base para uma variável com um tipo de local de `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="27464-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27464-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="27464-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27464-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="27464-105">Parameters</span></span>  

 `pRegister`  
 <span data-ttu-id="27464-106">fora Um valor de enumeração CorDebugRegister que indica o registro para uma variável com um tipo de local de `VLT_REGISTER` e o registro base para uma variável com um tipo de local de `VLT_REGISTER_RELATIVE` .</span><span class="sxs-lookup"><span data-stu-id="27464-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27464-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="27464-107">Return Value</span></span>  

 <span data-ttu-id="27464-108">O método retorna os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="27464-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="27464-109">Valor</span><span class="sxs-lookup"><span data-stu-id="27464-109">Value</span></span>|<span data-ttu-id="27464-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="27464-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="27464-111">A variável está no registro indicado pelo `pRegister` argumento.</span><span class="sxs-lookup"><span data-stu-id="27464-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="27464-112">A variável não está em um local de registro ou relativo ao registro.</span><span class="sxs-lookup"><span data-stu-id="27464-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27464-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27464-113">Requirements</span></span>  

 <span data-ttu-id="27464-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27464-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27464-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27464-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27464-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27464-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27464-117">**.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27464-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27464-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="27464-118">See also</span></span>

- [<span data-ttu-id="27464-119">Enumeração VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="27464-119">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
- [<span data-ttu-id="27464-120">Interface ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="27464-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
