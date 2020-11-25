---
title: Método IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 4638672b1d64a9ea07618212cc514d00996470eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721665"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="f096a-102">Método IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="f096a-102">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="f096a-103">Notifica o host de que o tempo de execução está retomando threads após uma coleta de lixo ou outra suspensão.</span><span class="sxs-lookup"><span data-stu-id="f096a-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f096a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f096a-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f096a-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f096a-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="f096a-106">no A geração na qual uma coleta de lixo foi executada.</span><span class="sxs-lookup"><span data-stu-id="f096a-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f096a-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="f096a-107">Remarks</span></span>  

 <span data-ttu-id="f096a-108">Não reagende nenhum thread durante o `SuspensionEnding` retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="f096a-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f096a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f096a-109">Requirements</span></span>  

 <span data-ttu-id="f096a-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f096a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f096a-111">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f096a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f096a-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f096a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f096a-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f096a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f096a-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="f096a-114">See also</span></span>

- [<span data-ttu-id="f096a-115">Interface IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="f096a-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
