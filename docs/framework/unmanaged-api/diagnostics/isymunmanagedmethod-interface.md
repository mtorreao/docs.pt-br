---
title: Interface ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: b72a77fecd15a43efbddd9dfd4618897c3372f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699268"
---
# <a name="isymunmanagedmethod-interface"></a>Interface ISymUnmanagedMethod

Representa um método dentro do repositório de símbolos. Essa interface fornece acesso apenas aos atributos relacionados a símbolos de um método, em vez dos atributos relacionados ao tipo.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetNamespace](isymunmanagedmethod-getnamespace-method.md)|Obtém o namespace no qual esse método é definido.|  
|[Método GetOffset](isymunmanagedmethod-getoffset-method.md)|Retorna o deslocamento dentro desse método que corresponde a uma determinada posição dentro de um documento.|  
|[Método GetParameters](isymunmanagedmethod-getparameters-method.md)|Obtém os parâmetros para este método.|  
|[Método GetRanges](isymunmanagedmethod-getranges-method.md)|Dada uma posição em um documento, retorna uma matriz de pares de deslocamento inicial e final que correspondem aos intervalos da MSIL (Microsoft Intermediate Language) que a posição aborda nesse método.|  
|[Método GetRootScope](isymunmanagedmethod-getrootscope-method.md)|Obtém o escopo léxico raiz dentro deste método. Esse escopo abrange todo o método.|  
|[Método GetScopeFromOffset](isymunmanagedmethod-getscopefromoffset-method.md)|Obtém o escopo léxico mais delimitador dentro desse método que envolve o deslocamento fornecido.|  
|[Método GetSequencePointCount](isymunmanagedmethod-getsequencepointcount-method.md)|Obtém a contagem de pontos de sequência dentro deste método.|  
|[Método GetSequencePoints](isymunmanagedmethod-getsequencepoints-method.md)|Obtém todos os pontos de sequência dentro deste método.|  
|[Método GetSourceStartEnd](isymunmanagedmethod-getsourcestartend-method.md)|Obtém as posições do documento inicial e final da origem deste método.|  
|[Método GetToken](isymunmanagedmethod-gettoken-method.md)|Retorna o token de metadados para esse método.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
