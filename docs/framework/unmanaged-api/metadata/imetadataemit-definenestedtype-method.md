---
title: Método IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719535"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="749d1-102">Método IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="749d1-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="749d1-103">Cria a assinatura de metadados de uma definição de tipo, retorna um `mdTypeDef` token para esse tipo e especifica que o tipo definido é um membro do tipo referenciado pelo `tdEncloser` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="749d1-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="749d1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="749d1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="749d1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="749d1-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="749d1-106">no O nome do tipo em Unicode.</span><span class="sxs-lookup"><span data-stu-id="749d1-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="749d1-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="749d1-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="749d1-108">Esta é uma bitmask de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="749d1-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="749d1-109">no O token da classe base.</span><span class="sxs-lookup"><span data-stu-id="749d1-109">[in] The token of the base class.</span></span> <span data-ttu-id="749d1-110">Este é um `mdTypeDef` `mdTypeRef` token ou.</span><span class="sxs-lookup"><span data-stu-id="749d1-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="749d1-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="749d1-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="749d1-112">no Uma matriz de tokens que especificam as interfaces que essa classe ou interface implementa.</span><span class="sxs-lookup"><span data-stu-id="749d1-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="749d1-113">no O token do tipo delimitador.</span><span class="sxs-lookup"><span data-stu-id="749d1-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="749d1-114">O último elemento da matriz deve ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="749d1-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="749d1-115">fora O `mdTypeDef` token atribuído.</span><span class="sxs-lookup"><span data-stu-id="749d1-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="749d1-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="749d1-116">Requirements</span></span>  

 <span data-ttu-id="749d1-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="749d1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="749d1-118">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="749d1-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="749d1-119">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="749d1-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="749d1-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749d1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749d1-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="749d1-121">See also</span></span>

- [<span data-ttu-id="749d1-122">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="749d1-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="749d1-123">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="749d1-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
