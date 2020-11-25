---
title: Interface ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 95ad3cbea4269173f22e662d15772ff97f7ee900
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705443"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a>Interface ISymUnmanagedSymbolSearchInfo

Fornece métodos que obtêm informações sobre o caminho de pesquisa. Obtenha essa interface chamando `QueryInterface` em um objeto que implementa a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método GetHRESULT](isymunmanagedsymbolsearchinfo-gethresult-method.md)|Obtém o HRESULT.|  
|[Método GetSearchPath](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|Obtém o caminho de pesquisa.|  
|[Método GetSearchPathLength](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|Obtém o comprimento do caminho de pesquisa.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
