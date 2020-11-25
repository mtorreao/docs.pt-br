---
title: Método ICorProfilerModuleEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 53009a1805056b83047299ebdca8f21d98ad5137
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732977"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="a56d3-102">Método ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="a56d3-102">ICorProfilerModuleEnum::GetCount Method</span></span>

<span data-ttu-id="a56d3-103">Obtém o número de módulos gerenciados que foram carregados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a56d3-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a56d3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a56d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a56d3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a56d3-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="a56d3-106">fora O número de módulos de tempo de execução na coleção.</span><span class="sxs-lookup"><span data-stu-id="a56d3-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a56d3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a56d3-107">Requirements</span></span>  

 <span data-ttu-id="a56d3-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a56d3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a56d3-109">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a56d3-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a56d3-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a56d3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a56d3-111">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a56d3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56d3-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="a56d3-112">See also</span></span>

- [<span data-ttu-id="a56d3-113">Interface ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="a56d3-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="a56d3-114">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="a56d3-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
