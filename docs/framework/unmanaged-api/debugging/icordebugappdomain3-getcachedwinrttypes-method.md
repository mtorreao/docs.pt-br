---
title: Método ICorDebugAppDomain3::GetCachedWinRTTypes
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: 5e0df443e691292817ff37900fbc87204a8325ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684493"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>Método ICorDebugAppDomain3::GetCachedWinRTTypes

Obtém um enumerador para todos os tipos de Windows Runtime em cache.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppGuidToTypeEnum`  
 fora Um ponteiro para um objeto de interface [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) que pode enumerar as representações gerenciadas dos tipos de Windows Runtime atualmente carregados no domínio do aplicativo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Windows Runtime  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugAppDomain3](icordebugappdomain3-interface.md)
