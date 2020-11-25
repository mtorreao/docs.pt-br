---
title: Método IMetaDataEmit::DeleteToken
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722070"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="68cbb-102">Método IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="68cbb-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="68cbb-103">Exclui o token especificado do escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="68cbb-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68cbb-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68cbb-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68cbb-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="68cbb-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="68cbb-106">no O token a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="68cbb-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68cbb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68cbb-107">Requirements</span></span>  

 <span data-ttu-id="68cbb-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68cbb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68cbb-109">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="68cbb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68cbb-110">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68cbb-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68cbb-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68cbb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68cbb-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="68cbb-112">See also</span></span>

- [<span data-ttu-id="68cbb-113">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="68cbb-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="68cbb-114">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="68cbb-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
