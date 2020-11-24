---
title: Interface ISymUnmanagedReaderSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: af4124aed823a0a2475a181efe3fa68e1fae0bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678383"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a>Interface ISymUnmanagedReaderSymbolSearchInfo

Fornece métodos que recebem informações de pesquisa de símbolo. Obtenha essa interface chamando `QueryInterface` em um objeto que implementa a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|Obtém informações de pesquisa de símbolo.|  
|[Método GetSymbolSearchInfoCount](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|Obtém uma contagem de informações de pesquisa de símbolo.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
