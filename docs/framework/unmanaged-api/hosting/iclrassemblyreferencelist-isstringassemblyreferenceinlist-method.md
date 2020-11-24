---
title: Método ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
ms.openlocfilehash: 74d47b3f55c10f65d47f726a2b96ba5e0b18b749
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679137"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a>Método ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList

Obtém um valor que indica se o nome fornecido corresponde ao nome de um assembly na lista.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pwzAssemblyName`  
 no O nome do assembly para o qual Pesquisar.  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|A cadeia de caracteres aparece na lista.|  
|S_FALSE|A cadeia de caracteres não aparece na lista.|  
|E_FAIL|Ocorreu uma falha catastrófica desconhecida. Depois que um método retorna E_FAIL, o Common Language Runtime não pode mais ser usado no processo. As chamadas subsequentes para métodos de hospedagem retornam HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Interface ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interface IHostAssemblyManager](ihostassemblymanager-interface.md)
- [Interface IHostAssemblyStore](ihostassemblystore-interface.md)
