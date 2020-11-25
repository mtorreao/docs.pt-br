---
title: Interface ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693080"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="2aa67-102">Interface ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="2aa67-102">ICorPublishProcess Interface</span></span>

<span data-ttu-id="2aa67-103">Fornece métodos que acessam informações a serem exibidas sobre um processo.</span><span class="sxs-lookup"><span data-stu-id="2aa67-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aa67-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2aa67-104">Methods</span></span>  
  
|<span data-ttu-id="2aa67-105">Método</span><span class="sxs-lookup"><span data-stu-id="2aa67-105">Method</span></span>|<span data-ttu-id="2aa67-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2aa67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aa67-107">Método EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="2aa67-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="2aa67-108">Obtém uma instância de [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) que contém os domínios de aplicativo no processo referenciado por isso `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="2aa67-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2aa67-109">Método GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="2aa67-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="2aa67-110">Obtém o caminho completo do executável para o processo referenciado por isso `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="2aa67-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2aa67-111">Método GetProcessID</span><span class="sxs-lookup"><span data-stu-id="2aa67-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="2aa67-112">Obtém o identificador do sistema operacional para o processo referenciado por isso `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="2aa67-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="2aa67-113">Método IsManaged</span><span class="sxs-lookup"><span data-stu-id="2aa67-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="2aa67-114">Obtém um valor que indica se o processo referenciado por isso `ICorPublishProcess` é conhecido por estar executando código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2aa67-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2aa67-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aa67-115">Requirements</span></span>  

 <span data-ttu-id="2aa67-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aa67-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa67-117">**Cabeçalho:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2aa67-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2aa67-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aa67-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aa67-119">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa67-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa67-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="2aa67-120">See also</span></span>

- [<span data-ttu-id="2aa67-121">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="2aa67-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2aa67-122">Coclass CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="2aa67-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
