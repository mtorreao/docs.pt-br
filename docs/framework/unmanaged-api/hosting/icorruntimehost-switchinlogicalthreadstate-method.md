---
title: Método ICorRuntimeHost::SwitchInLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: a4590bcd96226a713ff5535a8bc802c2116f862a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690129"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="591b2-102">Método ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="591b2-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="591b2-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="591b2-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="591b2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="591b2-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="591b2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="591b2-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="591b2-106">no Cookie que indica a fibra a ser usada.</span><span class="sxs-lookup"><span data-stu-id="591b2-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="591b2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="591b2-107">Requirements</span></span>  

 <span data-ttu-id="591b2-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="591b2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="591b2-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="591b2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="591b2-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="591b2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="591b2-111">**Versão do .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="591b2-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591b2-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="591b2-112">See also</span></span>

- [<span data-ttu-id="591b2-113">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="591b2-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
