---
title: Interface ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714153"
---
# <a name="iclrhostprotectionmanager-interface"></a>Interface ICLRHostProtectionManager

Permite que o host bloqueie classes gerenciadas, métodos, propriedades e campos específicos da execução em código parcialmente confiável.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Fornece uma garantia de que certas condições raras de corrida que podem causar erros fatais de Common Language Runtime (CLR) nunca surgirão.|  
|[Método SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md)|Especifica as categorias de tipos gerenciados e membros que devem ser impedidos de serem executados em código parcialmente confiável.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Enumeração EApiCategories](eapicategories-enumeration.md)
- [Interface ICLRControl](iclrcontrol-interface.md)
