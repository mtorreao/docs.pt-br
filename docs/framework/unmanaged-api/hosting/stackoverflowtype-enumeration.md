---
title: Enumeração StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729900"
---
# <a name="stackoverflowtype-enumeration"></a>Enumeração StackOverflowType

Contém valores que indicam a causa subjacente de um evento de estouro de pilha.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`SO_ClrEngine`|O estouro de pilha foi causado pelo mecanismo de execução.|  
|`SO_Managed`|O estouro de pilha foi causado por código gerenciado.|  
|`SO_Other`|O estouro de pilha foi causado por código não gerenciado.|  
  
## <a name="remarks"></a>Comentários  

 Essas informações são passadas para o host por meio de uma chamada para o método [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Hospedando enumerações](hosting-enumerations.md)
