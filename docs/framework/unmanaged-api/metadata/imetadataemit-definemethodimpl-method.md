---
title: Método IMetaDataEmit::DefineMethodImpl
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 24a7c5bca1287e55f3eb06d63e1fed8da37eb3b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719561"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="54c0d-102">Método IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="54c0d-102">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="54c0d-103">Cria uma definição para implementação de um método herdado de uma interface e retorna um token para essa definição de implementação de método.</span><span class="sxs-lookup"><span data-stu-id="54c0d-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54c0d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54c0d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54c0d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="54c0d-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="54c0d-106">no O `mdTypedef` token da classe de implementação.</span><span class="sxs-lookup"><span data-stu-id="54c0d-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="54c0d-107">no O `mdMethodDef` `mdMemberRef` token ou do corpo do código.</span><span class="sxs-lookup"><span data-stu-id="54c0d-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="54c0d-108">no O `mdMethodDef` `mdMemberRef` token ou do método de interface que está sendo implementado.</span><span class="sxs-lookup"><span data-stu-id="54c0d-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54c0d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54c0d-109">Requirements</span></span>  

 <span data-ttu-id="54c0d-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54c0d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54c0d-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="54c0d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54c0d-112">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54c0d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54c0d-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54c0d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c0d-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="54c0d-114">See also</span></span>

- [<span data-ttu-id="54c0d-115">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="54c0d-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="54c0d-116">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="54c0d-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
