---
title: Enumeração COINITICOR
ms.date: 03/30/2017
api_name:
- COINITICOR
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITICOR
helpviewer_keywords:
- COINITICOR enumeration [.NET Framework metadata]
ms.assetid: 67fefd89-28d6-4588-84ea-dc7a5870e014
topic_type:
- apiref
ms.openlocfilehash: 4d5bc66cdc292d390cb4ea187277fda8b8a071fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724202"
---
# <a name="coiniticor-enumeration"></a>Enumeração COINITICOR

Especifica constantes usadas pelo [CoInitializeCor](../hosting/coinitializecor-function.md) quando inicializa o Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum tagCOINITCOR  
{  
    COINITCOR = 0x0  
} COINITICOR;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`COINITCOR`|Indica o modo de inicialização padrão.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Enumerações de metadados](metadata-enumerations.md)
