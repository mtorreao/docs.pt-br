---
title: Método ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: aa45c814568188a5fe93e3acd2514cb54bb0f984
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688608"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>Método ICLRRuntimeInfo::LoadLibrary

Carrega uma biblioteca de .NET Framework do Common Language Runtime (CLR) representado por uma interface [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Esse método substitui a função [LoadLibraryShim](loadlibraryshim-function.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pwzDllName`  
 no O nome do assembly a ser carregado.  
  
 `phndModule`  
 fora Um identificador para o assembly carregado.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|E_POINTER|`pwzDllName` ou `phndModule` é nulo.|  
|E_OUTOFMEMORY|Não há memória suficiente disponível para lidar com a solicitação.|  
  
## <a name="remarks"></a>Comentários  

 Esse método carrega somente DLLs incluídas no pacote redistribuível .NET Framework. Ele não pode carregar assemblies gerados pelo usuário.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
- [Hosting](index.md)
