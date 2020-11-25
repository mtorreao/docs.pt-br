---
title: Método IGCThreadControl::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: 39834ba868a21ead3113f2f0d9157cd210d9798c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721641"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="c7b75-102">Método IGCThreadControl::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="c7b75-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="c7b75-103">Notifica o host que o thread que está fazendo a chamada está prestes a bloquear, talvez para uma coleta de lixo ou outra suspensão.</span><span class="sxs-lookup"><span data-stu-id="c7b75-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7b75-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c7b75-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c7b75-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7b75-105">Remarks</span></span>  

 <span data-ttu-id="c7b75-106">O host pode escolher dentro do `ThreadIsBlockingForSuspension` retorno de chamada se você deseja reagendar um thread.</span><span class="sxs-lookup"><span data-stu-id="c7b75-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7b75-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7b75-107">Requirements</span></span>  

 <span data-ttu-id="c7b75-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7b75-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7b75-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c7b75-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7b75-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7b75-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7b75-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7b75-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b75-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="c7b75-112">See also</span></span>

- [<span data-ttu-id="c7b75-113">Interface IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="c7b75-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
