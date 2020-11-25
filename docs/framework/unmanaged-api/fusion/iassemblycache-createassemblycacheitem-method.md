---
title: Método IAssemblyCache::CreateAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
ms.openlocfilehash: b417377ea1d0746e563490d87cc9a988e857d943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697032"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>Método IAssemblyCache::CreateAssemblyCacheItem

Obtém uma referência a um novo objeto [IAssemblyCacheItem](iassemblycacheitem-interface.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `dwFlags`  
 no Sinalizadores definidos em Fusion. idl. Os seguintes valores têm suporte:  
  
- IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
- IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)  
  
 `pvReserved`  
 no Reservado para extensibilidade futura. `pvReserved` deve ser uma referência nula.  
  
 `ppAsmItem`  
 fora O `IAssemblyCacheItem` ponteiro retornado.  
  
 `pszAssemblyName`  
 [in, opcional] Pares não canônicos e separados por vírgulas `name=value` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IAssemblyCache](iassemblycache-interface.md)
- [Interface IAssemblyCacheItem](iassemblycacheitem-interface.md)
