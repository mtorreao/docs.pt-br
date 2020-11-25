---
title: Método ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 0cfc734e3c2d250bba045a926f5b178b6cbc1ba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728193"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="2e994-102">Método ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="2e994-102">ICorDebugFrame::GetStackRange Method</span></span>

<span data-ttu-id="2e994-103">Obtém o intervalo de endereços absoluto deste quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="2e994-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e994-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2e994-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e994-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2e994-105">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="2e994-106">fora Um ponteiro para um `CORDB_ADDRESS` que especifica o endereço inicial do quadro de pilha representado por esse `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="2e994-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="2e994-107">fora Um ponteiro para um `CORDB_ADDRESS` que especifica o endereço final do quadro de pilha representado por esse `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="2e994-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e994-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="2e994-108">Remarks</span></span>  

 <span data-ttu-id="2e994-109">O intervalo de endereços da pilha é útil para compondo juntos rastreamentos de pilha intercalados coletados de vários mecanismos de depuração.</span><span class="sxs-lookup"><span data-stu-id="2e994-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="2e994-110">O intervalo numérico não fornece informações sobre o conteúdo do quadro de pilhas.</span><span class="sxs-lookup"><span data-stu-id="2e994-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="2e994-111">Só é significativo para a comparação de locais de quadros de pilhas.</span><span class="sxs-lookup"><span data-stu-id="2e994-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e994-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e994-112">Requirements</span></span>  

 <span data-ttu-id="2e994-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e994-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e994-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e994-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e994-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e994-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e994-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e994-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
