---
title: Função GetAppIdAuthority
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: 5e731ac1c652b8b4505073a3a10463ae0ce21ac0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724488"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="c937a-102">Função GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="c937a-102">GetAppIdAuthority Function</span></span>

<span data-ttu-id="c937a-103">Obtém um ponteiro para uma instância de [IAppIdAuthority](iappidauthority-interface.md) que gerencia chaves para identidades e referências de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c937a-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c937a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c937a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c937a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c937a-105">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="c937a-106">fora O `IAppIdAuthority` ponteiro retornado.</span><span class="sxs-lookup"><span data-stu-id="c937a-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c937a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c937a-107">Requirements</span></span>  

 <span data-ttu-id="c937a-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c937a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c937a-109">**Cabeçalho:** Isolamento. h</span><span class="sxs-lookup"><span data-stu-id="c937a-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c937a-110">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c937a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c937a-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="c937a-111">See also</span></span>

- [<span data-ttu-id="c937a-112">Interface IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="c937a-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="c937a-113">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="c937a-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
