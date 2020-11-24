---
title: Método ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 92b2a7f7f1dd98f0d847119a6431e3816c16d5da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679566"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>Método ICorDebugManagedCallback::LogMessage

Notifica o depurador de que um thread gerenciado Common Language Runtime (CLR) chamou um método na <xref:System.Diagnostics.EventLog> classe para registrar um evento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pAppDomain`  
 no Um ponteiro para um objeto ICorDebugAppDomain que representa o domínio do aplicativo que contém o thread gerenciado que registrou o evento.  
  
 `pThread`  
 no Um ponteiro para um objeto ICorDebugThread que representa o thread gerenciado.  
  
 `lLevel`  
 no Um valor da enumeração [LoggingLevelEnum](logginglevelenum-enumeration.md) que indica o nível de severidade da mensagem descritiva que foi gravada no log de eventos.  
  
 `pLogSwitchName`  
 no Um ponteiro para o nome da opção de rastreamento.  
  
 `pMessage`  
 no Um ponteiro para a mensagem que foi gravada no log de eventos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
