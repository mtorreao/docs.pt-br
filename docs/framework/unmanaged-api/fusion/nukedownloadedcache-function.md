---
title: Função NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728570"
---
# <a name="nukedownloadedcache-function"></a>Função NukeDownloadedCache

Exclui o cache de download do Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Valor retornado  

 Esse método retorna códigos de erro COM padrão, conforme definido em WinError. h.  
  
## <a name="remarks"></a>Comentários  

 O cache de download do CLR é a área em que os assemblies de nome forte baixados de uma URL são armazenados para possível reutilização.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **Biblioteca:** Fusion.dll e Mscorwks.dll. Use Fusion.dll em vez de Mscorwks.dll para garantir que você direcione a versão correta do .NET Framework.  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Função CreateHistoryReader](createhistoryreader-function.md)
- [Função GetHistoryFileDirectory](gethistoryfiledirectory-function.md)
- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
