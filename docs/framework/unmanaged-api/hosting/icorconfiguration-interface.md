---
title: Interface ICorConfiguration
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: fa8d15bc8e504a57d5cc87c170a3a5b022798add
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715778"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="6d6f3-102">Interface ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="6d6f3-102">ICorConfiguration Interface</span></span>

<span data-ttu-id="6d6f3-103">Fornece métodos para configurar o Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6d6f3-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d6f3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d6f3-104">Methods</span></span>  
  
|<span data-ttu-id="6d6f3-105">Método</span><span class="sxs-lookup"><span data-stu-id="6d6f3-105">Method</span></span>|<span data-ttu-id="6d6f3-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="6d6f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d6f3-107">Método AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="6d6f3-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="6d6f3-108">Indica aos serviços de depuração que um thread específico deve ter permissão para continuar a execução enquanto o depurador tem um aplicativo interrompido durante cenários de depuração gerenciados ou não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="6d6f3-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="6d6f3-109">Método SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="6d6f3-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="6d6f3-110">Define a interface de retorno de chamada que os serviços de depuração chamarão como threads CLR são bloqueados e desbloqueados para depuração.</span><span class="sxs-lookup"><span data-stu-id="6d6f3-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="6d6f3-111">Método SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="6d6f3-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="6d6f3-112">Define a interface de retorno de chamada a ser usada pelo coletor de lixo para solicitar que o host altere os limites de memória virtual.</span><span class="sxs-lookup"><span data-stu-id="6d6f3-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="6d6f3-113">Método SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="6d6f3-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="6d6f3-114">Define a interface de retorno de chamada para o agendamento de threads para tarefas sem tempo de execução que, de outra forma, seriam bloqueadas para uma coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="6d6f3-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d6f3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d6f3-115">Requirements</span></span>  

 <span data-ttu-id="6d6f3-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6f3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6f3-117">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6d6f3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d6f3-118">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d6f3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d6f3-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6f3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6f3-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d6f3-120">See also</span></span>

- [<span data-ttu-id="6d6f3-121">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="6d6f3-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="6d6f3-122">Coclass CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6d6f3-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
