---
title: Método ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: eb8692aebe7b702b5778b3f13e496d81dcd45784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678529"
---
# <a name="icordebugthread4getblockingobjects-method"></a>Método ICorDebugThread4::GetBlockingObjects

Fornece uma enumeração ordenada de estruturas [CorDebugBlockingObject](cordebugblockingobject-structure.md) que fornecem informações de bloqueio de thread.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppBlockingObjectEnum`  
 fora Um ponteiro para uma enumeração ordenada de estruturas [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
## <a name="remarks"></a>Comentários  

 O primeiro elemento na enumeração retornada corresponde à primeira estrutura que está bloqueando o thread. O segundo elemento corresponde a um item de bloqueio que é encontrado durante a execução de uma APC (chamada de procedimento assíncrono) quando bloqueado no primeiro e assim por diante.  
  
 A enumeração é válida somente pela duração do estado atual sincronizado.  
  
 Esse método deve ser chamado enquanto o depurado estiver em um estado sincronizado.  
  
 Se `ppBlockingObjectEnum` não for um ponteiro válido, o resultado será indefinido.  
  
 Se um thread for bloqueado e o erro não puder ser determinado, o método retornará um HRESULT que indica falha; caso contrário, ele retornará S_OK.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugThread4](icordebugthread4-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
- [Depuração](index.md)
