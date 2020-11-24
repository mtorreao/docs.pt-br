---
title: Método ICorDebugThread::EnumerateChains
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 76b231f00651186518d3bccfafa5780f258c4f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688179"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="63a74-102">Método ICorDebugThread::EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="63a74-102">ICorDebugThread::EnumerateChains Method</span></span>

<span data-ttu-id="63a74-103">Obtém um ponteiro de interface para um enumerador ICorDebugChainEnum que contém todas as cadeias de pilha neste objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="63a74-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a74-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="63a74-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63a74-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="63a74-105">Parameters</span></span>  

 `ppChains`  
 <span data-ttu-id="63a74-106">fora Um ponteiro para o endereço de um `ICorDebugChainEnum` objeto que permite a enumeração de todas as cadeias de pilha nesse thread, iniciando na cadeia ativa (ou seja, a mais recente).</span><span class="sxs-lookup"><span data-stu-id="63a74-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63a74-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="63a74-107">Remarks</span></span>  

 <span data-ttu-id="63a74-108">A cadeia de pilha representa a pilha de chamadas física para o thread.</span><span class="sxs-lookup"><span data-stu-id="63a74-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="63a74-109">As circunstâncias a seguir criam um limite de cadeia de pilha:</span><span class="sxs-lookup"><span data-stu-id="63a74-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="63a74-110">Uma transição gerenciada para não gerenciada ou não gerenciada para gerenciada.</span><span class="sxs-lookup"><span data-stu-id="63a74-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="63a74-111">Uma alternância de contexto.</span><span class="sxs-lookup"><span data-stu-id="63a74-111">A context switch.</span></span>  
  
- <span data-ttu-id="63a74-112">Um seqüestro de depurador de um thread de usuário.</span><span class="sxs-lookup"><span data-stu-id="63a74-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="63a74-113">No caso simples de um thread que está executando código puramente gerenciado em um único contexto, uma correspondência um-para-um existirá entre threads e cadeias de pilha.</span><span class="sxs-lookup"><span data-stu-id="63a74-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="63a74-114">Um depurador pode querer reorganizar as pilhas de chamadas físicas de todos os threads em pilhas de chamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="63a74-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="63a74-115">Isso envolveria classificar todas as cadeias de threads por seus relacionamentos de chamador/receptor e reagrupá-las.</span><span class="sxs-lookup"><span data-stu-id="63a74-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a74-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63a74-116">Requirements</span></span>  

 <span data-ttu-id="63a74-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63a74-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a74-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63a74-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63a74-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63a74-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63a74-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a74-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
