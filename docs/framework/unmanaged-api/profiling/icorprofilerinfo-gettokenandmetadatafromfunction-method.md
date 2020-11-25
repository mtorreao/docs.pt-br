---
title: Método ICorProfilerInfo::GetTokenAndMetadataFromFunction
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: 8e03eefc3758347389be4af6d53921480ee40263
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724072"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="07783-102">Método ICorProfilerInfo::GetTokenAndMetadataFromFunction</span><span class="sxs-lookup"><span data-stu-id="07783-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>

<span data-ttu-id="07783-103">Obtém o token de metadados e uma instância de interface de metadados que podem ser usados em relação ao token para a função especificada.</span><span class="sxs-lookup"><span data-stu-id="07783-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07783-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="07783-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07783-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="07783-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="07783-106">no A ID da função para a qual obter o token de metadados e a interface de metadados.</span><span class="sxs-lookup"><span data-stu-id="07783-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="07783-107">no A ID de referência da interface de metadados para obter a instância do.</span><span class="sxs-lookup"><span data-stu-id="07783-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="07783-108">fora Um ponteiro para o endereço da instância da interface de metadados que pode ser usada em relação ao token para a função especificada.</span><span class="sxs-lookup"><span data-stu-id="07783-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="07783-109">fora Um ponteiro para o token de metadados para a função especificada.</span><span class="sxs-lookup"><span data-stu-id="07783-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07783-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07783-110">Requirements</span></span>  

 <span data-ttu-id="07783-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07783-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07783-112">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="07783-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07783-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07783-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07783-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07783-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07783-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="07783-115">See also</span></span>

- [<span data-ttu-id="07783-116">Interface ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="07783-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
