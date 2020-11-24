---
title: Método IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 3c03497f48b8199da545d796637e5f8a5c532362
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675679"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="3eba9-102">Método IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="3eba9-102">IMetaDataEmit::DefineEvent Method</span></span>

<span data-ttu-id="3eba9-103">Cria uma definição para um evento com a assinatura de metadados especificada e Obtém um token para essa definição de evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eba9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3eba9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eba9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3eba9-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="3eba9-106">no O token para a classe ou interface de destino.</span><span class="sxs-lookup"><span data-stu-id="3eba9-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="3eba9-107">Esse é um `mdTypeDef` token ou `mdTypeDefNil` .</span><span class="sxs-lookup"><span data-stu-id="3eba9-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="3eba9-108">no O nome do evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="3eba9-109">no Sinalizadores de eventos.</span><span class="sxs-lookup"><span data-stu-id="3eba9-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="3eba9-110">no O token para a classe de evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-110">[in] The token for the event class.</span></span> <span data-ttu-id="3eba9-111">Este é um `mdTypeDef` , um `mdTypeRef` ou um `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="3eba9-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="3eba9-112">no O método usado para assinar o evento ou nulo.</span><span class="sxs-lookup"><span data-stu-id="3eba9-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="3eba9-113">no O método usado para cancelar a assinatura do evento, ou NULL.</span><span class="sxs-lookup"><span data-stu-id="3eba9-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="3eba9-114">no O método usado (por uma classe derivada) para gerar o evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="3eba9-115">no Uma matriz de tokens para outros métodos associados ao evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="3eba9-116">A matriz é encerrada com um `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="3eba9-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="3eba9-117">fora O token de metadados atribuído ao evento.</span><span class="sxs-lookup"><span data-stu-id="3eba9-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eba9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3eba9-118">Requirements</span></span>  

 <span data-ttu-id="3eba9-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eba9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eba9-120">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3eba9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3eba9-121">**Biblioteca:** Usado como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3eba9-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eba9-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eba9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eba9-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="3eba9-123">See also</span></span>

- [<span data-ttu-id="3eba9-124">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3eba9-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3eba9-125">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3eba9-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
