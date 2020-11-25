---
title: Estrutura MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 8e88d90e3291d21888fae7aa162f84b6377658c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730013"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="404f9-102">Estrutura MDAInfo</span><span class="sxs-lookup"><span data-stu-id="404f9-102">MDAInfo Structure</span></span>

<span data-ttu-id="404f9-103">Fornece detalhes sobre o `Event_MDAFired` evento, que dispara a criação de um MDA (Assistente de depuração gerenciada).</span><span class="sxs-lookup"><span data-stu-id="404f9-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404f9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="404f9-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="404f9-105">Membros</span><span class="sxs-lookup"><span data-stu-id="404f9-105">Members</span></span>  
  
|<span data-ttu-id="404f9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="404f9-106">Member</span></span>|<span data-ttu-id="404f9-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="404f9-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="404f9-108">O título do MDA atual.</span><span class="sxs-lookup"><span data-stu-id="404f9-108">The title of the current MDA.</span></span> <span data-ttu-id="404f9-109">O título descreve o tipo de falha que disparou o `Event_MDAFired` evento.</span><span class="sxs-lookup"><span data-stu-id="404f9-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="404f9-110">A mensagem de saída fornecida pelo MDA atual.</span><span class="sxs-lookup"><span data-stu-id="404f9-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="404f9-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="404f9-111">Remarks</span></span>  

 <span data-ttu-id="404f9-112">Os assistentes de depuração gerenciada (MDAs) são ferramentas de depuração que funcionam em conjunto com o Common Language Runtime (CLR) para executar tarefas como identificar condições inválidas no mecanismo de execução de tempo de execução ou despejar informações adicionais sobre o estado do mecanismo.</span><span class="sxs-lookup"><span data-stu-id="404f9-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="404f9-113">MDAs gerar mensagens XML sobre eventos que, de outra forma, são difíceis de interceptar.</span><span class="sxs-lookup"><span data-stu-id="404f9-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="404f9-114">Eles são especialmente úteis para a depuração de transições entre códigos gerenciados e não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="404f9-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="404f9-115">O tempo de execução executa as seguintes etapas quando um evento que dispara a criação de um MDA é acionado:</span><span class="sxs-lookup"><span data-stu-id="404f9-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="404f9-116">Se o host não tiver registrado uma instância de [IActionOnCLREvent](iactiononclrevent-interface.md) chamando [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) para ser notificado de um `Event_MDAFired` evento, o tempo de execução continuará com seu comportamento padrão não hospedado.</span><span class="sxs-lookup"><span data-stu-id="404f9-116">If the host has not registered an [IActionOnCLREvent](iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="404f9-117">Se o host tiver registrado um manipulador para esse evento, o tempo de execução verificará se um depurador está anexado ao processo.</span><span class="sxs-lookup"><span data-stu-id="404f9-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="404f9-118">Se for, o tempo de execução será interrompido no depurador.</span><span class="sxs-lookup"><span data-stu-id="404f9-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="404f9-119">Quando o depurador continuar, ele chamará o host.</span><span class="sxs-lookup"><span data-stu-id="404f9-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="404f9-120">Se nenhum depurador estiver anexado, o tempo de execução chamará `IActionOnCLREvent::OnEvent` e passará um ponteiro para uma `MDAInfo` instância como o `data` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="404f9-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="404f9-121">O host pode optar por ativar o MDAs e ser notificado quando um MDA for ativado.</span><span class="sxs-lookup"><span data-stu-id="404f9-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="404f9-122">Isso dá ao host uma oportunidade de substituir o comportamento padrão e anular o thread gerenciado que disparou o evento, para impedir que ele corrompa o estado do processo.</span><span class="sxs-lookup"><span data-stu-id="404f9-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="404f9-123">Para obter mais informações sobre como usar o MDAs, consulte [diagnosticando erros com assistentes de depuração gerenciada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="404f9-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="404f9-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="404f9-124">Requirements</span></span>  

 <span data-ttu-id="404f9-125">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404f9-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404f9-126">**Cabeçalho:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="404f9-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="404f9-127">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="404f9-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="404f9-128">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404f9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404f9-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="404f9-129">See also</span></span>

- [<span data-ttu-id="404f9-130">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="404f9-130">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="404f9-131">Diagnosticando erros com assistentes de depuração gerenciados</span><span class="sxs-lookup"><span data-stu-id="404f9-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
