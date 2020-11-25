---
title: Método IObjectHandle::Unwrap
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
ms.openlocfilehash: 32b6d2c05a96658ab2b8ec1df288d2be05bb947f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730654"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="dd4c0-102">Método IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="dd4c0-102">IObjectHandle::Unwrap Method</span></span>

<span data-ttu-id="dd4c0-103">Desenvolve um objeto Marshal-by-Value de indireção.</span><span class="sxs-lookup"><span data-stu-id="dd4c0-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4c0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dd4c0-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd4c0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="dd4c0-105">Parameters</span></span>  

 `ppv`  
 <span data-ttu-id="dd4c0-106">fora Um ponteiro para o objeto a ser desencapsulado.</span><span class="sxs-lookup"><span data-stu-id="dd4c0-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd4c0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd4c0-107">Requirements</span></span>  

 <span data-ttu-id="dd4c0-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd4c0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4c0-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd4c0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd4c0-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd4c0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd4c0-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
