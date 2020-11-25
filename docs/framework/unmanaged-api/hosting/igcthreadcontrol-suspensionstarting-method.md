---
title: Método IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 9d39ee79f7734f7dd099a07640ecb06f4f8dcbb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721654"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="22eac-102">Método IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="22eac-102">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="22eac-103">Notifica o host de que o tempo de execução está começando uma suspensão de thread para uma coleta de lixo ou outra suspensão.</span><span class="sxs-lookup"><span data-stu-id="22eac-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22eac-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22eac-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="22eac-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="22eac-105">Remarks</span></span>  

 <span data-ttu-id="22eac-106">Não reagende nenhum thread durante o `SuspensionStarting` retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="22eac-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22eac-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22eac-107">Requirements</span></span>  

 <span data-ttu-id="22eac-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22eac-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22eac-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="22eac-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22eac-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22eac-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22eac-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22eac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22eac-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="22eac-112">See also</span></span>

- [<span data-ttu-id="22eac-113">Interface IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="22eac-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
