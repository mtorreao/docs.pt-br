---
title: Método ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
ms.openlocfilehash: 8de0858abe7db9ae1225f449083e417e13507b3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703028"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a>Método ICorDebugManagedCallback::StepComplete

Notifica o depurador de que uma etapa foi concluída.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pAppDomain`  
 no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo que contém o thread no qual a etapa foi concluída.  
  
 `pThread`  
 no Um ponteiro para um objeto ICorDebugThread que representa o thread no qual a etapa foi concluída.  
  
 `pStepper`  
 no Um ponteiro para um objeto ICorDebugStepper que representa a etapa na execução de código.  
  
 `reason`  
 no Um valor da enumeração CorDebugStepReason que indica o resultado de uma etapa individual.  
  
## <a name="remarks"></a>Comentários  

 O stepper pode ser usado para continuar a depuração, se desejado, a menos que a depuração seja encerrada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
