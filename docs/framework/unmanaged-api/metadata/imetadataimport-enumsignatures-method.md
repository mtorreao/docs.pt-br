---
title: Método IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 3021124184ab0491337a07144e6f77b5bfea3681
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721966"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="4ac37-102">Método IMetaDataImport::EnumSignatures</span><span class="sxs-lookup"><span data-stu-id="4ac37-102">IMetaDataImport::EnumSignatures Method</span></span>

<span data-ttu-id="4ac37-103">Enumera os tokens de assinatura que representam assinaturas autônomas no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="4ac37-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac37-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4ac37-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ac37-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4ac37-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4ac37-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="4ac37-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4ac37-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="4ac37-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="4ac37-108">fora A matriz usada para armazenar os tokens de assinatura.</span><span class="sxs-lookup"><span data-stu-id="4ac37-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4ac37-109">no O tamanho máximo da `rSignatures` matriz.</span><span class="sxs-lookup"><span data-stu-id="4ac37-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="4ac37-110">fora O número de tokens de assinatura retornados em `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="4ac37-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ac37-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="4ac37-111">Return Value</span></span>  
  
|<span data-ttu-id="4ac37-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ac37-112">HRESULT</span></span>|<span data-ttu-id="4ac37-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4ac37-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4ac37-114">`EnumSignatures` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="4ac37-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4ac37-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="4ac37-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4ac37-116">Nesse caso, `pcSignatures` é zero.</span><span class="sxs-lookup"><span data-stu-id="4ac37-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ac37-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="4ac37-117">Remarks</span></span>  

 <span data-ttu-id="4ac37-118">Os tokens de assinatura são criados pelo método [IMetaDataEmit:: GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4ac37-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac37-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ac37-119">Requirements</span></span>  

 <span data-ttu-id="4ac37-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ac37-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac37-121">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4ac37-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ac37-122">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ac37-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ac37-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac37-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac37-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ac37-124">See also</span></span>

- [<span data-ttu-id="4ac37-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4ac37-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4ac37-126">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4ac37-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
