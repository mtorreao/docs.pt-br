---
title: Método ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: 514c20455b95ecf74ffaecd349982fd8f8f49816
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723227"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="c8495-102">Método ICorProfilerCallback::ModuleUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="c8495-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>

<span data-ttu-id="c8495-103">Notifica o criador de perfil de que um módulo concluiu o descarregamento.</span><span class="sxs-lookup"><span data-stu-id="c8495-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8495-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c8495-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8495-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c8495-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c8495-106">no A ID do módulo que foi descarregado.</span><span class="sxs-lookup"><span data-stu-id="c8495-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c8495-107">no Um HRESULT que indica se o módulo foi descarregado com êxito.</span><span class="sxs-lookup"><span data-stu-id="c8495-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8495-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="c8495-108">Remarks</span></span>  

 <span data-ttu-id="c8495-109">O valor de `moduleId` não é válido para uma solicitação de informações depois que o método [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) retorna.</span><span class="sxs-lookup"><span data-stu-id="c8495-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c8495-110">Algumas partes do descarregamento da classe podem continuar após o `ModuleUnloadFinished` retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="c8495-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="c8495-111">Um HRESULT de falha em `hrStatus` indica uma falha.</span><span class="sxs-lookup"><span data-stu-id="c8495-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c8495-112">No entanto, um HRESULT de êxito em `hrStatus` indica apenas que a primeira parte do descarregamento do módulo foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c8495-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8495-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8495-113">Requirements</span></span>  

 <span data-ttu-id="c8495-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8495-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8495-115">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c8495-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8495-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8495-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8495-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8495-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8495-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8495-118">See also</span></span>

- [<span data-ttu-id="c8495-119">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c8495-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
