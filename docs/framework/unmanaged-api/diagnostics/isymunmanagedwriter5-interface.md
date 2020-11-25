---
title: Interface ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 894f3b0e45df2c681cbdec1f154703be64f32fc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725788"
---
# <a name="isymunmanagedwriter5-interface"></a>Interface ISymUnmanagedWriter5

Interface ISymUnmanagedWriter5.  
  
## <a name="syntax"></a>Sintaxe  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Métodos  

 Essa interface contém os seguintes métodos:  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Feche a seção de dados personalizados especiais para obter informações de mapeamento de token para origem. Depois de fechada, não é possível adicionar mais informações de mapeamento.|  
|[Método MapTokenToSourceSpan](isymunmanagedwriter5-maptokentosourcespan-method.md)|Mapeia o token de metadados fornecido para o span de linha de origem fornecido no arquivo de origem especificado.<br /><br /> Deve ser chamado entre as chamadas para o [método OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e o [método CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).|  
|[Método OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Abra uma seção especial de dados personalizados para emitir informações de mapeamento de extensão de token para origem no. Abrir esta seção quando um método já estiver aberto, ou vice-versa, é um erro.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interfaces de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-interfaces.md)
- [Interface ISymUnmanagedWriter4](isymunmanagedwriter4-interface.md)
