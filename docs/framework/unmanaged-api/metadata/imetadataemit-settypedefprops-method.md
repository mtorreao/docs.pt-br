---
title: Método IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706821"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="eacb8-102">Método IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="eacb8-102">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="eacb8-103">Define recursos de um tipo definido por uma chamada anterior para [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="eacb8-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacb8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eacb8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eacb8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="eacb8-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="eacb8-106">no Um `mdTypeDef` token obtido da chamada original para [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="eacb8-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="eacb8-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="eacb8-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="eacb8-108">Esta é uma bitmask de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="eacb8-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="eacb8-109">no O `mdToken` da classe base.</span><span class="sxs-lookup"><span data-stu-id="eacb8-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="eacb8-110">Obtido de uma chamada anterior para [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)ou `null` .</span><span class="sxs-lookup"><span data-stu-id="eacb8-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="eacb8-111">no Uma matriz de tokens para as interfaces que esse tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="eacb8-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="eacb8-112">Esses `mdTypeRef` tokens são obtidos usando [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="eacb8-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="eacb8-113">O último elemento da matriz deve ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="eacb8-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eacb8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eacb8-114">Requirements</span></span>  

 <span data-ttu-id="eacb8-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eacb8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eacb8-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eacb8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eacb8-117">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eacb8-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eacb8-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eacb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacb8-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="eacb8-119">See also</span></span>

- [<span data-ttu-id="eacb8-120">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="eacb8-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="eacb8-121">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="eacb8-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
