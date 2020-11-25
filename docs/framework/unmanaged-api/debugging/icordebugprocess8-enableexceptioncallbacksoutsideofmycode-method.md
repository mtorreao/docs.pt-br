---
title: Método ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 750d2a2d69c74e147c34c9c496079ee48ac04b42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732535"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="4dec6-102">Método ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode</span><span class="sxs-lookup"><span data-stu-id="4dec6-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>

<span data-ttu-id="4dec6-103">[Com suporte no .NET Framework 4,6 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="4dec6-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="4dec6-104">Habilita ou desabilita determinados tipos de retornos de chamada de exceção [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4dec6-104">Enables or disables certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dec6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dec6-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dec6-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4dec6-106">Parameters</span></span>  

 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="4dec6-107">[in]</span><span class="sxs-lookup"><span data-stu-id="4dec6-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dec6-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="4dec6-108">Remarks</span></span>  

 <span data-ttu-id="4dec6-109">Se o valor de `enableExceptionsOutsideOfJMC` for `false` :</span><span class="sxs-lookup"><span data-stu-id="4dec6-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
- <span data-ttu-id="4dec6-110">Uma exceção DEBUG_EXCEPTION_FIRST_CHANCE não resultará em um retorno de chamada para o depurador.</span><span class="sxs-lookup"><span data-stu-id="4dec6-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
- <span data-ttu-id="4dec6-111">Uma exceção de DEBUG_EXCEPTION_CATCH_HANDLER_FOUND não resultará em um retorno de chamada para o depurador se a exceção nunca sair do código do usuário (ou seja, o caminho de uma origem de exceção para um manipulador de exceção não tem nenhum método marcado como JustMyCode ou JMC).</span><span class="sxs-lookup"><span data-stu-id="4dec6-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="4dec6-112">O valor padrão de `enableExceptionsOutsideOfJMC` é `true`.</span><span class="sxs-lookup"><span data-stu-id="4dec6-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dec6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dec6-113">Requirements</span></span>  

 <span data-ttu-id="4dec6-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dec6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dec6-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dec6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dec6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dec6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dec6-117">**.NET Framework versões:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dec6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dec6-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="4dec6-118">See also</span></span>

- [<span data-ttu-id="4dec6-119">Interface ICorDebugProcess8</span><span class="sxs-lookup"><span data-stu-id="4dec6-119">ICorDebugProcess8 Interface</span></span>](icordebugprocess8-interface.md)
- [<span data-ttu-id="4dec6-120">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="4dec6-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
