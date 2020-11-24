---
title: Interface IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680964"
---
# <a name="ihostassemblymanager-interface"></a>Interface IHostAssemblyManager

Fornece métodos que permitem que um host especifique conjuntos de assemblies que devem ser carregados pelo Common Language Runtime (CLR) ou pelo host.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetAssemblyStore](ihostassemblymanager-getassemblystore-method.md)|Obtém um ponteiro de interface para um [IHostAssemblyStore](ihostassemblystore-interface.md) que representa a lista de assemblies carregados pelo host.|  
|[Método GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Obtém um ponteiro de interface para um [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa a lista de assemblies que o host espera que o CLR carregue.|  
  
## <a name="remarks"></a>Comentários  

 Não é necessário que o host implemente `IHostAssemblyManager` ou `IHostAssemblyStore` . Se o host implementar `IHostAssemblyManager` , ele também deverá implementar `IHostAssemblyStore` .  
  
 As consultas de tempo de execução para um `IHostAssemblyManager` chamando [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) na inicialização com um `IID` de IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interface IHostAssemblyStore](ihostassemblystore-interface.md)
- [Interface IHostControl](ihostcontrol-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
