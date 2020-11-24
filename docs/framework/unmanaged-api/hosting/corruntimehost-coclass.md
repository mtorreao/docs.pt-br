---
title: Coclass CorRuntimeHost
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd4e675b4ba50b47146428d204c28cc943c23c69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687997"
---
# <a name="corruntimehost-coclass"></a>Coclass CorRuntimeHost

Fornece interfaces para gerenciar aplicativos que estão sendo executados pelo Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interface|Descrição|  
|---------------|-----------------|  
|[Interface ICorConfiguration](icorconfiguration-interface.md)|Fornece métodos para configurar o Common Language Runtime (CLR).|  
|[Interface ICorRuntimeHost](icorruntimehost-interface.md)|Fornece métodos que permitem que o host inicie e pare o Common Language Runtime explicitamente, para criar e configurar domínios de aplicativo, acessar o domínio padrão e enumerar todos os domínios em execução no processo.|  
|[Interface IDebuggerInfo](idebuggerinfo-interface.md)|Fornece métodos para obter informações sobre o estado dos serviços de depuração.|  
|[Interface IGCHost](igchost-interface.md)|Fornece métodos para obter informações sobre o sistema de coleta de lixo e para controlar alguns aspectos da coleta de lixo.|  
|IValidator|Fornece métodos para validação de imagens executáveis portáteis e relatórios detalhados de erros de validação.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. idl  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Hospedando coclasses](hosting-coclasses.md)
