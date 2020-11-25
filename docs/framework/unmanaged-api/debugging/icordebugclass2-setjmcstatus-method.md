---
title: Método ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717819"
---
# <a name="icordebugclass2setjmcstatus-method"></a>Método ICorDebugClass2::SetJMCStatus

Para cada método da classe, define um valor que indica se o método é um código definido pelo usuário.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `bIsJustMyCode`  
 no Defina como `true` para indicar que o método é um código definido pelo usuário; caso contrário, defina como `false` .  
  
## <a name="remarks"></a>Comentários  

 Um stepper JMC (Just-the-code) ignorará o código não definido pelo usuário. O código definido pelo usuário deve ser um subconjunto de código depurável.  
  
 `SetJMCStatus` Retorna um valor HRESULT de S_FALSE se ele falhar ao definir o valor de qualquer método, mesmo se ele definir com êxito o valor para todos os outros métodos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
