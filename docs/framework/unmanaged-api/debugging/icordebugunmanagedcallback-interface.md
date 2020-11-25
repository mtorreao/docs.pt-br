---
title: Interface ICorDebugUnmanagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: 73722c9fbc1571496159c32b0106f25bc05dbe65
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703012"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="8d235-102">Interface ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="8d235-102">ICorDebugUnmanagedCallback Interface</span></span>

<span data-ttu-id="8d235-103">Fornece notificação de eventos nativos que não estão diretamente relacionados ao Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8d235-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d235-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d235-104">Methods</span></span>  
  
|<span data-ttu-id="8d235-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d235-105">Method</span></span>|<span data-ttu-id="8d235-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8d235-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d235-107">Método DebugEvent</span><span class="sxs-lookup"><span data-stu-id="8d235-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="8d235-108">Notifica o depurador de que um evento nativo foi acionado.</span><span class="sxs-lookup"><span data-stu-id="8d235-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d235-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="8d235-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d235-110">Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.</span><span class="sxs-lookup"><span data-stu-id="8d235-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d235-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d235-111">Requirements</span></span>  

 <span data-ttu-id="8d235-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d235-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d235-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d235-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d235-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d235-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d235-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d235-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d235-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d235-116">See also</span></span>

- [<span data-ttu-id="8d235-117">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="8d235-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
