---
title: 'Método ICorDebugVariableHome:: getlocationtype'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 3979ed19f8a61ac1fc045b83c52e23d7255ac364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711865"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="cc2ea-102">Método ICorDebugVariableHome:: getlocationtype</span><span class="sxs-lookup"><span data-stu-id="cc2ea-102">ICorDebugVariableHome::GetLocationType Method</span></span>

<span data-ttu-id="cc2ea-103">Obtém o tipo do local nativo da variável.</span><span class="sxs-lookup"><span data-stu-id="cc2ea-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2ea-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc2ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc2ea-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc2ea-105">Parameters</span></span>  

 `pLocationType`  
 <span data-ttu-id="cc2ea-106">fora Um ponteiro para o tipo do local nativo da variável.</span><span class="sxs-lookup"><span data-stu-id="cc2ea-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="cc2ea-107">Consulte a enumeração [VariableLocationType](variablelocationtype-enumeration.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc2ea-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc2ea-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc2ea-108">Requirements</span></span>  

 <span data-ttu-id="cc2ea-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc2ea-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc2ea-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc2ea-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc2ea-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc2ea-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc2ea-112">**.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc2ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2ea-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc2ea-113">See also</span></span>

- [<span data-ttu-id="cc2ea-114">Interface ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="cc2ea-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="cc2ea-115">Enumeração VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="cc2ea-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
