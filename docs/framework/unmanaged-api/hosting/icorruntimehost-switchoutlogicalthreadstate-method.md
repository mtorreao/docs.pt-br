---
title: Método ICorRuntimeHost::SwitchOutLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: e41ead54b50b8b28ebd9ee9c97d15ca6c71e7313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690116"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="68a2e-102">Método ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="68a2e-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>

<span data-ttu-id="68a2e-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="68a2e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a2e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68a2e-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68a2e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68a2e-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="68a2e-106">fora Cookie que indica a fibra que está sendo desativada.</span><span class="sxs-lookup"><span data-stu-id="68a2e-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a2e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68a2e-107">Requirements</span></span>  

 <span data-ttu-id="68a2e-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68a2e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a2e-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="68a2e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68a2e-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68a2e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68a2e-111">**Versão do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="68a2e-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a2e-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="68a2e-112">See also</span></span>

- [<span data-ttu-id="68a2e-113">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="68a2e-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
