---
title: Método IMetaDataImport2::GetGenericParamConstraintProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
ms.openlocfilehash: 8beaea0b7493b7cea76466bb15355cfc5c6d5c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702696"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="685dd-102">Método IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="685dd-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>

<span data-ttu-id="685dd-103">Obtém os metadados associados à restrição de parâmetro genérico representada pelo token de restrição especificado.</span><span class="sxs-lookup"><span data-stu-id="685dd-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="685dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="685dd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="685dd-105">Parameters</span></span>  

 `gpc`  
 <span data-ttu-id="685dd-106">no O token para a restrição de parâmetro genérico para a qual retornar os metadados.</span><span class="sxs-lookup"><span data-stu-id="685dd-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="685dd-107">fora Um ponteiro para o token que representa o parâmetro genérico que é restrito.</span><span class="sxs-lookup"><span data-stu-id="685dd-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="685dd-108">fora Um ponteiro para um token de TypeDef, TypeRef ou TypeSpec que representa uma restrição em `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="685dd-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685dd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="685dd-109">Requirements</span></span>  

 <span data-ttu-id="685dd-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="685dd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="685dd-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="685dd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="685dd-112">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="685dd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="685dd-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="685dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685dd-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="685dd-114">See also</span></span>

- [<span data-ttu-id="685dd-115">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="685dd-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="685dd-116">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="685dd-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
