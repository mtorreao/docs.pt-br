---
title: Enumeração CREATE_ASM_NAME_OBJ_FLAGS
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: 52d5ad3a18c102422e90621c7d1e23b2692c0000
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683220"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>Enumeração CREATE_ASM_NAME_OBJ_FLAGS

Especifica os atributos de um objeto de [interface IAssemblyName](iassemblyname-interface.md) quando ele é construído pela função [CreateAssemblyNameObject](createassemblynameobject-function.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Indica que o parâmetro passado é uma identidade textual.|  
|`CANOF_SET_DEFAULT_VALUES`|Define alguns valores padrão.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Verifica a regra do assembly Friend (somente nome e chave pública). Este membro é somente para uso interno.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Uma combinação dos `CANOF_PARSE_DISPLAY_NAME` sinalizadores e `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` . Este membro é somente para uso interno.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IAssemblyName](iassemblyname-interface.md)
- [Função CreateAssemblyNameObject](createassemblynameobject-function.md)
- [Enumerações Fusion](fusion-enumerations.md)
