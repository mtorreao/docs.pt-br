---
title: Método IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702674"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="d2d7a-102">Método IMetaDataImport2::GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="d2d7a-102">IMetaDataImport2::GetGenericParamProps Method</span></span>

<span data-ttu-id="d2d7a-103">Obtém os metadados associados ao parâmetro genérico representado pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2d7a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d2d7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2d7a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d2d7a-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="d2d7a-106">no O token que representa o parâmetro genérico para o qual retornar metadados.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="d2d7a-107">fora A posição ordinal do `Type` parâmetro no construtor ou método pai.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="d2d7a-108">fora Um valor da enumeração [CorGenericParamAttr](corgenericparamattr-enumeration.md) que descreve o `Type` para o parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-108">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="d2d7a-109">fora Um TypeDef ou token MethodDef que representa o proprietário do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="d2d7a-110">fora Reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="d2d7a-111">fora O nome do parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d2d7a-112">no O tamanho do `wzName` buffer.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d2d7a-113">fora O tamanho retornado do nome, em caracteres largos.</span><span class="sxs-lookup"><span data-stu-id="d2d7a-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2d7a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2d7a-114">Requirements</span></span>  

 <span data-ttu-id="d2d7a-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2d7a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2d7a-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d2d7a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2d7a-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2d7a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2d7a-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2d7a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d7a-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2d7a-119">See also</span></span>

- [<span data-ttu-id="d2d7a-120">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d2d7a-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="d2d7a-121">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d2d7a-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
