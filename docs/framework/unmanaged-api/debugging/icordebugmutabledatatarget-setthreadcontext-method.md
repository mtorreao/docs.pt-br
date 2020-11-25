---
title: 'Método ICorDebugMutableDataTarget:: SetThreadContext'
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 558a1ee2eb0ac06213c2ebcebbd5595b69ecc43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695704"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>Método ICorDebugMutableDataTarget:: SetThreadContext

Define o contexto (valores de registro) para um thread.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `dwThreadID`  
 no O identificador de thread definido pelo sistema operacional.  
  
 `contextSize`  
 no O tamanho do `pContext` buffer a ser gravado.  
  
 `pContext`  
 no Um ponteiro para os bytes a serem gravados.  
  
## <a name="remarks"></a>Comentários  

 O `SetThreadContext` método atualiza o contexto atual para o thread especificado pelo argumento definido pelo sistema operacional `dwThreadID` . O formato do registro de contexto é determinado pela plataforma indicada pelo método [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) . No Windows, essa é uma estrutura de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
