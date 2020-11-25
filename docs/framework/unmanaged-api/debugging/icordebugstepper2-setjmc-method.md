---
title: Método ICorDebugStepper2::SetJMC
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 1bbcbcfbb78d421f247a13f58070b68f701e4ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697201"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="6ea47-102">Método ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="6ea47-102">ICorDebugStepper2::SetJMC Method</span></span>

<span data-ttu-id="6ea47-103">Define um valor que especifica se este ICorDebugStepper etapas somente por meio de código que é criado pelo desenvolvedor de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6ea47-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="6ea47-104">Esse processo também é conhecido como depuração de apenas meu código (JMC).</span><span class="sxs-lookup"><span data-stu-id="6ea47-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea47-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6ea47-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea47-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6ea47-106">Parameters</span></span>  

 `fIsJMCStepper`  
 <span data-ttu-id="6ea47-107">no Defina como `true` Step somente por meio de código que é criado pelo desenvolvedor de um aplicativo; caso contrário, defina como `false` .</span><span class="sxs-lookup"><span data-stu-id="6ea47-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea47-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ea47-108">Requirements</span></span>  

 <span data-ttu-id="6ea47-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea47-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea47-110">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ea47-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ea47-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea47-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea47-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea47-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
