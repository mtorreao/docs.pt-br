---
title: Método ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730494"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Método ICLRHostProtectionManager::SetProtectedCategories

Especifica quais categorias de tipos gerenciados e membros devem ser impedidos de serem executados em código parcialmente confiável.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `categories`  
 no Uma combinação de valores [EApiCategories](eapicategories-enumeration.md) , indicando quais categorias de tipos gerenciados e membros devem ser impedidos de serem executados em código parcialmente confiável.  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` retornado com êxito.|  
|HOST_E_CLRNOTAVAILABLE|O Common Language Runtime (CLR) não foi carregado em um processo ou o CLR está em um estado no qual não pode executar código gerenciado ou processar a chamada com êxito.|  
|HOST_E_TIMEOUT|A chamada atingiu o tempo limite.|  
|HOST_E_NOT_OWNER|O chamador não possui o bloqueio.|  
|HOST_E_ABANDONED|Um evento foi cancelado enquanto um thread ou uma fibra bloqueada estava esperando.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Depois que um método retorna E_FAIL, o CLR não pode mais ser usado no processo. As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentários  

 Cada `EApiCategories` valor se refere a uma lista de tipos e membros gerenciados. A `EApiCategories` enumeração e o `SetProtectedCategories` método estão diretamente relacionados à classe gerenciada <xref:System.Security.Permissions.HostProtectionAttribute> , que é usada para marcar tipos gerenciados e membros que expõem recursos correspondentes às categorias descritas por `EApiCategories` . Para obter mais informações, consulte <xref:System.Security.Permissions.HostProtectionAttribute> e a <xref:System.Security.Permissions.HostProtectionResource> enumeração, que corresponde diretamente a `EApiCategories` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [Enumeração EApiCategories](eapicategories-enumeration.md)
- [Interface ICLRControl](iclrcontrol-interface.md)
- [Interface ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
