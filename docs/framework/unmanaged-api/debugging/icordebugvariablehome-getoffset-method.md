---
title: 'Método ICorDebugVariableHome:: GetOffset'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711787"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="4fdad-102">Método ICorDebugVariableHome:: GetOffset</span><span class="sxs-lookup"><span data-stu-id="4fdad-102">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="4fdad-103">Obtém o deslocamento do registro base de uma variável.</span><span class="sxs-lookup"><span data-stu-id="4fdad-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fdad-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4fdad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fdad-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4fdad-105">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="4fdad-106">fora O deslocamento do registro base.</span><span class="sxs-lookup"><span data-stu-id="4fdad-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fdad-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="4fdad-107">Return Value</span></span>  

 <span data-ttu-id="4fdad-108">O método retorna os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4fdad-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="4fdad-109">Valor</span><span class="sxs-lookup"><span data-stu-id="4fdad-109">Value</span></span>|<span data-ttu-id="4fdad-110">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4fdad-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="4fdad-111">A variável está em um local de memória relativa ao registro.</span><span class="sxs-lookup"><span data-stu-id="4fdad-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="4fdad-112">A variável não está em um local de memória relativa ao registro.</span><span class="sxs-lookup"><span data-stu-id="4fdad-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4fdad-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fdad-113">Requirements</span></span>  

 <span data-ttu-id="4fdad-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fdad-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fdad-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fdad-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fdad-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fdad-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fdad-117">**.NET Framework versões:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fdad-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdad-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fdad-118">See also</span></span>

- [<span data-ttu-id="4fdad-119">Interface ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="4fdad-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
