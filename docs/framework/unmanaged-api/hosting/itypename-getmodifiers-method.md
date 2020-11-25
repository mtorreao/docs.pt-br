---
title: Método ITypeName::GetModifiers
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 64751032c017473ffd82248b310b14c087f74129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727829"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="91824-102">Método ITypeName::GetModifiers</span><span class="sxs-lookup"><span data-stu-id="91824-102">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="91824-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="91824-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91824-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91824-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="91824-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91824-105">Requirements</span></span>  

 <span data-ttu-id="91824-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91824-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91824-107">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="91824-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91824-108">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91824-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91824-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91824-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91824-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="91824-110">See also</span></span>

- [<span data-ttu-id="91824-111">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="91824-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
