---
title: Método IMetaDataEmit::DeleteFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 5989c45782b4f83ecfa285cb305080320abf6a3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700542"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="48cdf-102">Método IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="48cdf-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="48cdf-103">Destrói a assinatura de metadados de marshaling do PInvoke para o objeto referenciado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="48cdf-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48cdf-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="48cdf-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48cdf-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="48cdf-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="48cdf-106">no Um `mdFieldDef` `mdParamDef` token ou que representa o campo ou parâmetro para o qual excluir a assinatura de metadados de marshaling.</span><span class="sxs-lookup"><span data-stu-id="48cdf-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48cdf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48cdf-107">Requirements</span></span>  

 <span data-ttu-id="48cdf-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48cdf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48cdf-109">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="48cdf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48cdf-110">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48cdf-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48cdf-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48cdf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48cdf-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="48cdf-112">See also</span></span>

- [<span data-ttu-id="48cdf-113">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="48cdf-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="48cdf-114">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="48cdf-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
