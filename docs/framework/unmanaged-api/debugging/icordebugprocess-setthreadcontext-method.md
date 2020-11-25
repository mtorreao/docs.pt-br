---
title: Método ICorDebugProcess::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 5b4052485a6d420eb83578d135ce51f8a918aab0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724514"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>Método ICorDebugProcess::SetThreadContext

Define o contexto para o thread fornecido nesse processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `threadID`  
 no A ID do thread para o qual definir o contexto.  
  
 `contextSize`  
 no O tamanho da `context` matriz.  
  
 `context`  
 no Uma matriz de bytes que descreve o contexto do thread.  
  
 O contexto especifica a arquitetura do processador no qual o thread está sendo executado.  
  
## <a name="remarks"></a>Comentários  

 O depurador deve chamar esse método em vez da função do Win32 `SetThreadContext` , pois o thread pode realmente estar em um estado "seqüestrado", no qual seu contexto foi alterado temporariamente. Esse método deve ser usado somente quando um thread estiver em código nativo. Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para threads em código gerenciado. Nunca é necessário modificar o contexto de um thread durante um evento de depuração OOB (fora de banda).  
  
 Os dados passados devem ser uma estrutura de contexto para a plataforma atual.  
  
 Esse método pode corromper o tempo de execução se for usado de forma inadequada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
