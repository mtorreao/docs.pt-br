---
title: Interface ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678227"
---
# <a name="iclrgcmanager-interface"></a>Interface ICLRGCManager

Fornece métodos que permitem que um host interaja com o sistema de coleta de lixo do Common Language Runtime.  
  
> [!NOTE]
> Começando com o .NET Framework 4,5, você pode usar o método [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) para definir o tamanho de um segmento de coleta de lixo e o tamanho máximo da geração 0 do sistema de coleta de lixo para valores maiores que o `DWORD` limite imposto pelo método [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método Collect](iclrgcmanager-collect-method.md)|Força uma coleta de lixo para a geração especificada.|  
|[Método GetStats](iclrgcmanager-getstats-method.md)|Obtém um conjunto de estatísticas atuais sobre o sistema de coleta de lixo.|  
|[Método SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md)|Define o tamanho de um segmento de coleta de lixo e o tamanho máximo da geração 0 do sistema de coleta de lixo.|  
  
## <a name="remarks"></a>Comentários  

 O Common Language Runtime (CLR) implementa seu mecanismo de coleta de lixo com o <xref:System.GC> tipo gerenciado. Para obter mais informações sobre o sistema de coleta de lixo, consulte [coleta de lixo](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Gerenciamento automático de memória](../../../standard/automatic-memory-management.md)
- [Estrutura COR_GC_STATS](cor-gc-stats-structure.md)
- [Interface ICLRControl](iclrcontrol-interface.md)
- [Interfaces de hospedagem CLR](clr-hosting-interfaces.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
- [Hosting](index.md)
