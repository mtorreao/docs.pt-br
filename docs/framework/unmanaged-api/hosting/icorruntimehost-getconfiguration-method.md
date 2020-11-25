---
title: Método ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720640"
---
# <a name="icorruntimehostgetconfiguration-method"></a>Método ICorRuntimeHost::GetConfiguration

Obtém um objeto que permite ao host especificar a configuração de retorno de chamada do Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pConfiguration`  
 fora Um ponteiro para o endereço de um objeto [ICorConfiguration](icorconfiguration-interface.md) que pode ser usado para configurar o CLR.  
  
## <a name="remarks"></a>Comentários  

 O CLR deve ser configurado antes de sua inicialização; caso contrário, o `GetConfiguration` método retornará um HRESULT indicando um erro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **Versões do .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Confira também

- [Interface ICorRuntimeHost](icorruntimehost-interface.md)
