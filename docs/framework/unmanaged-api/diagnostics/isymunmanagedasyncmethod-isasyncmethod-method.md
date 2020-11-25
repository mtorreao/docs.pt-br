---
title: Método ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707146"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>Método ISymUnmanagedAsyncMethod::IsAsyncMethod

Verifica se o método tem informações assíncronas ou não.  
  
 Se esse método retornar `FALSE` , ele será inválido para chamar outros métodos nesta interface. Eles serão retornados `E_UNEXPECTED` nesse caso.  
  
## <a name="syntax"></a>Sintaxe  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Valor Retornado  

 Retorna `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)
