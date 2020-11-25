---
title: Método IMetaDataImport::EnumProperties
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
ms.openlocfilehash: 24ee37a36e34c74258e1c750ba424640c0496f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728245"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="cc3d0-102">Método IMetaDataImport::EnumProperties</span><span class="sxs-lookup"><span data-stu-id="cc3d0-102">IMetaDataImport::EnumProperties Method</span></span>

<span data-ttu-id="cc3d0-103">Enumera os tokens PropertyDef que representam as propriedades do tipo referenciado pelo token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3d0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cc3d0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc3d0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cc3d0-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="cc3d0-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cc3d0-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="cc3d0-108">no Um token de TypeDef que representa o tipo com propriedades a serem enumeradas.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="cc3d0-109">fora A matriz usada para armazenar os tokens PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cc3d0-110">no O tamanho máximo da `rProperties` matriz.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="cc3d0-111">fora O número de tokens PropertyDef retornados em `rProperties` .</span><span class="sxs-lookup"><span data-stu-id="cc3d0-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc3d0-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="cc3d0-112">Return Value</span></span>  
  
|<span data-ttu-id="cc3d0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc3d0-113">HRESULT</span></span>|<span data-ttu-id="cc3d0-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="cc3d0-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cc3d0-115">`EnumProperties` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cc3d0-116">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="cc3d0-117">Nesse caso, `pcProperties` é zero.</span><span class="sxs-lookup"><span data-stu-id="cc3d0-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc3d0-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc3d0-118">Requirements</span></span>  

 <span data-ttu-id="cc3d0-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc3d0-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3d0-120">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cc3d0-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc3d0-121">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc3d0-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc3d0-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3d0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3d0-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc3d0-123">See also</span></span>

- [<span data-ttu-id="cc3d0-124">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cc3d0-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cc3d0-125">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cc3d0-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
