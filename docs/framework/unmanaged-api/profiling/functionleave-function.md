---
title: Função FunctionLeave
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 13636da9c3e8ac4aa9e8dc1fa02b2e33afef4717
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722252"
---
# <a name="functionleave-function"></a><span data-ttu-id="52923-102">Função FunctionLeave</span><span class="sxs-lookup"><span data-stu-id="52923-102">FunctionLeave Function</span></span>

<span data-ttu-id="52923-103">Notifica o criador de perfil de que uma função está prestes a retornar ao chamador.</span><span class="sxs-lookup"><span data-stu-id="52923-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52923-104">A `FunctionLeave` função foi preterida no .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="52923-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="52923-105">Ele continuará funcionando, mas incorrerá em uma penalidade de desempenho.</span><span class="sxs-lookup"><span data-stu-id="52923-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="52923-106">Em vez disso, use a função [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="52923-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52923-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="52923-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52923-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="52923-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="52923-109">\[in] o identificador da função que está retornando.</span><span class="sxs-lookup"><span data-stu-id="52923-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="52923-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="52923-110">Remarks</span></span>  

 <span data-ttu-id="52923-111">A `FunctionLeave` função é um retorno de chamada; você deve implementá-la.</span><span class="sxs-lookup"><span data-stu-id="52923-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="52923-112">A implementação deve usar o `__declspec` `naked` atributo de classe de armazenamento ().</span><span class="sxs-lookup"><span data-stu-id="52923-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="52923-113">O mecanismo de execução não salva nenhum registro antes de chamar essa função.</span><span class="sxs-lookup"><span data-stu-id="52923-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="52923-114">Na entrada, você deve salvar todos os registros que usar, incluindo aqueles na FPU (unidade de ponto flutuante).</span><span class="sxs-lookup"><span data-stu-id="52923-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="52923-115">Ao sair, você deve restaurar a pilha removendo todos os parâmetros que foram enviados por Push por seu chamador.</span><span class="sxs-lookup"><span data-stu-id="52923-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="52923-116">A implementação de `FunctionLeave` não deve bloquear, pois atrasará a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="52923-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="52923-117">A implementação não deve tentar uma coleta de lixo porque a pilha pode não estar em um estado amigável de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="52923-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="52923-118">Se for feita uma tentativa de coleta de lixo, o tempo de execução será bloqueado até o `FunctionLeave` retorno.</span><span class="sxs-lookup"><span data-stu-id="52923-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="52923-119">Além disso, a `FunctionLeave` função não deve chamar um código gerenciado ou, de qualquer forma, causar uma alocação de memória gerenciada.</span><span class="sxs-lookup"><span data-stu-id="52923-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52923-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52923-120">Requirements</span></span>  

 <span data-ttu-id="52923-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52923-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52923-122">**Cabeçalho:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="52923-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="52923-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52923-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52923-124">**Versões do .NET Framework:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="52923-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52923-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="52923-125">See also</span></span>

- [<span data-ttu-id="52923-126">Função FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="52923-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="52923-127">Função FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="52923-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="52923-128">Função FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="52923-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="52923-129">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="52923-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="52923-130">Criando perfil de funções estáticas globais</span><span class="sxs-lookup"><span data-stu-id="52923-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
