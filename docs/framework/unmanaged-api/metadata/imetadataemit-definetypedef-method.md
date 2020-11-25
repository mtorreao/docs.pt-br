---
title: Método IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 2e75b6322e40fe010e9e0a3412a99c0d3460afae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719353"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="801d9-102">Método IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="801d9-102">IMetaDataEmit::DefineTypeDef Method</span></span>

<span data-ttu-id="801d9-103">Cria uma definição de tipo para um tipo de Common Language Runtime e Obtém um token de metadados para essa definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="801d9-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801d9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="801d9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="801d9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="801d9-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="801d9-106">no O nome do tipo em Unicode.</span><span class="sxs-lookup"><span data-stu-id="801d9-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="801d9-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="801d9-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="801d9-108">Esta é uma bitmask de `CoreTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="801d9-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="801d9-109">no O token da classe base.</span><span class="sxs-lookup"><span data-stu-id="801d9-109">[in] The token of the base class.</span></span> <span data-ttu-id="801d9-110">Ele deve ser um `mdTypeDef` ou um `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="801d9-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="801d9-111">no Uma matriz de tokens que especifica as interfaces que essa classe ou interface implementa.</span><span class="sxs-lookup"><span data-stu-id="801d9-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="801d9-112">fora O `mdTypeDef` token atribuído.</span><span class="sxs-lookup"><span data-stu-id="801d9-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="801d9-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="801d9-113">Remarks</span></span>  

 <span data-ttu-id="801d9-114">Um sinalizador em `dwTypeDefFlags` especifica se o tipo que está sendo criado é um tipo de referência de Common Type System (classe ou interface) ou um tipo de valor de Common Type System.</span><span class="sxs-lookup"><span data-stu-id="801d9-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="801d9-115">Dependendo dos parâmetros fornecidos, esse método, como um efeito colateral, também pode criar um `mdInterfaceImpl` registro para cada interface herdada ou implementada por esse tipo.</span><span class="sxs-lookup"><span data-stu-id="801d9-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="801d9-116">No entanto, esse método não retorna nenhum desses `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="801d9-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="801d9-117">Se um cliente quiser adicionar ou modificar um token posteriormente `mdInterfaceImpl` , ele deverá usar a `IMetaDataImport` interface para enumerá-los.</span><span class="sxs-lookup"><span data-stu-id="801d9-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="801d9-118">Se você quiser usar a semântica COM da `[default]` interface, deverá fornecer a interface padrão como o primeiro elemento em `rtkImplements` ; um atributo personalizado definido na classe indicará que a classe tem uma interface padrão (que sempre é considerada o primeiro `mdInterfaceImpl` token declarado para a classe).</span><span class="sxs-lookup"><span data-stu-id="801d9-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="801d9-119">Cada elemento da `rtkImplements` matriz contém um `mdTypeDef` token ou `mdTypeRef` .</span><span class="sxs-lookup"><span data-stu-id="801d9-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="801d9-120">O último elemento na matriz deve ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="801d9-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801d9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="801d9-121">Requirements</span></span>  

 <span data-ttu-id="801d9-122">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801d9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801d9-123">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="801d9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="801d9-124">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="801d9-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="801d9-125">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="801d9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801d9-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="801d9-126">See also</span></span>

- [<span data-ttu-id="801d9-127">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="801d9-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="801d9-128">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="801d9-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
