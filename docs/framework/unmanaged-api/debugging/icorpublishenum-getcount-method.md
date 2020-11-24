---
title: Método ICorPublishEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a23d61da2913d8732c3860a44eb58ffadab48315
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677928"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="05d8d-102">Método ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="05d8d-102">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="05d8d-103">Obtém o número de itens na enumeração.</span><span class="sxs-lookup"><span data-stu-id="05d8d-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d8d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="05d8d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d8d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="05d8d-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="05d8d-106">fora Um ponteiro para o número de itens na enumeração.</span><span class="sxs-lookup"><span data-stu-id="05d8d-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d8d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05d8d-107">Requirements</span></span>  

 <span data-ttu-id="05d8d-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d8d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d8d-109">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="05d8d-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="05d8d-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05d8d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05d8d-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d8d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d8d-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="05d8d-112">See also</span></span>

- [<span data-ttu-id="05d8d-113">Interface ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="05d8d-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
