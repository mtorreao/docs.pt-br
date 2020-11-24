---
title: Método ICorThreadpool::CorChangeTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: 3d119c8355f5b58a05f1ea1695969b2e98682c72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690220"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="82afb-102">Método ICorThreadpool::CorChangeTimer</span><span class="sxs-lookup"><span data-stu-id="82afb-102">ICorThreadpool::CorChangeTimer Method</span></span>

<span data-ttu-id="82afb-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="82afb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82afb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82afb-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="82afb-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82afb-105">Requirements</span></span>  

 <span data-ttu-id="82afb-106">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82afb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82afb-107">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82afb-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82afb-108">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82afb-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82afb-109">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82afb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82afb-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="82afb-110">See also</span></span>

- [<span data-ttu-id="82afb-111">Interface ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="82afb-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
