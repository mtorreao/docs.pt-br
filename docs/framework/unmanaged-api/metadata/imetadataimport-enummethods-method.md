---
title: Método IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 00726b7e74bdedc658886cccbc4329eaf3ae76d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696798"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="1b726-102">Método IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="1b726-102">IMetaDataImport::EnumMethods Method</span></span>

<span data-ttu-id="1b726-103">Enumera tokens MethodDef que representam métodos do tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1b726-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b726-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1b726-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b726-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1b726-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="1b726-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="1b726-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1b726-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="1b726-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="1b726-108">no Um token de TypeDef que representa o tipo com os métodos a serem enumerados.</span><span class="sxs-lookup"><span data-stu-id="1b726-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="1b726-109">fora A matriz para armazenar os tokens MethodDef.</span><span class="sxs-lookup"><span data-stu-id="1b726-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1b726-110">no O tamanho máximo da matriz MethodDef `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="1b726-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1b726-111">fora O número de tokens MethodDef retornados em `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="1b726-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b726-112">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="1b726-112">Return Value</span></span>  
  
|<span data-ttu-id="1b726-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b726-113">HRESULT</span></span>|<span data-ttu-id="1b726-114">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1b726-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1b726-115">`EnumMethods` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="1b726-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1b726-116">Não há tokens MethodDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="1b726-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="1b726-117">Nesse caso, `pcTokens` é zero.</span><span class="sxs-lookup"><span data-stu-id="1b726-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b726-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b726-118">Requirements</span></span>  

 <span data-ttu-id="1b726-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b726-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b726-120">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1b726-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b726-121">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b726-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b726-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b726-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b726-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="1b726-123">See also</span></span>

- [<span data-ttu-id="1b726-124">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1b726-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1b726-125">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1b726-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
