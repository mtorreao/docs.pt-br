---
title: Método ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: d17179dbeb9564b16c0c95a43502a53a67d3b9b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703155"
---
# <a name="icordebugilframegetargument-method"></a>Método ICorDebugILFrame::GetArgument

Obtém o valor do argumento especificado neste quadro de ativação da MSIL (Microsoft Intermediate Language).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `dwIndex`  
 no O índice do argumento neste quadro de pilha MSIL.  
  
 `ppValue`  
 [out] Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor recuperado.  
  
## <a name="remarks"></a>Comentários  

 O `GetArgument` método pode ser usado em um quadro de pilha MSIL ou em um quadro compilado JIT (just-in-time).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
