---
title: Método IMetaDataImport::EnumTypeSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 38c9f8df12b0fc83a236d2cb7c32d1198be7096d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719808"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="a4f0c-102">Método IMetaDataImport::EnumTypeSpecs</span><span class="sxs-lookup"><span data-stu-id="a4f0c-102">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="a4f0c-103">Enumera os tokens de TypeSpec definidos no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f0c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a4f0c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4f0c-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a4f0c-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a4f0c-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a4f0c-107">Esse valor deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="a4f0c-108">fora A matriz usada para armazenar os tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a4f0c-109">no O tamanho máximo da `rTypeSpecs` matriz.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="a4f0c-110">fora O número de tokens TypeSpec retornados em `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="a4f0c-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4f0c-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="a4f0c-111">Return Value</span></span>  
  
|<span data-ttu-id="a4f0c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4f0c-112">HRESULT</span></span>|<span data-ttu-id="a4f0c-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a4f0c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a4f0c-114">`EnumTypeSpecs` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a4f0c-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a4f0c-116">Nesse caso, `pcTypeSpecs` é zero.</span><span class="sxs-lookup"><span data-stu-id="a4f0c-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4f0c-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="a4f0c-117">Remarks</span></span>  

 <span data-ttu-id="a4f0c-118">Os tokens TypeSpec são criados pelo método [IMetaDataEmit:: GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4f0c-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4f0c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4f0c-119">Requirements</span></span>  

 <span data-ttu-id="a4f0c-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4f0c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f0c-121">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a4f0c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4f0c-122">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4f0c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4f0c-123">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4f0c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f0c-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="a4f0c-124">See also</span></span>

- [<span data-ttu-id="a4f0c-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a4f0c-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a4f0c-126">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a4f0c-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
