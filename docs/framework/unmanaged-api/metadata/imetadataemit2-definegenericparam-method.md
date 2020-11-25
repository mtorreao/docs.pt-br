---
title: Método IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: c9ff918121e7bb4ee972e674207810358b3f36f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712905"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="2b28e-102">Método IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="2b28e-102">IMetaDataEmit2::DefineGenericParam Method</span></span>

<span data-ttu-id="2b28e-103">Cria uma definição para um parâmetro de tipo genérico e Obtém um token para esse parâmetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="2b28e-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b28e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2b28e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b28e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2b28e-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="2b28e-106">no Um `mdTypeDef` `mdMethodDef` token ou que representa o método ou construtor para o qual definir um parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2b28e-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="2b28e-107">no O índice do parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2b28e-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2b28e-108">no Um valor da enumeração [CorGenericParamAttr](corgenericparamattr-enumeration.md) que descreve o tipo para o parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2b28e-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="2b28e-109">no O nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2b28e-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2b28e-110">no Esse parâmetro é reservado para extensibilidade futura.</span><span class="sxs-lookup"><span data-stu-id="2b28e-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="2b28e-111">no Uma matriz de restrições de tipo terminada em zero.</span><span class="sxs-lookup"><span data-stu-id="2b28e-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="2b28e-112">Os membros da matriz devem ser um `mdTypeDef` `mdTypeRef` token de metadados, ou `mdTypeSpec` .</span><span class="sxs-lookup"><span data-stu-id="2b28e-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="2b28e-113">fora Um token que representa o parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="2b28e-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b28e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b28e-114">Requirements</span></span>  

 <span data-ttu-id="2b28e-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b28e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b28e-116">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2b28e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b28e-117">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b28e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b28e-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b28e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b28e-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b28e-119">See also</span></span>

- [<span data-ttu-id="2b28e-120">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2b28e-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="2b28e-121">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2b28e-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
