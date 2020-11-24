---
title: Método IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690485"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="e32c8-102">Método IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="e32c8-102">IMetaDataImport::EnumPermissionSets Method</span></span>

<span data-ttu-id="e32c8-103">Enumera permissões para os objetos em um escopo de metadados especificado.</span><span class="sxs-lookup"><span data-stu-id="e32c8-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32c8-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e32c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e32c8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e32c8-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e32c8-106">[entrada, saída] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="e32c8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e32c8-107">Isso deve ser nulo para a primeira chamada deste método.</span><span class="sxs-lookup"><span data-stu-id="e32c8-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="e32c8-108">no Um token de metadados que limita o escopo da pesquisa ou nulo para pesquisar o escopo mais amplo possível.</span><span class="sxs-lookup"><span data-stu-id="e32c8-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="e32c8-109">no Sinalizadores que representam os <xref:System.Security.Permissions.SecurityAction> valores a serem incluídos `rPermission` ou zero para retornar todas as ações.</span><span class="sxs-lookup"><span data-stu-id="e32c8-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="e32c8-110">fora A matriz usada para armazenar os tokens de permissão.</span><span class="sxs-lookup"><span data-stu-id="e32c8-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e32c8-111">no O tamanho máximo da `rPermission` matriz.</span><span class="sxs-lookup"><span data-stu-id="e32c8-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e32c8-112">fora O número de tokens de permissão retornados em `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="e32c8-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e32c8-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="e32c8-113">Return Value</span></span>  
  
|<span data-ttu-id="e32c8-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e32c8-114">HRESULT</span></span>|<span data-ttu-id="e32c8-115">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="e32c8-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e32c8-116">`EnumPermissionSets` retornado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e32c8-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e32c8-117">Não há tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e32c8-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="e32c8-118">Nesse caso, `pcTokens` é zero.</span><span class="sxs-lookup"><span data-stu-id="e32c8-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e32c8-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e32c8-119">Requirements</span></span>  

 <span data-ttu-id="e32c8-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32c8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32c8-121">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e32c8-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e32c8-122">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e32c8-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e32c8-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32c8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32c8-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="e32c8-124">See also</span></span>

- [<span data-ttu-id="e32c8-125">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e32c8-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e32c8-126">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e32c8-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
