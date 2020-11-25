---
title: Interface ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: acb8d48ed6314756e2c1a10fff314a303799fb24
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707276"
---
# <a name="isymencunmanagedmethod-interface"></a>Interface ISymENCUnmanagedMethod

Fornece informações para o recurso Editar e continuar.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetDocumentsForMethod](isymencunmanagedmethod-getdocumentsformethod-method.md)|Obtém os documentos em que este método tem linhas.|  
|[Método GetDocumentsForMethodCount](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Obtém o número de documentos em que esse método tem linhas.|  
|[Método GetFileNameFromOffset](isymencunmanagedmethod-getfilenamefromoffset-method.md)|Obtém o nome do arquivo da linha associada a um deslocamento.|  
|[Método GetLineFromOffset](isymencunmanagedmethod-getlinefromoffset-method.md)|Obtém as informações de linha associadas a um deslocamento.|  
|[Método GetSourceExtentInDocument](isymencunmanagedmethod-getsourceextentindocument-method.md)|Obtém a menor linha inicial e a linha final maior para o método em um documento específico.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
