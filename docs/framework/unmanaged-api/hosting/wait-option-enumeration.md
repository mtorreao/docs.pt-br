---
title: Enumeração WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 056d41df328de5796eec9f04589205d18b408f1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732795"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="60d62-102">Enumeração WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="60d62-102">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="60d62-103">Contém valores que indicam a ação que um host deve executar se uma operação solicitada pelos blocos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="60d62-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d62-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="60d62-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="60d62-105">Membros</span><span class="sxs-lookup"><span data-stu-id="60d62-105">Members</span></span>  
  
|<span data-ttu-id="60d62-106">Membro</span><span class="sxs-lookup"><span data-stu-id="60d62-106">Member</span></span>|<span data-ttu-id="60d62-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="60d62-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="60d62-108">Notifica o host de que a tarefa deve ser despertada se o CLR chama o método [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="60d62-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="60d62-109">Notifica o host de que ele deve bombear mensagens no thread do sistema operacional atual se o thread for bloqueado.</span><span class="sxs-lookup"><span data-stu-id="60d62-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="60d62-110">O tempo de execução especifica esse valor somente em um <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="60d62-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="60d62-111">Notifica o host que a solicitação de sincronização especificada não pode ser quebrada por um host.</span><span class="sxs-lookup"><span data-stu-id="60d62-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="60d62-112">Ou seja, o host não pode retornar `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="60d62-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60d62-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="60d62-113">Remarks</span></span>  

 <span data-ttu-id="60d62-114">Os métodos [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) e [IHostTaskManager:: SwitchToTask](ihosttaskmanager-switchtotask-method.md) usam um parâmetro desse tipo.</span><span class="sxs-lookup"><span data-stu-id="60d62-114">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d62-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60d62-115">Requirements</span></span>  

 <span data-ttu-id="60d62-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60d62-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d62-117">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60d62-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60d62-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60d62-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60d62-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d62-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d62-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="60d62-120">See also</span></span>

- [<span data-ttu-id="60d62-121">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="60d62-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
