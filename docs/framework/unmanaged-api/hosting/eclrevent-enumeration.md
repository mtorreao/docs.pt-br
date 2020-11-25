---
title: Enumeração EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 5d6ec42da60a7b294177063b9f8bd5afbf352c62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726815"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="1c900-102">Enumeração EClrEvent</span><span class="sxs-lookup"><span data-stu-id="1c900-102">EClrEvent Enumeration</span></span>

<span data-ttu-id="1c900-103">Descreve os eventos de Common Language Runtime (CLR) para os quais o host pode registrar retornos de chamada.</span><span class="sxs-lookup"><span data-stu-id="1c900-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c900-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c900-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="1c900-105">Membros</span><span class="sxs-lookup"><span data-stu-id="1c900-105">Members</span></span>  
  
|<span data-ttu-id="1c900-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1c900-106">Member</span></span>|<span data-ttu-id="1c900-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="1c900-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="1c900-108">Especifica um erro fatal de CLR.</span><span class="sxs-lookup"><span data-stu-id="1c900-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="1c900-109">Especifica o descarregamento de um específico <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="1c900-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="1c900-110">Especifica que uma mensagem do MDA (Assistente de depuração gerenciada) foi gerada.</span><span class="sxs-lookup"><span data-stu-id="1c900-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="1c900-111">Especifica que ocorreu um erro de estouro de pilha.</span><span class="sxs-lookup"><span data-stu-id="1c900-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c900-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="1c900-112">Remarks</span></span>  

 <span data-ttu-id="1c900-113">O host pode registrar retornos de chamada para qualquer um dos tipos de eventos descritos pela `EClrEvent` chamada de métodos da interface [ICLROnEventManager](iclroneventmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1c900-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="1c900-114">O host obtém um ponteiro para essa interface chamando o método [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c900-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="1c900-115">Os `Event_CLRDisabled` `Event_DomainUnload` eventos e podem ser gerados mais de uma vez e de threads diferentes para sinalizar um descarregamento ou a desabilitação do CLR.</span><span class="sxs-lookup"><span data-stu-id="1c900-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="1c900-116">O `Event_MDAFired` evento gera a criação de uma instância de [MDAInfo](mdainfo-structure.md) que contém os detalhes da mensagem do MDA.</span><span class="sxs-lookup"><span data-stu-id="1c900-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="1c900-117">Para obter mais informações sobre MDAs, consulte [diagnosticando erros com assistentes de depuração gerenciada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="1c900-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c900-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c900-118">Requirements</span></span>  

 <span data-ttu-id="1c900-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c900-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c900-120">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1c900-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c900-121">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c900-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c900-122">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c900-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c900-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="1c900-123">See also</span></span>

- [<span data-ttu-id="1c900-124">Interface IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="1c900-124">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="1c900-125">Interface ICLRControl</span><span class="sxs-lookup"><span data-stu-id="1c900-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="1c900-126">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="1c900-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
