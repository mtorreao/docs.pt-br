---
title: Método ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: bd89db3fa0b1814a98b016fcf9d1aeeabfff718b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715843"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="38dc9-102">Método ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="38dc9-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>

<span data-ttu-id="38dc9-103">Indica aos serviços de depuração que um thread específico deve ter permissão para continuar a execução enquanto o depurador tem um aplicativo interrompido durante cenários de depuração gerenciados ou não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="38dc9-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38dc9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38dc9-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38dc9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="38dc9-105">Parameters</span></span>  

 `dwSpecialThreadId`  
 <span data-ttu-id="38dc9-106">no A ID do thread que deve ter permissão para continuar a execução.</span><span class="sxs-lookup"><span data-stu-id="38dc9-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38dc9-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="38dc9-107">Remarks</span></span>  

 <span data-ttu-id="38dc9-108">O thread especificado não terá permissão para executar código gerenciado ou inserir o tempo de execução de qualquer forma.</span><span class="sxs-lookup"><span data-stu-id="38dc9-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="38dc9-109">Um exemplo desse thread seria um thread em processo para dar suporte a depuradores de script herdados.</span><span class="sxs-lookup"><span data-stu-id="38dc9-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38dc9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38dc9-110">Requirements</span></span>  

 <span data-ttu-id="38dc9-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38dc9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38dc9-112">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="38dc9-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38dc9-113">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38dc9-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38dc9-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38dc9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38dc9-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="38dc9-115">See also</span></span>

- [<span data-ttu-id="38dc9-116">Interface ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="38dc9-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
