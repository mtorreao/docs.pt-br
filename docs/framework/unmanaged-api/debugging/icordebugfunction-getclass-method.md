---
title: Método ICorDebugFunction::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 40cb59a2ad0539764702369b13d632eddbab8174
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728154"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="b9b57-102">Método ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="b9b57-102">ICorDebugFunction::GetClass Method</span></span>

<span data-ttu-id="b9b57-103">Obtém um objeto ICorDebugClass que representa a classe da qual essa função é membro.</span><span class="sxs-lookup"><span data-stu-id="b9b57-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b57-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b9b57-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b57-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b9b57-105">Parameters</span></span>  

 `ppClass`  
 <span data-ttu-id="b9b57-106">fora Um ponteiro para o endereço do `ICorDebugClass` objeto que representa a classe, ou NULL, se essa função não for um membro de uma classe.</span><span class="sxs-lookup"><span data-stu-id="b9b57-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b57-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9b57-107">Requirements</span></span>  

 <span data-ttu-id="b9b57-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b57-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b57-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9b57-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9b57-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b57-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9b57-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b57-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
