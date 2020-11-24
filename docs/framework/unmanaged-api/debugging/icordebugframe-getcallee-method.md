---
title: Método ICorDebugFrame::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 6347e0109f256dc46eb0140ffd1f51977c205b51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678799"
---
# <a name="icordebugframegetcallee-method"></a>Método ICorDebugFrame::GetCallee

Obtém um ponteiro para o objeto ICorDebugFrame na cadeia atual que esse quadro chamou.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppFrame`  
 fora Um ponteiro para o endereço de um `ICorDebugFrame` objeto que representa o quadro chamado. Esse valor será nulo se o quadro de chamada for o quadro interno na cadeia atual.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
