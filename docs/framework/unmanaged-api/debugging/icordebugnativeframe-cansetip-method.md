---
title: Método ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: 194065e53d550c9bbd0486de54462309a4d9ffa1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695732"
---
# <a name="icordebugnativeframecansetip-method"></a>Método ICorDebugNativeFrame::CanSetIP

Obtém um HRESULT que indica se é seguro definir o ponteiro de instrução (IP) para o local de deslocamento especificado no código nativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `nOffset`  
 no A configuração desejada para o ponteiro de instrução.  
  
## <a name="remarks"></a>Comentários  

 Use o `CanSetIP` método antes de chamar o método [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) . Se `CanSetIP` o retornar qualquer HRESULT diferente de S_OK, você ainda poderá invocar `ICorDebugNativeFrame::SetIP` , mas não há nenhuma garantia de que o depurador continuará a execução segura e correta do código que está sendo depurado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também
