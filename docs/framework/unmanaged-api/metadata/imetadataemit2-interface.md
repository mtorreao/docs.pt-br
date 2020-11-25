---
title: Interface IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: b8ad159dace734c343297b256092162f17ab829b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726477"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="3a9b0-102">Interface IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3a9b0-102">IMetaDataEmit2 Interface</span></span>

<span data-ttu-id="3a9b0-103">Estende a interface [IMetaDataEmit](imetadataemit-interface.md) principalmente para fornecer a capacidade de trabalhar com tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-103">Extends the [IMetaDataEmit](imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a9b0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3a9b0-104">Methods</span></span>  
  
|<span data-ttu-id="3a9b0-105">Método</span><span class="sxs-lookup"><span data-stu-id="3a9b0-105">Method</span></span>|<span data-ttu-id="3a9b0-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3a9b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a9b0-107">Método DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="3a9b0-107">DefineGenericParam Method</span></span>](imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="3a9b0-108">Cria uma definição para um parâmetro de tipo genérico e Obtém um token para esse parâmetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="3a9b0-109">Método DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="3a9b0-109">DefineMethodSpec Method</span></span>](imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="3a9b0-110">Cria uma instância genérica de um método e Obtém um token para a definição.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="3a9b0-111">Método GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="3a9b0-111">GetDeltaSaveSize Method</span></span>](imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="3a9b0-112">Obtém um valor que indica a diferença no tamanho dos dados necessários para expressar as alterações da sessão de edição e continuação atual.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="3a9b0-113">Método ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="3a9b0-113">ResetENCLog Method</span></span>](imetadataemit2-resetenclog-method.md)|<span data-ttu-id="3a9b0-114">Redefine o log de edição e continuação e inicia uma nova sessão.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="3a9b0-115">Método SaveDelta</span><span class="sxs-lookup"><span data-stu-id="3a9b0-115">SaveDelta Method</span></span>](imetadataemit2-savedelta-method.md)|<span data-ttu-id="3a9b0-116">Salva as alterações da sessão de edição e continuação atual para o arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="3a9b0-117">Método SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="3a9b0-117">SaveDeltaToMemory Method</span></span>](imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="3a9b0-118">Salva as alterações da sessão de edição e continuação atual na memória.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="3a9b0-119">Método SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="3a9b0-119">SaveDeltaToStream Method</span></span>](imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="3a9b0-120">Salva as alterações da sessão de edição e continuação atual para o fluxo especificado.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="3a9b0-121">Método SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="3a9b0-121">SetGenericParamProps Method</span></span>](imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="3a9b0-122">Define valores de propriedade para a definição de parâmetro genérico referenciada pelo token especificado.</span><span class="sxs-lookup"><span data-stu-id="3a9b0-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a9b0-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a9b0-123">Requirements</span></span>  

 <span data-ttu-id="3a9b0-124">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a9b0-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9b0-125">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a9b0-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a9b0-126">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a9b0-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a9b0-127">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9b0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9b0-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a9b0-128">See also</span></span>

- [<span data-ttu-id="3a9b0-129">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="3a9b0-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="3a9b0-130">Interface IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3a9b0-130">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
