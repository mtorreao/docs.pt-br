---
title: Método IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: c72e5b9544d1d8ae989405ac9bfdb22050b1aaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731599"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="9f184-102">Método IMetaDataAssemblyImport::EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="9f184-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>

<span data-ttu-id="9f184-103">Obtém um ponteiro para um enumerador para os recursos referenciados no manifesto do assembly atual.</span><span class="sxs-lookup"><span data-stu-id="9f184-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f184-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f184-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="9f184-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9f184-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="9f184-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="9f184-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9f184-107">Esse deve ser um valor nulo quando o `EnumManifestResources` método é chamado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9f184-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="9f184-108">fora A matriz usada para armazenar os `mdManifestResource` tokens de metadados.</span><span class="sxs-lookup"><span data-stu-id="9f184-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9f184-109">no O número máximo de `mdManifestResource` tokens que podem ser colocados `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="9f184-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="9f184-110">fora O número de `mdManifestResource` tokens realmente colocados no `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="9f184-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f184-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="9f184-111">Return Value</span></span>  
  
|<span data-ttu-id="9f184-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f184-112">HRESULT</span></span>|<span data-ttu-id="9f184-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9f184-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9f184-114">`EnumManifestResources` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9f184-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9f184-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="9f184-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9f184-116">Nesse caso, `pcTokens` é definido como zero.</span><span class="sxs-lookup"><span data-stu-id="9f184-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f184-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f184-117">Requirements</span></span>  

 <span data-ttu-id="9f184-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f184-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f184-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9f184-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f184-120">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f184-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f184-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f184-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f184-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f184-122">See also</span></span>

- [<span data-ttu-id="9f184-123">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9f184-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
