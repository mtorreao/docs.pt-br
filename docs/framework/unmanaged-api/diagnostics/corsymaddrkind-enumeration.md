---
title: Enumeração CorSymAddrKind
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
ms.openlocfilehash: f71d8956e8706cdc71b94b6e6e2e8210e5b9161e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725229"
---
# <a name="corsymaddrkind-enumeration"></a>Enumeração CorSymAddrKind

Indica o tipo de endereço de memória.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Indica uma variável local ou um índice de parâmetro da MSIL (Microsoft Intermediate Language).|  
|`ADDR_NATIVE_RVA`|Indica um endereço virtual relativo em um módulo.|  
|`ADDR_NATIVE_REGISTER`|Indica um registro de CPU.|  
|`ADDR_NATIVE_REGREL`|Indica que o primeiro endereço é um registro e o segundo endereço é um deslocamento.|  
|`ADDR_NATIVE_OFFSET`|Indica um deslocamento de um endereço base.|  
|`ADDR_NATIVE_REGREG`|Indica que o primeiro endereço é a parte inferior de um registro, e o segundo endereço é a parte superior.|  
|`ADDR_NATIVE_REGSTK`|Indica que o primeiro endereço é a parte inferior de um registro, o segundo é a parte superior e o terceiro é um deslocamento.|  
|`ADDR_NATIVE_STKREG`|Indica que o primeiro endereço é um registro, o segundo é um deslocamento e o terceiro é a parte superior do registro.|  
|`ADDR_BITFIELD`|Indica que o primeiro endereço é o início de um campo e o segundo endereço é o comprimento do campo.|  
|`ADDR_NATIVE_ISECTOFFSET`|Indica que o primeiro endereço é a seção e o segundo endereço é um deslocamento.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Enumerações de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-enumerations.md)
