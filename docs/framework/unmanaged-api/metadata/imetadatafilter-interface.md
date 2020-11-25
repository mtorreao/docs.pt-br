---
title: Interface IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701842"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="37b7f-102">Interface IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="37b7f-102">IMetaDataFilter Interface</span></span>

<span data-ttu-id="37b7f-103">Fornece métodos para marcação e filtragem de tokens de metadados para evitar ações repetidas que já foram realizadas.</span><span class="sxs-lookup"><span data-stu-id="37b7f-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37b7f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="37b7f-104">Methods</span></span>  
  
|<span data-ttu-id="37b7f-105">Método</span><span class="sxs-lookup"><span data-stu-id="37b7f-105">Method</span></span>|<span data-ttu-id="37b7f-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="37b7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37b7f-107">Método IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="37b7f-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="37b7f-108">Obtém um valor que indica se o token de metadados especificado foi processado.</span><span class="sxs-lookup"><span data-stu-id="37b7f-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="37b7f-109">Método MarkToken</span><span class="sxs-lookup"><span data-stu-id="37b7f-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="37b7f-110">Define um valor que indica que o token de metadados especificado foi processado.</span><span class="sxs-lookup"><span data-stu-id="37b7f-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="37b7f-111">Método UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="37b7f-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="37b7f-112">Remove as marcas de processamento de todos os tokens no escopo de metadados atual.</span><span class="sxs-lookup"><span data-stu-id="37b7f-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37b7f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37b7f-113">Requirements</span></span>  

 <span data-ttu-id="37b7f-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b7f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b7f-115">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="37b7f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37b7f-116">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37b7f-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37b7f-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b7f-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="37b7f-118">See also</span></span>

- [<span data-ttu-id="37b7f-119">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="37b7f-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
