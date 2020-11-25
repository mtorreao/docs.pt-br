---
title: Método IMetaDataAssemblyImport::EnumExportedTypes
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708888"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="3bae7-102">Método IMetaDataAssemblyImport::EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="3bae7-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="3bae7-103">Enumera os tipos exportados referenciados no manifesto do assembly no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="3bae7-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bae7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3bae7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bae7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3bae7-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3bae7-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="3bae7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3bae7-107">Esse deve ser um valor nulo quando o `EnumExportedTypes` método é chamado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3bae7-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="3bae7-108">fora A enumeração de `mdExportedType` tokens de metadados.</span><span class="sxs-lookup"><span data-stu-id="3bae7-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3bae7-109">no O número máximo de `mdExportedType` tokens que podem ser colocados na `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="3bae7-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3bae7-110">fora O número de `mdExportedType` tokens realmente colocados no `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="3bae7-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bae7-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3bae7-111">Return Value</span></span>  
  
|<span data-ttu-id="3bae7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bae7-112">HRESULT</span></span>|<span data-ttu-id="3bae7-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3bae7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3bae7-114">`EnumExportedTypes` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3bae7-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3bae7-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="3bae7-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3bae7-116">Nesse caso, `pcTokens` é definido como zero.</span><span class="sxs-lookup"><span data-stu-id="3bae7-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bae7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bae7-117">Requirements</span></span>  

 <span data-ttu-id="3bae7-118">**Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bae7-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bae7-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3bae7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bae7-120">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bae7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bae7-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bae7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bae7-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="3bae7-122">See also</span></span>

- [<span data-ttu-id="3bae7-123">Interface IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3bae7-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
