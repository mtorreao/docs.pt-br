---
title: Método ICorDebugNativeFrame::GetLocalDoubleRegisterValue
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 10f06fb04099ef947711bc7c5641e5a7f1fa36b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695693"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a>Método ICorDebugNativeFrame::GetLocalDoubleRegisterValue

Obtém o valor de um argumento ou uma variável local que é armazenada nos dois registros especificados para esse quadro nativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `highWordReg`  
 no Um valor da enumeração "CorDebugRegister" que especifica o registro que contém a palavra alta do valor.  
  
 `lowWordReg`  
 no Um valor da `CorDebugRegister` enumeração que especifica o registro que contém a palavra inferior do valor.  
  
 `cbSigBlob`  
 no Um inteiro que especifica o tamanho da assinatura de metadados binários que é referenciada pelo `pvSigBlob` parâmetro.  
  
 `pvSigBlob`  
 no Um `PCCOR_SIGNATURE` valor que aponta para a assinatura de metadados binários do tipo do valor.  
  
 `ppValue`  
 fora Um ponteiro para o endereço de um objeto "ICorDebugValue" que representa o valor recuperado que é armazenado nos registros especificados.  
  
## <a name="remarks"></a>Comentários  

 O `GetLocalDoubleRegisterValue` método pode ser usado em um quadro nativo ou em um quadro compilado JIT (just-in-time).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também
