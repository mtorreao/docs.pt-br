---
title: Interface ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707601"
---
# <a name="iclrmetahostpolicy-interface"></a>Interface ICLRMetaHostPolicy

Fornece o método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , que retorna um ponteiro para uma interface Common Language Runtime (CLR) com base em critérios de política, assembly gerenciado, versão e arquivo de configuração.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)|Fornece uma interface CLR preferida com base em critérios de política, assembly gerenciado, versão e arquivo de configuração.|  
  
## <a name="remarks"></a>Comentários  

 Você pode obter uma referência a essa interface chamando a função [CLRCreateInstance](clrcreateinstance-function.md) , conforme mostrado no código a seguir:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Essa interface, na verdade, não carrega nem ativa o CLR, mas simplesmente retorna a versão do CLR preferida com base nas versões disponíveis que estão instaladas ou carregadas.  
  
 A API de hospedagem do .NET Framework 4 consolida políticas para que os hosts com necessidades específicas possam usar a funcionalidade básica sem incorrer em penalidades involuntárias. Por exemplo, muitas das MSCorEE.dll exportações serão vinculadas a um CLR específico, embora um método possa não exigi-la logicamente. A enumeração de [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) fornece políticas de associação que são comuns à maioria dos hosts.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de hospedagem CLR adicionadas no .NET Framework 4 e 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
- [Hosting](index.md)
