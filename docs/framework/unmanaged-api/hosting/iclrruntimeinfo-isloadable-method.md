---
title: Método ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: 2236e815211168d8e7105375b75f30128f7f209a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714959"
---
# <a name="iclrruntimeinfoisloadable-method"></a>Método ICLRRuntimeInfo::IsLoadable

Indica se o tempo de execução associado a essa interface pode ser carregado no processo atual, levando em conta outros tempos de execução que já podem estar carregados no processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pbLoadable`  
 [fora] `true` Se esse tempo de execução puder ser carregado no processo atual; caso contrário, `false` .  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|E_POINTER|`pbLoadable` é nulo.|  
  
## <a name="remarks"></a>Comentários  

 Se outro tempo de execução já estiver carregado no processo e o tempo de execução associado a essa interface puder ser carregado para execução lado a lado no processo, `pbLoadable` retorna `true` . Se os dois tempos de execução não puderem ser executados lado a lado no processo, o `pbLoadable` retornará `false` . Por exemplo, o Common Language Runtime (CLR) versão 4 pode ser executado lado a lado no mesmo processo com o CLR versão 2,0 ou CLR versão 1,1. No entanto, o CLR versão 1,1 e a versão 2,0 do CLR não podem ser executados lado a lado no processo.  
  
 Se nenhum tempo de execução for carregado no processo, esse método sempre retornará `true` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
- [Hosting](index.md)
