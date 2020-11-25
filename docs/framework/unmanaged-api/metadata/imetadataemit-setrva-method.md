---
title: Método IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: df9dc1a36a9adcef3f93a9929565cef117e84d75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704221"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="cdea3-102">Método IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="cdea3-102">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="cdea3-103">Define o endereço virtual relativo do método especificado.</span><span class="sxs-lookup"><span data-stu-id="cdea3-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdea3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cdea3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdea3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cdea3-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="cdea3-106">no O token para o método de destino ou a implementação do método.</span><span class="sxs-lookup"><span data-stu-id="cdea3-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="cdea3-107">no O endereço do código ou da área de dados.</span><span class="sxs-lookup"><span data-stu-id="cdea3-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdea3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdea3-108">Requirements</span></span>  

 <span data-ttu-id="cdea3-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdea3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdea3-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cdea3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cdea3-111">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdea3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdea3-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdea3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdea3-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="cdea3-113">See also</span></span>

- [<span data-ttu-id="cdea3-114">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cdea3-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cdea3-115">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cdea3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
