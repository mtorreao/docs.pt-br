---
title: Método ICorDebugThread::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 7d3575909f54c8d676c9fd4246e6eac4a8a0ea1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727972"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="32e68-102">Método ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="32e68-102">ICorDebugThread::GetRegisterSet Method</span></span>

<span data-ttu-id="32e68-103">Obtém um ponteiro de interface para o conjunto de registros que está associado à parte ativa deste objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="32e68-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e68-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="32e68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e68-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="32e68-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="32e68-106">fora Um ponteiro para o endereço de um objeto de interface [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa o conjunto de registros para a parte ativa desse thread.</span><span class="sxs-lookup"><span data-stu-id="32e68-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e68-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32e68-107">Requirements</span></span>  

 <span data-ttu-id="32e68-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e68-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e68-109">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32e68-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32e68-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e68-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32e68-111">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e68-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
