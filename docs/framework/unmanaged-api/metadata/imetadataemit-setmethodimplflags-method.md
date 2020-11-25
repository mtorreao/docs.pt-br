---
title: Método IMetaDataEmit::SetMethodImplFlags
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: 486d545413337f6696bd9f21c516466fc3747256
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730351"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="8639f-102">Método IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="8639f-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="8639f-103">Define ou atualiza a assinatura de metadados da implementação do método herdado que é referenciado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="8639f-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8639f-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8639f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8639f-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8639f-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="8639f-106">no O token para o método a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="8639f-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="8639f-107">no Uma combinação dos valores da enumeração [CorMethodImpl](cormethodimpl-enumeration.md) que especifica os recursos de implementação do método.</span><span class="sxs-lookup"><span data-stu-id="8639f-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8639f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8639f-108">Requirements</span></span>  

 <span data-ttu-id="8639f-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8639f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8639f-110">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8639f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8639f-111">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8639f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8639f-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8639f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8639f-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="8639f-113">See also</span></span>

- [<span data-ttu-id="8639f-114">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8639f-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8639f-115">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8639f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
