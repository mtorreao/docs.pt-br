---
title: Interface ISymUnmanagedReader2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709070"
---
# <a name="isymunmanagedreader2-interface"></a>Interface ISymUnmanagedReader2

Representa um leitor de símbolo que fornece acesso a documentos, métodos e variáveis em um repositório de símbolos. Essa interface estende a interface [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetMethodByVersionPreRemap](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Obtenha um método de leitor de símbolo, dado um token de método e um número de versão de edição e continuação.|  
|[Método GetMethodsInDocument](isymunmanagedreader2-getmethodsindocument-method.md)|Obtém todos os métodos que têm informações de linha no documento fornecido.|  
|[Método GetSymAttributePreRemap](isymunmanagedreader2-getsymattributepreremap-method.md)|Obtém um atributo personalizado com base no seu nome.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
- [Interface ISymUnmanagedReader](isymunmanagedreader-interface.md)
