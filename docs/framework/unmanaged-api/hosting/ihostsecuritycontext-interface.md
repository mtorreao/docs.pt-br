---
title: Interface IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724800"
---
# <a name="ihostsecuritycontext-interface"></a>Interface IHostSecurityContext

Permite que o Common Language Runtime (CLR) Mantenha informações de contexto de segurança implementadas pelo host.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método Capture](ihostsecuritycontext-capture-method.md)|Obtém um clone da `IHostSecurityContext` instância retornada de uma chamada para [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Comentários  

 Um host pode controlar todo o acesso ao código para tokens de thread tanto pelo CLR quanto pelo código do usuário. Ele também pode garantir que as informações completas do contexto de segurança sejam passadas entre operações assíncronas ou pontos de código com acesso restrito ao código. `IHostSecurityContext` encapsula essas informações de contexto de segurança, que são opacas para o tempo de execução. O tempo de execução captura essas informações usando o `Capture` e move-as entre a expedição do item de trabalho do pool de threads, a execução do finalizador e os construtores de módulo e classe.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Interface IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
