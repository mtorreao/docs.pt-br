---
title: Método ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: a7d78daf74d3cc01c2313f092bce53950dbd7bfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681217"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="0f836-102">Método ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0f836-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>

<span data-ttu-id="0f836-103">Obtém o contexto do thread atual.</span><span class="sxs-lookup"><span data-stu-id="0f836-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f836-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0f836-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f836-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0f836-105">Parameters</span></span>  

 `contextSize`  
 <span data-ttu-id="0f836-106">no O tamanho, em bytes, da `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="0f836-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="0f836-107">[entrada, saída] Uma matriz de bytes que compõe a estrutura do Win32 `CONTEXT` para a plataforma atual.</span><span class="sxs-lookup"><span data-stu-id="0f836-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f836-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="0f836-108">Remarks</span></span>  

 <span data-ttu-id="0f836-109">O depurador deve chamar essa função em vez da função do Win32 `GetThreadContext` , pois o thread pode estar em um estado "seqüestrado" em que seu contexto foi alterado temporariamente.</span><span class="sxs-lookup"><span data-stu-id="0f836-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="0f836-110">Os dados retornados são uma `CONTEXT` estrutura Win32 para a plataforma atual.</span><span class="sxs-lookup"><span data-stu-id="0f836-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="0f836-111">Para quadros não folha, os clientes devem verificar quais registros são válidos usando [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f836-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f836-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f836-112">Requirements</span></span>  

 <span data-ttu-id="0f836-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f836-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f836-114">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f836-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f836-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f836-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f836-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f836-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f836-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="0f836-117">See also</span></span>

- [<span data-ttu-id="0f836-118">Interface ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="0f836-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="0f836-119">Interface ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="0f836-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
