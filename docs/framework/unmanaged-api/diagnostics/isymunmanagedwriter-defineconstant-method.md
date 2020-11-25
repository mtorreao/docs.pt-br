---
title: Método ISymUnmanagedWriter::DefineConstant
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 7c4589c3371d2c66279684a365cde102bef58c6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727582"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a>Método ISymUnmanagedWriter::DefineConstant

Define um nome para um valor constante.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `name`  
 no Um ponteiro para um `WCHAR` que define o nome da constante.  
  
 `value`  
 no O valor da constante.  
  
 `cSig`  
 no O tamanho da `signature` matriz.  
  
 `signature`  
 no A assinatura de tipo para a constante.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Método DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)
