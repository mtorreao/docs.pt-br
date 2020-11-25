---
title: Método IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721095"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="cc2c7-102">Método IInstallReferenceEnum::GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="cc2c7-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="cc2c7-103">Obtém um ponteiro para o próximo objeto [IInstallReferenceItem](iinstallreferenceitem-interface.md) contido neste objeto [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cc2c7-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2c7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc2c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc2c7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc2c7-105">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="cc2c7-106">fora O `IInstallReferenceItem` ponteiro retornado.</span><span class="sxs-lookup"><span data-stu-id="cc2c7-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cc2c7-107">no Reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="cc2c7-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cc2c7-108">`dwFlags` deve ser 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="cc2c7-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cc2c7-109">no Reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="cc2c7-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cc2c7-110">`pvReserved` deve ser uma referência nula.</span><span class="sxs-lookup"><span data-stu-id="cc2c7-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc2c7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc2c7-111">Requirements</span></span>  

 <span data-ttu-id="cc2c7-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc2c7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc2c7-113">**Cabeçalho:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cc2c7-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cc2c7-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc2c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2c7-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc2c7-115">See also</span></span>

- [<span data-ttu-id="cc2c7-116">Interface IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="cc2c7-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="cc2c7-117">Interface IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="cc2c7-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
