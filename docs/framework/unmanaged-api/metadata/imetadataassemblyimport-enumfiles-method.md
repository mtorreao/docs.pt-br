---
title: Método IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: f9af770f3bdca98f6b3d06d8b0fe6c92745f73e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731604"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="e67ce-102">Método IMetaDataAssemblyImport::EnumFiles</span><span class="sxs-lookup"><span data-stu-id="e67ce-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>

<span data-ttu-id="e67ce-103">Enumera os arquivos referenciados no manifesto do assembly atual.</span><span class="sxs-lookup"><span data-stu-id="e67ce-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67ce-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e67ce-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e67ce-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e67ce-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e67ce-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="e67ce-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e67ce-107">Deve ser um valor nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="e67ce-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="e67ce-108">fora A matriz usada para armazenar os `mdFile` tokens de metadados.</span><span class="sxs-lookup"><span data-stu-id="e67ce-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e67ce-109">no O número máximo de `mdFile` tokens que podem ser colocados `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="e67ce-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e67ce-110">fora O número de `mdFile` tokens realmente colocados no `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="e67ce-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e67ce-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e67ce-111">Return Value</span></span>  
  
|<span data-ttu-id="e67ce-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e67ce-112">HRESULT</span></span>|<span data-ttu-id="e67ce-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e67ce-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e67ce-114">`EnumFiles` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e67ce-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e67ce-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e67ce-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e67ce-116">Nesse caso, `pcTokens` é definido como zero.</span><span class="sxs-lookup"><span data-stu-id="e67ce-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e67ce-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e67ce-117">Requirements</span></span>  

 <span data-ttu-id="e67ce-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e67ce-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67ce-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e67ce-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e67ce-120">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e67ce-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e67ce-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67ce-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67ce-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="e67ce-122">See also</span></span>

- [<span data-ttu-id="e67ce-123">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="e67ce-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
