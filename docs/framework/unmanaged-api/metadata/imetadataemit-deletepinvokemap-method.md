---
title: Método IMetaDataEmit::DeletePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722083"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="9bbab-102">Método IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="9bbab-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="9bbab-103">Destrói os metadados de mapeamento do PInvoke para o objeto referenciado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="9bbab-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bbab-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9bbab-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bbab-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9bbab-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="9bbab-106">no Um `mdFieldDef` `mdMethodDef` token ou que representa o objeto para o qual excluir os metadados de mapeamento do PInvoke.</span><span class="sxs-lookup"><span data-stu-id="9bbab-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bbab-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9bbab-107">Requirements</span></span>  

 <span data-ttu-id="9bbab-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bbab-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bbab-109">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9bbab-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9bbab-110">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9bbab-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bbab-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bbab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbab-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="9bbab-112">See also</span></span>

- [<span data-ttu-id="9bbab-113">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9bbab-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9bbab-114">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9bbab-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
