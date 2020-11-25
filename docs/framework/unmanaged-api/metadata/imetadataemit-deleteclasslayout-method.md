---
title: Método IMetaDataEmit::DeleteClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: d355e0e3b2461932384ca11d83d46fd1dc63b80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732678"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="01e04-102">Método IMetaDataEmit::DeleteClassLayout</span><span class="sxs-lookup"><span data-stu-id="01e04-102">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="01e04-103">Destrói a assinatura de metadados de layout de classe para o tipo representado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="01e04-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e04-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="01e04-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01e04-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="01e04-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="01e04-106">no Um `mdTypeDef` token de metadados que representa o tipo para o qual o layout de classe será excluído.</span><span class="sxs-lookup"><span data-stu-id="01e04-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01e04-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01e04-107">Requirements</span></span>  

 <span data-ttu-id="01e04-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01e04-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01e04-109">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01e04-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01e04-110">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01e04-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01e04-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01e04-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e04-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="01e04-112">See also</span></span>

- [<span data-ttu-id="01e04-113">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="01e04-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="01e04-114">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="01e04-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
