---
title: Interface ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677831"
---
# <a name="iclrerrorreportingmanager-interface"></a>Interface ICLRErrorReportingManager

Fornece métodos que permitem ao host configurar despejos de pilha personalizados para o relatório de erros.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)|Especifica a configuração de despejos de pilha personalizados para o relatório de erros.|  
|[Método EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)|Limpa a configuração de despejo de pilha personalizado que foi definida por uma chamada anterior para `BeginCustomDump` .|  
|[Método GetBucketParametersForCurrentException](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Obtém o Bucket do Watson para a exceção atual no thread de chamada.|  
  
## <a name="remarks"></a>Comentários  

 O `BeginCustomDump` método define a configuração de despejo de pilha personalizado. O `EndCustomDump` método limpa a configuração de despejo de pilha personalizada e libera qualquer estado associado. Ele deve ser chamado após a conclusão do despejo personalizado.  
  
> [!IMPORTANT]
> Falha ao chamar `EndCustomDump` faz com que a memória seja vazada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Enumeração ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
