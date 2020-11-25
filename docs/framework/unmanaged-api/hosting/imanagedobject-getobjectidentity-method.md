---
title: Método IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
ms.openlocfilehash: fc74b84bccceb1772bf3642e51ec88c562ce5dce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730702"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="21b1b-102">Método IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="21b1b-102">IManagedObject::GetObjectIdentity Method</span></span>

<span data-ttu-id="21b1b-103">Obtém a identidade deste objeto gerenciado.</span><span class="sxs-lookup"><span data-stu-id="21b1b-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b1b-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="21b1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21b1b-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="21b1b-105">Parameters</span></span>  

 `pBSTRGUID`  
 <span data-ttu-id="21b1b-106">fora Um ponteiro para o GUID do processo no qual o objeto reside.</span><span class="sxs-lookup"><span data-stu-id="21b1b-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="21b1b-107">fora Um ponteiro para a ID do domínio do aplicativo do objeto.</span><span class="sxs-lookup"><span data-stu-id="21b1b-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="21b1b-108">fora Um ponteiro para o índice do objeto na tabela v clássica COM.</span><span class="sxs-lookup"><span data-stu-id="21b1b-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21b1b-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="21b1b-109">Remarks</span></span>  

 <span data-ttu-id="21b1b-110">A identidade de um objeto gerenciado inclui GUID do processo, ID de domínio do aplicativo e o índice do objeto na tabela v clássica do COM.</span><span class="sxs-lookup"><span data-stu-id="21b1b-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21b1b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21b1b-111">Requirements</span></span>  

 <span data-ttu-id="21b1b-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21b1b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b1b-113">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21b1b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21b1b-114">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21b1b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21b1b-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b1b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="21b1b-116">See also</span></span>

- [<span data-ttu-id="21b1b-117">Interface IManagedObject</span><span class="sxs-lookup"><span data-stu-id="21b1b-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
