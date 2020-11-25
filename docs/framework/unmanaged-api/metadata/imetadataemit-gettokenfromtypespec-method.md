---
title: Método IMetaDataEmit::GetTokenFromTypeSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 3a8f369728b8464850259518981bf6690cb17a01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722031"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="06073-102">Método IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="06073-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="06073-103">Obtém um token de metadados para o tipo com a assinatura de metadados especificada.</span><span class="sxs-lookup"><span data-stu-id="06073-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06073-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="06073-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06073-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="06073-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="06073-106">no A assinatura que está sendo definida.</span><span class="sxs-lookup"><span data-stu-id="06073-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="06073-107">no A contagem de bytes em `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="06073-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="06073-108">fora O `mdTypeSpec` token atribuído.</span><span class="sxs-lookup"><span data-stu-id="06073-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06073-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06073-109">Requirements</span></span>  

 <span data-ttu-id="06073-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06073-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06073-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06073-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06073-112">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06073-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06073-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06073-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06073-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="06073-114">See also</span></span>

- [<span data-ttu-id="06073-115">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="06073-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="06073-116">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="06073-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
