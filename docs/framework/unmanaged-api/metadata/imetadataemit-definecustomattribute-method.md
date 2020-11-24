---
title: Método IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 096a460f9d6581ebdd00f8487af68f652524d52f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681659"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="de849-102">Método IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="de849-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="de849-103">Cria uma definição para um atributo personalizado com a assinatura de metadados especificada, a ser anexada ao objeto especificado e Obtém um token para essa definição de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="de849-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de849-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="de849-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de849-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="de849-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="de849-106">no O token para o item de proprietário.</span><span class="sxs-lookup"><span data-stu-id="de849-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="de849-107">no O token que identifica o atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="de849-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="de849-108">no Um ponteiro para o atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="de849-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="de849-109">no A contagem de bytes em `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="de849-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="de849-110">fora O `mdCustomAttribute` token atribuído.</span><span class="sxs-lookup"><span data-stu-id="de849-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de849-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de849-111">Requirements</span></span>  

 <span data-ttu-id="de849-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de849-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de849-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="de849-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de849-114">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de849-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de849-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de849-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de849-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="de849-116">See also</span></span>

- [<span data-ttu-id="de849-117">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="de849-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="de849-118">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="de849-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
