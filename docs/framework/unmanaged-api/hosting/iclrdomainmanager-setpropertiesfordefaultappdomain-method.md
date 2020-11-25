---
title: Método ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702128"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>Método ICLRDomainManager::SetPropertiesForDefaultAppDomain

Define as propriedades que serão usadas para inicializar o domínio de aplicativo padrão.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `nProperties`  
 no O número de entradas no `pwszPropertyNames` e no `pwszPropertyValues` .  
  
 `pwszPropertyNames`  
 no Uma matriz de nomes de propriedade ou NULL se não houver propriedades. Atualmente, o único nome de propriedade reconhecido por esse método é "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 no Uma matriz de valores de propriedade ou NULL se não houver nenhuma propriedade.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` inclui um nome de propriedade que não é reconhecido por este método.|  
  
## <a name="remarks"></a>Comentários  

 O valor da propriedade para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" é uma lista de ASSEMBLIES que têm o <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) com o <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> sinalizador, que deve se tornar visível para chamadores parcialmente confiáveis no domínio do aplicativo padrão.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Hosting](index.md)
- [Interface ICLRDomainManager](iclrdomainmanager-interface.md)
