---
title: Método ICLRDebugManager::GetDacl
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: 8a7de5a900bc1af219924b6a83f83cf7e2ef6150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726139"
---
# <a name="iclrdebugmanagergetdacl-method"></a>Método ICLRDebugManager::GetDacl

Este método não está implementado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppacl`  
 fora Um ponteiro de interface para a lista de controle de acesso (ACL).  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|DESCRIÇÃO|  
|-------------|-----------------|  
|E_NOTIMPL|O método não está implementado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRControl](iclrcontrol-interface.md)
- [Interface ICLRDebugManager](iclrdebugmanager-interface.md)
- [Método SetDacl](iclrdebugmanager-setdacl-method.md)
- [Interface IHostControl](ihostcontrol-interface.md)
