---
title: Método ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: a45f613b7547e2e80abdbd8ac85cb0b2b6a499e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716883"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="ee51a-102">Método ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="ee51a-102">ICorPublish::GetProcess Method</span></span>

<span data-ttu-id="ee51a-103">Obtém uma instância de [ICorPublishProcess](icorpublishprocess-interface.md) que representa o processo com o identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="ee51a-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee51a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee51a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee51a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ee51a-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="ee51a-106">no O identificador do processo.</span><span class="sxs-lookup"><span data-stu-id="ee51a-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ee51a-107">fora Um ponteiro para o endereço de uma `ICorPublishProcess` instância que representa o processo.</span><span class="sxs-lookup"><span data-stu-id="ee51a-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee51a-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="ee51a-108">Remarks</span></span>  

 <span data-ttu-id="ee51a-109">`GetProcess` falhará se o processo não existir ou não for um processo gerenciado que possa ser depurado pelo usuário atual.</span><span class="sxs-lookup"><span data-stu-id="ee51a-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee51a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee51a-110">Requirements</span></span>  

 <span data-ttu-id="ee51a-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee51a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee51a-112">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ee51a-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ee51a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee51a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee51a-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee51a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee51a-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee51a-115">See also</span></span>

- [<span data-ttu-id="ee51a-116">Interface ICorPublish</span><span class="sxs-lookup"><span data-stu-id="ee51a-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
