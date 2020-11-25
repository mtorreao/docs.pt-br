---
title: Método ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: dd1608badf553650b05b7de98d9bbcd76b2f3edf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728427"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>Método ICorDebugClass::GetStaticFieldValue

Obtém o valor do campo estático especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `fieldDef`  
 no Um token de campo `Def` que faz referência ao campo a ser recuperado.  
  
 `pFrame`  
 no Um ponteiro para um objeto ICorDebugFrame que representa o quadro a ser usado para ambiguidade entre os estáticos de thread, contexto ou domínio de aplicativo.  
  
 Se o campo estático for relativo a um thread, um contexto ou um domínio de aplicativo, o quadro determinará o valor adequado.  
  
 `ppValue`  
 fora Um ponteiro para o endereço de um objeto ICorDebugValue que representa o valor do campo estático.  
  
## <a name="remarks"></a>Comentários  

 Para tipos com parâmetros, o valor de um campo estático é relativo à instanciação específica. Portanto, se o construtor de classe usar parâmetros do tipo <xref:System.Type> , chame [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) em vez de `ICorDebugClass::GetStaticFieldValue` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
