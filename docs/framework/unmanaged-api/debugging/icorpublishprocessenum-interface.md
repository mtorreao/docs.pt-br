---
title: Interface ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: ebf484524b32d8e917d88c21425fab314dfc41be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692612"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="f95d4-102">Interface ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="f95d4-102">ICorPublishProcessEnum Interface</span></span>

<span data-ttu-id="f95d4-103">Uma subclasse da interface [ICorPublishEnum](icorpublishenum-interface.md) que fornece métodos para atravessar uma coleção de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f95d4-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f95d4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f95d4-104">Methods</span></span>  
  
|<span data-ttu-id="f95d4-105">Método</span><span class="sxs-lookup"><span data-stu-id="f95d4-105">Method</span></span>|<span data-ttu-id="f95d4-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f95d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f95d4-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="f95d4-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="f95d4-108">Obtém o número especificado de `ICorPublishProcess` instâncias da coleção, começando na posição atual.</span><span class="sxs-lookup"><span data-stu-id="f95d4-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f95d4-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="f95d4-109">Remarks</span></span>  

 <span data-ttu-id="f95d4-110">A `ICorPublishProcessEnum` interface implementa os métodos da interface abstrata, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f95d4-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="f95d4-111">Uma `ICorPublishProcessEnum` instância é criada pelo método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f95d4-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="f95d4-112">A passagem da coleção de `ICorPublishProcess` objetos é baseada nos critérios de filtro fornecidos no momento em que a `ICorPublishProcessEnum` instância foi criada.</span><span class="sxs-lookup"><span data-stu-id="f95d4-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f95d4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f95d4-113">Requirements</span></span>  

 <span data-ttu-id="f95d4-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f95d4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f95d4-115">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f95d4-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f95d4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f95d4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f95d4-117">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f95d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f95d4-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="f95d4-118">See also</span></span>

- [<span data-ttu-id="f95d4-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="f95d4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f95d4-120">Coclass CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="f95d4-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
