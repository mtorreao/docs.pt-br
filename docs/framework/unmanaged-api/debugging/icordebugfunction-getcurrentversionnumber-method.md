---
title: Método ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: 14579d4c84be9bb225e618715b3a7d45ccaac0a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728141"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>Método ICorDebugFunction::GetCurrentVersionNumber

Obtém o número de versão da edição mais recente feita à função representada por esse objeto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pnCurrentVersion`  
 fora Um ponteiro para um valor inteiro que é o número de versão da edição mais recente feita nessa função.  
  
## <a name="remarks"></a>Comentários  

 O número de versão da edição mais recente feita a essa função pode ser maior que o número de versão da própria função. Use o método [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) ou o método [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) para recuperar o número de versão da função.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
