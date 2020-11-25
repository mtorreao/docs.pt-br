---
title: Método IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720406"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="399be-102">Método IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="399be-102">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="399be-103">Enumera os tokens de TypeDef que representam todos os tipos no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="399be-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="399be-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="399be-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="399be-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="399be-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="399be-106">fora Um ponteiro para o novo enumerador.</span><span class="sxs-lookup"><span data-stu-id="399be-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="399be-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="399be-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="399be-108">no A matriz usada para armazenar os tokens de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="399be-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="399be-109">no O tamanho máximo da `rTypeDefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="399be-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="399be-110">fora O número de tokens de TypeDef retornados em `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="399be-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="399be-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="399be-111">Return Value</span></span>  
  
|<span data-ttu-id="399be-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="399be-112">HRESULT</span></span>|<span data-ttu-id="399be-113">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="399be-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="399be-114">`EnumTypeDefs` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="399be-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="399be-115">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="399be-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="399be-116">Nesse caso, `pcTypeDefs` é zero.</span><span class="sxs-lookup"><span data-stu-id="399be-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="399be-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="399be-117">Remarks</span></span>  

 <span data-ttu-id="399be-118">O token TypeDef representa um tipo como uma classe ou uma interface, bem como qualquer tipo adicionado por meio de um mecanismo de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="399be-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="399be-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="399be-119">Requirements</span></span>  

 <span data-ttu-id="399be-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="399be-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="399be-121">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="399be-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="399be-122">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="399be-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="399be-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="399be-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399be-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="399be-124">See also</span></span>

- [<span data-ttu-id="399be-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="399be-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="399be-126">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="399be-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
