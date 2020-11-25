---
title: Interface ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725879"
---
# <a name="isymunmanagedscope-interface"></a>Interface ISymUnmanagedScope

Representa um escopo léxico dentro de um método.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetChildren](isymunmanagedscope-getchildren-method.md)|Obtém os filhos deste escopo.|  
|[Método GetEndOffset](isymunmanagedscope-getendoffset-method.md)|Obtém o deslocamento de fim deste escopo.|  
|[Método GetLocalCount](isymunmanagedscope-getlocalcount-method.md)|Obtém uma contagem das variáveis locais definidas neste escopo.|  
|[Método GetLocals](isymunmanagedscope-getlocals-method.md)|Obtém as variáveis locais definidas nesse escopo.|  
|[Método GetMethod](isymunmanagedscope-getmethod-method.md)|Obtém o método que contém esse escopo.|  
|[Método GetNamespaces](isymunmanagedscope-getnamespaces-method.md)|Obtém os namespaces que estão sendo usados nesse escopo.|  
|[Método GetParent](isymunmanagedscope-getparent-method.md)|Obtém o escopo pai deste escopo.|  
|[Método GetStartOffset](isymunmanagedscope-getstartoffset-method.md)|Obtém o deslocamento inicial para este escopo.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
- [Interface ISymUnmanagedScope2](isymunmanagedscope2-interface.md)
