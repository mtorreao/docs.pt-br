---
title: Interface IMetaDataError
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701920"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="b2484-102">Interface IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="b2484-102">IMetaDataError Interface</span></span>

<span data-ttu-id="b2484-103">Fornece um mecanismo de retorno de chamada para relatar erros durante a mesclagem de metadados.</span><span class="sxs-lookup"><span data-stu-id="b2484-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2484-104">A `IMetaDataError` interface deve ser implementada pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="b2484-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2484-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b2484-105">Methods</span></span>  
  
|<span data-ttu-id="b2484-106">Método</span><span class="sxs-lookup"><span data-stu-id="b2484-106">Method</span></span>|<span data-ttu-id="b2484-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b2484-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2484-108">Método OnError</span><span class="sxs-lookup"><span data-stu-id="b2484-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="b2484-109">Fornece uma notificação de erros que ocorrem durante a mesclagem de metadados.</span><span class="sxs-lookup"><span data-stu-id="b2484-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2484-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2484-110">Requirements</span></span>  

 <span data-ttu-id="b2484-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2484-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2484-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b2484-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2484-113">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2484-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2484-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2484-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2484-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="b2484-115">See also</span></span>

- [<span data-ttu-id="b2484-116">Interfaces de metadados</span><span class="sxs-lookup"><span data-stu-id="b2484-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
