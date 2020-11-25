---
title: Função GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: c22f0701cfda4523f595366a97435ef8da08b0cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724462"
---
# <a name="getcachepath-function"></a><span data-ttu-id="242ab-102">Função GetCachePath</span><span class="sxs-lookup"><span data-stu-id="242ab-102">GetCachePath Function</span></span>

<span data-ttu-id="242ab-103">Obtém o caminho para o assembly armazenado em cache, usando os sinalizadores especificados.</span><span class="sxs-lookup"><span data-stu-id="242ab-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="242ab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="242ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="242ab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="242ab-105">Parameters</span></span>  

 `dwCacheFlags`  
 <span data-ttu-id="242ab-106">no Um valor [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) que indica a origem do assembly armazenado em cache.</span><span class="sxs-lookup"><span data-stu-id="242ab-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="242ab-107">fora O ponteiro retornado para o caminho.</span><span class="sxs-lookup"><span data-stu-id="242ab-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="242ab-108">[entrada, saída] O comprimento máximo solicitado de `pwzCachePath` e, após o retorno, o comprimento real de `pwzCachePath` .</span><span class="sxs-lookup"><span data-stu-id="242ab-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="242ab-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="242ab-109">Requirements</span></span>  

 <span data-ttu-id="242ab-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="242ab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="242ab-111">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="242ab-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="242ab-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="242ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242ab-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="242ab-113">See also</span></span>

- [<span data-ttu-id="242ab-114">Enumeração ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="242ab-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="242ab-115">Funções estáticas globais de fusão</span><span class="sxs-lookup"><span data-stu-id="242ab-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
