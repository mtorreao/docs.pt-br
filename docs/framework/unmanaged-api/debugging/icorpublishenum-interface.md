---
title: Interface ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 492d4b727ce507340fec47d30a791aa49d0cecb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693340"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="58484-102">Interface ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="58484-102">ICorPublishEnum Interface</span></span>

<span data-ttu-id="58484-103">Serve como a interface base abstrata para os enumeradores que são usados na publicação de informações sobre processos e domínios de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="58484-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58484-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="58484-104">Methods</span></span>  
  
|<span data-ttu-id="58484-105">Método</span><span class="sxs-lookup"><span data-stu-id="58484-105">Method</span></span>|<span data-ttu-id="58484-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="58484-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58484-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="58484-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="58484-108">Cria uma cópia deste objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="58484-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="58484-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="58484-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="58484-110">Obtém o número de itens na enumeração.</span><span class="sxs-lookup"><span data-stu-id="58484-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="58484-111">Método Reset</span><span class="sxs-lookup"><span data-stu-id="58484-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="58484-112">Move o cursor de para o início da enumeração.</span><span class="sxs-lookup"><span data-stu-id="58484-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="58484-113">Método Skip</span><span class="sxs-lookup"><span data-stu-id="58484-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="58484-114">Move o cursor para a frente na enumeração pelo número especificado de itens.</span><span class="sxs-lookup"><span data-stu-id="58484-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58484-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="58484-115">Remarks</span></span>  

 <span data-ttu-id="58484-116">Os seguintes enumeradores derivam de `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="58484-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="58484-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="58484-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="58484-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="58484-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="58484-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58484-119">Requirements</span></span>  

 <span data-ttu-id="58484-120">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58484-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58484-121">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="58484-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="58484-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58484-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58484-123">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58484-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58484-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="58484-124">See also</span></span>

- [<span data-ttu-id="58484-125">Coclass CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="58484-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="58484-126">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="58484-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
