---
title: Método ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: 54ecce830b928ded115233eb99932cc15a471033
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703129"
---
# <a name="icordebugilframegetlocalvariable-method"></a>Método ICorDebugILFrame::GetLocalVariable

Obtém o valor da variável local especificada neste quadro de ativação da MSIL (Microsoft Intermediate Language).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `dwIndex`  
 no O índice da variável local neste quadro da pilha MSIL.  
  
 `ppValue`  
 [out] Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor recuperado.  
  
## <a name="remarks"></a>Comentários  

 O `GetLocalVariable` método pode ser usado em um quadro de pilha MSIL ou em um quadro compilado JIT (just-in-time).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
