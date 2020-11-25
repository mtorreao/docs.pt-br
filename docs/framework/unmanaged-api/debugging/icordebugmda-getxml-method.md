---
title: Método ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: 9a088c7e4e9c72c8247ccdd384bc724587210c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710864"
---
# <a name="icordebugmdagetxml-method"></a>Método ICorDebugMDA::GetXML

Obtém o fluxo XML completo associado ao MDA (Assistente de depuração gerenciada) representado por [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `cchName`  
 no O tamanho da `szName` matriz.  
  
 `pcchName`  
 fora Um ponteiro para o comprimento do fluxo XML.  
  
 `szName`  
 fora Uma matriz na qual armazenar o fluxo XML. A matriz pode estar vazia.  
  
## <a name="remarks"></a>Comentários  

 O `GetXML` método pode potencialmente afetar o desempenho, dependendo do tamanho do fluxo XML associado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugMDA](icordebugmda-interface.md)
- [Diagnosticando erros com assistentes de depuração gerenciados](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
