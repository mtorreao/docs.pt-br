---
title: Enumeração CorFileMapping
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726109"
---
# <a name="corfilemapping-enumeration"></a>Enumeração CorFileMapping

Contém valores que descrevem o tipo de mapeamento de arquivo que é retornado de uma chamada para o método [IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`fmFlat`|O arquivo é mapeado como um arquivo de dados. Ou seja, o `SEC_IMAGE` sinalizador não foi passado para a função Microsoft Win32 `CreateFileMapping` .|  
|`fmExecutableImage`|O arquivo é mapeado para execução, usando a `LoadLibrary` função ou a `CreateFileMapping` função com o `SEC_IMAGE` sinalizador.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorHdr. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Enumerações de metadados](metadata-enumerations.md)
- [Método GetFileMapping](imetadatainfo-getfilemapping-method.md)
