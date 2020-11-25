---
title: Método IMetaDataImport::EnumUserStrings
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: c7dcc740dcf9b228713693a57dc8ef96d215ebad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716553"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="13273-102">Método IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="13273-102">IMetaDataImport::EnumUserStrings Method</span></span>

<span data-ttu-id="13273-103">Enumera os tokens de cadeia de caracteres que representam cadeias embutidas em código no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="13273-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13273-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="13273-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13273-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="13273-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="13273-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="13273-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="13273-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="13273-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="13273-108">fora A matriz usada para armazenar os tokens de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="13273-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="13273-109">no O tamanho máximo da `rStrings` matriz.</span><span class="sxs-lookup"><span data-stu-id="13273-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="13273-110">fora O número de tokens de cadeia de caracteres retornados em `rStrings` .</span><span class="sxs-lookup"><span data-stu-id="13273-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13273-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="13273-111">Return Value</span></span>  
  
|<span data-ttu-id="13273-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13273-112">HRESULT</span></span>|<span data-ttu-id="13273-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="13273-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="13273-114">`EnumUserStrings` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="13273-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="13273-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="13273-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="13273-116">Nesse caso, `pcStrings` é zero.</span><span class="sxs-lookup"><span data-stu-id="13273-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13273-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="13273-117">Remarks</span></span>  

 <span data-ttu-id="13273-118">Os tokens de cadeia de caracteres são criados pelo método [IMetaDataEmit::D efineuserstring](imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13273-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="13273-119">Esse método é projetado para ser usado por um navegador de metadados em vez de por um compilador.</span><span class="sxs-lookup"><span data-stu-id="13273-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13273-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13273-120">Requirements</span></span>  

 <span data-ttu-id="13273-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13273-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13273-122">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13273-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13273-123">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13273-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13273-124">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13273-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13273-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="13273-125">See also</span></span>

- [<span data-ttu-id="13273-126">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="13273-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="13273-127">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="13273-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
