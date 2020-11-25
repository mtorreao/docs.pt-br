---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713841"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a>Método ICorDebugDataTarget2::EnumerateThreadIDs

Retorna uma lista de IDs de thread ativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 cThreadIDs  
 [in] O número máximo de threads cujos IDs podem ser retornados.  
  
 pcThreadIds  
 [out] Um ponteiro para um `ULONG32` que indica o número real de IDs de thread gravadas na matriz `pThreadIds`.  
  
 pThreadIDs  
 Uma matriz de identificadores de thread.  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Consulte [requisitos do sistema](../../get-started/system-requirements.md). **Cabeçalho:** CorDebug. idl, CorDebug. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
