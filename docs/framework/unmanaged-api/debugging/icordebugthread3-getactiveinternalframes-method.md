---
title: Método ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 2ca3bf94298b45e404c930ffe52e101085ee482d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726204"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="9ae2e-102">Método ICorDebugThread3::GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="9ae2e-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>

<span data-ttu-id="9ae2e-103">Retorna uma matriz de quadros internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) na pilha.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae2e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9ae2e-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ae2e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9ae2e-105">Parameters</span></span>  

 `cInternalFrames`  
 <span data-ttu-id="9ae2e-106">no O número de quadros internos esperados em `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="9ae2e-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="9ae2e-107">fora Um ponteiro para um `ULONG32` que contém o número de quadros internos na pilha.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="9ae2e-108">[entrada, saída] Um ponteiro para o endereço de uma matriz de quadros internos na pilha.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ae2e-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9ae2e-109">Return Value</span></span>  

 <span data-ttu-id="9ae2e-110">Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9ae2e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ae2e-111">HRESULT</span></span>|<span data-ttu-id="9ae2e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9ae2e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ae2e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ae2e-113">S_OK</span></span>|<span data-ttu-id="9ae2e-114">O objeto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) foi criado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="9ae2e-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9ae2e-115">E_INVALIDARG</span></span>|<span data-ttu-id="9ae2e-116">`cInternalFrames` Não é zero e `ppInternalFrames` é `null` `pcInternalFrames` `null` .</span><span class="sxs-lookup"><span data-stu-id="9ae2e-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="9ae2e-117">HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="9ae2e-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="9ae2e-118">`ppInternalFrames` é menor do que a contagem de quadros internos.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9ae2e-119">Exceções</span><span class="sxs-lookup"><span data-stu-id="9ae2e-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae2e-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="9ae2e-120">Remarks</span></span>  

 <span data-ttu-id="9ae2e-121">Os quadros internos são estruturas de dados enviadas por push para a pilha pelo tempo de execução para armazenar dados temporários.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="9ae2e-122">Ao chamar pela primeira vez `GetActiveInternalFrames` , você deve definir o `cInternalFrames` parâmetro como 0 (zero) e o `ppInternalFrames` parâmetro como NULL.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="9ae2e-123">Quando `GetActiveInternalFrames` o primeiro retorna, `pcInternalFrames` contém a contagem dos quadros internos na pilha.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="9ae2e-124">`GetActiveInternalFrames` deve ser chamado uma segunda vez.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="9ae2e-125">Você deve passar a contagem apropriada ( `pcInternalFrames` ) no `cInternalFrames` parâmetro e especificar um ponteiro para uma matriz de tamanho apropriado no `ppInternalFrames` .</span><span class="sxs-lookup"><span data-stu-id="9ae2e-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="9ae2e-126">Use o método [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) para retornar os quadros de pilhas reais.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae2e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ae2e-127">Requirements</span></span>  

 <span data-ttu-id="9ae2e-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae2e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae2e-129">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae2e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae2e-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae2e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae2e-131">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae2e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae2e-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ae2e-132">See also</span></span>

- [<span data-ttu-id="9ae2e-133">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="9ae2e-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9ae2e-134">Depuração</span><span class="sxs-lookup"><span data-stu-id="9ae2e-134">Debugging</span></span>](index.md)
