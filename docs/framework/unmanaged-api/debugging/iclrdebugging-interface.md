---
title: Interface ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 6eea7f6c222b8e30376ec72ee0c193a68c23f0d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723552"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="8db48-102">Interface ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="8db48-102">ICLRDebugging Interface</span></span>

<span data-ttu-id="8db48-103">Fornece métodos que manipulam os módulos de carregamento e descarregamento para depuração.</span><span class="sxs-lookup"><span data-stu-id="8db48-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8db48-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8db48-104">Methods</span></span>  
  
|<span data-ttu-id="8db48-105">Método</span><span class="sxs-lookup"><span data-stu-id="8db48-105">Method</span></span>|<span data-ttu-id="8db48-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8db48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8db48-107">Método OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="8db48-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="8db48-108">Obtém a interface "ICorDebugProcess" que corresponde a um módulo Common Language Runtime (CLR) carregado no processo.</span><span class="sxs-lookup"><span data-stu-id="8db48-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="8db48-109">Método CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="8db48-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="8db48-110">Determina se uma biblioteca fornecida por uma interface [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) ainda está em uso ou pode ser descarregada.</span><span class="sxs-lookup"><span data-stu-id="8db48-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8db48-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="8db48-111">Remarks</span></span>  

 <span data-ttu-id="8db48-112">Você pode obter uma instância da `ICLRDebugging` interface usando a função [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="8db48-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8db48-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8db48-113">Requirements</span></span>  

 <span data-ttu-id="8db48-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8db48-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8db48-115">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8db48-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8db48-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8db48-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8db48-117">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8db48-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db48-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="8db48-118">See also</span></span>

- [<span data-ttu-id="8db48-119">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="8db48-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8db48-120">Depuração</span><span class="sxs-lookup"><span data-stu-id="8db48-120">Debugging</span></span>](index.md)
