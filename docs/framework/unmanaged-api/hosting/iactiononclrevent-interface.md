---
title: Interface IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 8ca4bb1fe35451f95f752a4e71f5f0b541b55e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721771"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="18348-102">Interface IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="18348-102">IActionOnCLREvent Interface</span></span>

<span data-ttu-id="18348-103">Fornece o método [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) , que executa retornos de chamada em eventos que foram registrados usando uma chamada para o método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="18348-103">Provides the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18348-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="18348-104">Methods</span></span>  
  
|<span data-ttu-id="18348-105">Método</span><span class="sxs-lookup"><span data-stu-id="18348-105">Method</span></span>|<span data-ttu-id="18348-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="18348-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18348-107">Método OnEvent</span><span class="sxs-lookup"><span data-stu-id="18348-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="18348-108">Executa um retorno de chamada para um evento registrado.</span><span class="sxs-lookup"><span data-stu-id="18348-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18348-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18348-109">Requirements</span></span>  

 <span data-ttu-id="18348-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18348-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18348-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="18348-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18348-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18348-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18348-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18348-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18348-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="18348-114">See also</span></span>

- [<span data-ttu-id="18348-115">Enumeração EClrEvent</span><span class="sxs-lookup"><span data-stu-id="18348-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="18348-116">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="18348-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="18348-117">Interface ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="18348-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="18348-118">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="18348-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
