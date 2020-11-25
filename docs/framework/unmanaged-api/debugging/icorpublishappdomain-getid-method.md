---
title: Método ICorPublishAppDomain::GetID
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: ab331145a8147e8830cb9b158a1975bc748c7cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716857"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="297ac-102">Método ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="297ac-102">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="297ac-103">Obtém o identificador exclusivo para este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="297ac-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="297ac-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="297ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="297ac-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="297ac-105">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="297ac-106">fora Um ponteiro para o identificador do domínio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="297ac-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="297ac-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="297ac-107">Remarks</span></span>  

 <span data-ttu-id="297ac-108">O identificador é exclusivo somente no escopo do processo que o contém.</span><span class="sxs-lookup"><span data-stu-id="297ac-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="297ac-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="297ac-109">Requirements</span></span>  

 <span data-ttu-id="297ac-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="297ac-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="297ac-111">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="297ac-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="297ac-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="297ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="297ac-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="297ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297ac-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="297ac-114">See also</span></span>

- [<span data-ttu-id="297ac-115">Interface ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="297ac-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
