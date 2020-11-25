---
title: Método IMetaDataImport::EnumFields
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711579"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="2c2f6-102">Método IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="2c2f6-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="2c2f6-103">Enumera os tokens FieldDef para o tipo referenciado pelo token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2f6-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c2f6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2f6-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2c2f6-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="2c2f6-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="2c2f6-107">no O token de TypeDef da classe cujos campos devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="2c2f6-108">fora A lista de tokens FieldDef.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2c2f6-109">no O tamanho máximo da `rFields` matriz.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2c2f6-110">fora O número real de tokens FieldDef retornados em `rFields` .</span><span class="sxs-lookup"><span data-stu-id="2c2f6-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c2f6-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="2c2f6-111">Return Value</span></span>  
  
|<span data-ttu-id="2c2f6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c2f6-112">HRESULT</span></span>|<span data-ttu-id="2c2f6-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2c2f6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2c2f6-114">`EnumFields` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2c2f6-115">Não há campos para enumerar.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-115">There are no fields to enumerate.</span></span> <span data-ttu-id="2c2f6-116">Nesse caso, `pcTokens` é zero.</span><span class="sxs-lookup"><span data-stu-id="2c2f6-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c2f6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c2f6-117">Requirements</span></span>  

 <span data-ttu-id="2c2f6-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2f6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2f6-119">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c2f6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c2f6-120">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c2f6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2f6-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2f6-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c2f6-122">See also</span></span>

- [<span data-ttu-id="2c2f6-123">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2c2f6-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2c2f6-124">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2c2f6-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
