---
title: Método IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: 65f6be8c12ce057422ad178c759affed170e44ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721706"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="452fd-102">Método IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="452fd-102">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="452fd-103">Chamado pelo Common Language Runtime (CLR) para notificar o host de que um domínio de aplicativo foi criado.</span><span class="sxs-lookup"><span data-stu-id="452fd-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="452fd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="452fd-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="452fd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="452fd-105">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="452fd-106">no Um ponteiro para um objeto de interface [IUnknown](/cpp/atl/iunknown) que representa o novo domínio de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="452fd-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="452fd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="452fd-107">Requirements</span></span>  

 <span data-ttu-id="452fd-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="452fd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="452fd-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="452fd-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="452fd-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="452fd-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="452fd-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="452fd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452fd-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="452fd-112">See also</span></span>

- [<span data-ttu-id="452fd-113">Interface IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="452fd-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
