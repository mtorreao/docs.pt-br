---
title: Método ICorProfilerCallback::ExceptionCLRCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: 894084978f976bcee71138d35534a80b5f9cda5f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699970"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="92416-102">Método ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="92416-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>

<span data-ttu-id="92416-103">Chamado quando um `catch` bloco de uma exceção é encontrado dentro do Common Language Runtime (CLR) em si.</span><span class="sxs-lookup"><span data-stu-id="92416-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="92416-104">Esse método é obsoleto no .NET Framework versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="92416-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92416-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92416-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="92416-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92416-106">Requirements</span></span>  

 <span data-ttu-id="92416-107">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92416-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92416-108">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="92416-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92416-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92416-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92416-110">**Versão do .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="92416-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92416-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="92416-111">See also</span></span>

- [<span data-ttu-id="92416-112">Interface ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="92416-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="92416-113">Método ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="92416-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
