---
title: Método ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723461"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="b444f-102">Método ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="b444f-102">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="b444f-103">Anexa o depurador a um processo existente.</span><span class="sxs-lookup"><span data-stu-id="b444f-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b444f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b444f-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b444f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b444f-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="b444f-106">no A ID do processo ao qual o depurador deve ser anexado.</span><span class="sxs-lookup"><span data-stu-id="b444f-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="b444f-107">no Valor booliano definido como `true` se o depurador deve se comportar como o depurador do Win32 para o processo e expedir os retornos de chamada não gerenciados; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="b444f-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b444f-108">fora Um ponteiro para o endereço de um objeto "ICorDebugProcess" que representa o processo ao qual o depurador foi anexado.</span><span class="sxs-lookup"><span data-stu-id="b444f-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b444f-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="b444f-109">Remarks</span></span>  

 <span data-ttu-id="b444f-110">Não há suporte para depuração de interoperabilidade em plataformas Win9x e não x86, como plataformas baseadas em IA-64 e AMD64.</span><span class="sxs-lookup"><span data-stu-id="b444f-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b444f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b444f-111">Requirements</span></span>  

 <span data-ttu-id="b444f-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b444f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b444f-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b444f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b444f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b444f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b444f-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b444f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b444f-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="b444f-116">See also</span></span>

- [<span data-ttu-id="b444f-117">Interface ICorDebug</span><span class="sxs-lookup"><span data-stu-id="b444f-117">ICorDebug Interface</span></span>](icordebug-interface.md)
