---
title: Método IMetaDataEmit::SetParent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: cef817b52718acfbc4360e9d3742a5a78abd3afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675042"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="9215f-102">Método IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="9215f-102">IMetaDataEmit::SetParent Method</span></span>

<span data-ttu-id="9215f-103">Estabelece que o membro especificado, conforme definido por uma chamada anterior a [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md), é um membro do tipo especificado, conforme definido por uma chamada anterior para [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="9215f-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9215f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9215f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9215f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9215f-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="9215f-106">no O `mdMemberRef` token para receber um novo pai.</span><span class="sxs-lookup"><span data-stu-id="9215f-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="9215f-107">no O `mdToken` para o novo pai.</span><span class="sxs-lookup"><span data-stu-id="9215f-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9215f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9215f-108">Requirements</span></span>  

 <span data-ttu-id="9215f-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9215f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9215f-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9215f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9215f-111">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9215f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9215f-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9215f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9215f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="9215f-113">See also</span></span>

- [<span data-ttu-id="9215f-114">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9215f-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9215f-115">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9215f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
