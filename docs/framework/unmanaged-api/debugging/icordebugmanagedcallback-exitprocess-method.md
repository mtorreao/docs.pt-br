---
title: Método ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 67f3e63b58e08a4b9ccfbd555e6edcdef0d00d90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688922"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Método ICorDebugManagedCallback::ExitProcess

Notifica o depurador de que um processo foi encerrado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pProcess`  
 no Um ponteiro para um objeto ICorDebugProcess que representa o processo.  
  
## <a name="remarks"></a>Comentários  

 Você não pode continuar a partir de um `ExitProcess` evento. Esse evento pode ser acionado de forma assíncrona a outros eventos enquanto o processo parece estar parado. Isso pode ocorrer se o processo for encerrado enquanto é interrompido, geralmente devido a alguma força externa.  
  
 Se o Common Language Runtime (CLR) já estiver expedindo um retorno de chamada gerenciado, esse evento será atrasado até que o retorno de chamada seja retornado.  
  
 O `ExitProcess` evento é o único evento Exit/Unload que é garantido para ser chamado no desligamento.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
