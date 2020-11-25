---
title: Método IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733172"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="35a6e-102">Método IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="35a6e-102">IMetaDataImport::GetMethodSemantics Method</span></span>

<span data-ttu-id="35a6e-103">Obtém sinalizadores que indicam a relação entre o método referenciado pelo token MethodDef especificado e a propriedade emparelhada e o evento referenciado pelo token EventProp especificado.</span><span class="sxs-lookup"><span data-stu-id="35a6e-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a6e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="35a6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35a6e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="35a6e-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="35a6e-106">no Um token MethodDef que representa o método para obter as informações de função semântica para.</span><span class="sxs-lookup"><span data-stu-id="35a6e-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="35a6e-107">no Um token que representa a propriedade emparelhada e o evento para o qual obter a função do método.</span><span class="sxs-lookup"><span data-stu-id="35a6e-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="35a6e-108">fora Um ponteiro para os sinalizadores de semântica associados.</span><span class="sxs-lookup"><span data-stu-id="35a6e-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="35a6e-109">Esse valor é um bitmask da enumeração [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="35a6e-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35a6e-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="35a6e-110">Remarks</span></span>  

 <span data-ttu-id="35a6e-111">O método [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) define os sinalizadores de semântica de um método.</span><span class="sxs-lookup"><span data-stu-id="35a6e-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a6e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35a6e-112">Requirements</span></span>  

 <span data-ttu-id="35a6e-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a6e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a6e-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="35a6e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35a6e-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35a6e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35a6e-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a6e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a6e-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="35a6e-117">See also</span></span>

- [<span data-ttu-id="35a6e-118">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="35a6e-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="35a6e-119">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="35a6e-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
