---
title: Método IDebuggerInfo::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 28b0c5ad5ed8b706974399dcd5468e9810b9fd57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721693"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="a4dd2-102">Método IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="a4dd2-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>

<span data-ttu-id="a4dd2-103">Obtém um valor que indica se um depurador gerenciado está anexado a esse processo.</span><span class="sxs-lookup"><span data-stu-id="a4dd2-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4dd2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4dd2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4dd2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a4dd2-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="a4dd2-106">fora Um ponteiro para um valor que `true` se um depurador gerenciado estiver anexado ao processo; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="a4dd2-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4dd2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4dd2-107">Requirements</span></span>  

 <span data-ttu-id="a4dd2-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4dd2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4dd2-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4dd2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4dd2-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4dd2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4dd2-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4dd2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4dd2-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="a4dd2-112">See also</span></span>

- [<span data-ttu-id="a4dd2-113">Interface IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="a4dd2-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
