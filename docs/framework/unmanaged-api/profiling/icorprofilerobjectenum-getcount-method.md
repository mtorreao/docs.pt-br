---
title: Método ICorProfilerObjectEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
ms.openlocfilehash: a0777797870a707c0d0f00bc0b4c986448118231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702388"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="ac1d6-102">Método ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="ac1d6-102">ICorProfilerObjectEnum::GetCount Method</span></span>

<span data-ttu-id="ac1d6-103">Obtém o número total de objetos congelados na coleção.</span><span class="sxs-lookup"><span data-stu-id="ac1d6-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac1d6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ac1d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac1d6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ac1d6-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="ac1d6-106">fora Um ponteiro para o número de objetos congelados na coleção.</span><span class="sxs-lookup"><span data-stu-id="ac1d6-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="ac1d6-107">Esse método sempre retornará zero no .NET Framework versão 3,5 Service Pack 1 (SP1) e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="ac1d6-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac1d6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac1d6-108">Requirements</span></span>  

 <span data-ttu-id="ac1d6-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac1d6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac1d6-110">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="ac1d6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac1d6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac1d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac1d6-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac1d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac1d6-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac1d6-113">See also</span></span>

- [<span data-ttu-id="ac1d6-114">Interface ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ac1d6-114">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
