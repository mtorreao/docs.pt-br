---
title: Função FunctionEnter3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: b511c5abe10ab6c0ec856a5686b082132ed4a5d9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722851"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="4bf72-102">Função FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4bf72-102">FunctionEnter3WithInfo Function</span></span>

<span data-ttu-id="4bf72-103">Notifica o criador de perfil que o controle está sendo passado para uma função e fornece um identificador que pode ser passado para o [método ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar o quadro de pilha e os argumentos de função.</span><span class="sxs-lookup"><span data-stu-id="4bf72-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf72-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4bf72-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bf72-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4bf72-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="4bf72-106">\[in] o identificador da função à qual o controle é passado.</span><span class="sxs-lookup"><span data-stu-id="4bf72-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="4bf72-107">\[in] um identificador opaco que representa informações sobre um determinado registro de ativação.</span><span class="sxs-lookup"><span data-stu-id="4bf72-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="4bf72-108">Esse identificador é válido somente durante o retorno de chamada ao qual é passado.</span><span class="sxs-lookup"><span data-stu-id="4bf72-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bf72-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="4bf72-109">Remarks</span></span>  

 <span data-ttu-id="4bf72-110">O `FunctionEnter3WithInfo` método de retorno de chamada notifica o criador de perfil conforme as funções são chamadas e permite que o criador de perfil Use o [método ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) para inspecionar valores de argumento.</span><span class="sxs-lookup"><span data-stu-id="4bf72-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="4bf72-111">Para acessar informações de argumento, o `COR_PRF_ENABLE_FUNCTION_ARGS` sinalizador precisa ser definido.</span><span class="sxs-lookup"><span data-stu-id="4bf72-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="4bf72-112">O criador de perfil pode usar o [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para definir os sinalizadores de evento e, em seguida, usar o [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar sua implementação dessa função.</span><span class="sxs-lookup"><span data-stu-id="4bf72-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="4bf72-113">A `FunctionEnter3WithInfo` função é um retorno de chamada; você deve implementá-la.</span><span class="sxs-lookup"><span data-stu-id="4bf72-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="4bf72-114">A implementação deve usar o `__declspec(naked)` atributo de classe de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4bf72-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="4bf72-115">O mecanismo de execução não salva nenhum registro antes de chamar essa função.</span><span class="sxs-lookup"><span data-stu-id="4bf72-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="4bf72-116">Na entrada, você deve salvar todos os registros que usar, incluindo aqueles na FPU (unidade de ponto flutuante).</span><span class="sxs-lookup"><span data-stu-id="4bf72-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="4bf72-117">Ao sair, você deve restaurar a pilha removendo todos os parâmetros que foram enviados por Push por seu chamador.</span><span class="sxs-lookup"><span data-stu-id="4bf72-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="4bf72-118">A implementação de `FunctionEnter3WithInfo` não deve bloquear, pois atrasará a coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="4bf72-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="4bf72-119">A implementação não deve tentar uma coleta de lixo, pois a pilha pode não estar em um estado amigável de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="4bf72-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="4bf72-120">Se for feita uma tentativa de coleta de lixo, o tempo de execução será bloqueado até o `FunctionEnter3WithInfo` retorno.</span><span class="sxs-lookup"><span data-stu-id="4bf72-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="4bf72-121">A `FunctionEnter3WithInfo` função não deve chamar código gerenciado ou causar uma alocação de memória gerenciada de qualquer forma.</span><span class="sxs-lookup"><span data-stu-id="4bf72-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bf72-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bf72-122">Requirements</span></span>  

 <span data-ttu-id="4bf72-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf72-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf72-124">**Cabeçalho:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="4bf72-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4bf72-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bf72-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bf72-126">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bf72-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf72-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="4bf72-127">See also</span></span>

- [<span data-ttu-id="4bf72-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="4bf72-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="4bf72-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="4bf72-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="4bf72-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4bf72-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="4bf72-131">Criando perfil de funções estáticas globais</span><span class="sxs-lookup"><span data-stu-id="4bf72-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
