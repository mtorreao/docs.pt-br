---
title: Método IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722096"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="b11e2-102">Método IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="b11e2-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="b11e2-103">Obtém o conjunto de propriedades do tipo exportado com a assinatura de metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="b11e2-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b11e2-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b11e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b11e2-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b11e2-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="b11e2-106">no Um `mdExportedType` token de metadados que representa o tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="b11e2-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="b11e2-107">fora O nome do tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="b11e2-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b11e2-108">no O tamanho, em caracteres largos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="b11e2-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b11e2-109">fora O número de caracteres largos realmente retornados em `szName`</span><span class="sxs-lookup"><span data-stu-id="b11e2-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="b11e2-110">fora Um `mdFile` `mdAssemblyRef` token de metadados, ou `mdExportedType` que contém ou permite o acesso às propriedades do tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="b11e2-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="b11e2-111">fora Um ponteiro para um `mdTypeDef` token que representa um tipo no arquivo.</span><span class="sxs-lookup"><span data-stu-id="b11e2-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="b11e2-112">fora Um ponteiro para os sinalizadores que descrevem os metadados aplicados ao tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="b11e2-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="b11e2-113">O valor de flags pode ser um ou mais valores de [CorTypeAttr](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b11e2-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b11e2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b11e2-114">Requirements</span></span>  

 <span data-ttu-id="b11e2-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b11e2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b11e2-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b11e2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b11e2-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b11e2-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b11e2-118">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b11e2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b11e2-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="b11e2-119">See also</span></span>

- [<span data-ttu-id="b11e2-120">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b11e2-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
