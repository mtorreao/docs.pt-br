---
title: Método ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717819"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="3474e-102">Método ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="3474e-102">ICorDebugClass2::SetJMCStatus Method</span></span>

<span data-ttu-id="3474e-103">Para cada método da classe, define um valor que indica se o método é um código definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3474e-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3474e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3474e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3474e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3474e-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="3474e-106">no Defina como `true` para indicar que o método é um código definido pelo usuário; caso contrário, defina como `false` .</span><span class="sxs-lookup"><span data-stu-id="3474e-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3474e-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="3474e-107">Remarks</span></span>  

 <span data-ttu-id="3474e-108">Um stepper JMC (Just-the-code) ignorará o código não definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3474e-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="3474e-109">O código definido pelo usuário deve ser um subconjunto de código depurável.</span><span class="sxs-lookup"><span data-stu-id="3474e-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="3474e-110">`SetJMCStatus` Retorna um valor HRESULT de S_FALSE se ele falhar ao definir o valor de qualquer método, mesmo se ele definir com êxito o valor para todos os outros métodos.</span><span class="sxs-lookup"><span data-stu-id="3474e-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3474e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3474e-111">Requirements</span></span>  

 <span data-ttu-id="3474e-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3474e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3474e-113">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3474e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3474e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3474e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3474e-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3474e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
