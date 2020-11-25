---
title: Método ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 55acb6e3ec60925cba3d8aa5328547c54f270356
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732665"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="92ad9-102">Método ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="92ad9-102">ICorDebugController::Detach Method</span></span>

<span data-ttu-id="92ad9-103">Desanexa o depurador do domínio do processo ou do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="92ad9-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ad9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92ad9-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="92ad9-105">Comentários</span><span class="sxs-lookup"><span data-stu-id="92ad9-105">Remarks</span></span>  

 <span data-ttu-id="92ad9-106">O processo ou o domínio do aplicativo continua a execução normalmente, mas o objeto "ICorDebugProcess" ou "ICorDebugAppDomain" não é mais válido e não ocorrerão nenhum retorno de chamada adicional.</span><span class="sxs-lookup"><span data-stu-id="92ad9-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="92ad9-107">No .NET Framework versão 2,0, se a depuração não gerenciada estiver habilitada, esse método falhará devido a limitações do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="92ad9-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ad9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92ad9-108">Requirements</span></span>  

 <span data-ttu-id="92ad9-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ad9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ad9-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ad9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ad9-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ad9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ad9-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ad9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ad9-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="92ad9-113">See also</span></span>
