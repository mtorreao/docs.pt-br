---
title: Método ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: a918b5c2334683348adc6a7382527faedb52d7b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683531"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>Método ISymUnmanagedWriter::SetMethodSourceRange

Especifica os verdadeiros início e término de um método de dentro de um arquivo de origem. Use esse método para especificar a extensão de um método independentemente dos pontos de sequência que existem dentro do método.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `startDoc`  
 no Um ponteiro para o documento que contém a posição inicial.  
  
 `startLine`  
 no O número da linha inicial.  
  
 `startColumn`  
 no A coluna inicial.  
  
 `endDoc`  
 no Um ponteiro para o documento que contém a posição final.  
  
 `endLine`  
 no O número da linha final.  
  
 `endColumn`  
 no O número da coluna final.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
