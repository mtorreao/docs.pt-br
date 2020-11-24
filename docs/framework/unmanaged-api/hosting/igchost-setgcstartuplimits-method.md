---
title: Método IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
ms.openlocfilehash: 0eea9dba57886edfef13c31948a9cff94c6c1bfd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687867"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="01dc2-102">Método IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="01dc2-102">IGCHost::SetGCStartupLimits Method</span></span>

<span data-ttu-id="01dc2-103">Define o tamanho do segmento e o tamanho máximo para a geração 0.</span><span class="sxs-lookup"><span data-stu-id="01dc2-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="01dc2-104">A partir do .NET Framework 4,5, você pode definir o tamanho do segmento e o tamanho máximo de geração 0 para valores maiores do que `DWORD` usar o método [IGCHost2:: SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01dc2-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01dc2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="01dc2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01dc2-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="01dc2-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="01dc2-107">no O tamanho do segmento usado pelo sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="01dc2-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="01dc2-108">no O tamanho máximo para a geração 0.</span><span class="sxs-lookup"><span data-stu-id="01dc2-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01dc2-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="01dc2-109">Remarks</span></span>  

 <span data-ttu-id="01dc2-110">O `SetGCStartupLimits` método pode ser chamado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="01dc2-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="01dc2-111">Esses valores não podem ser alterados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="01dc2-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01dc2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01dc2-112">Requirements</span></span>  

 <span data-ttu-id="01dc2-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01dc2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01dc2-114">**Cabeçalho:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="01dc2-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="01dc2-115">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01dc2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01dc2-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01dc2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dc2-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="01dc2-117">See also</span></span>

- [<span data-ttu-id="01dc2-118">Interface IGCHost</span><span class="sxs-lookup"><span data-stu-id="01dc2-118">IGCHost Interface</span></span>](igchost-interface.md)
