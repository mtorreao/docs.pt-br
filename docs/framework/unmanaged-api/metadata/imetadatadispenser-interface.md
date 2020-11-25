---
title: Interface IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: c798aeba46adf91a8c13f8143c00f02173a0bb52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726100"
---
# <a name="imetadatadispenser-interface"></a>Interface IMetaDataDispenser

Fornece métodos para criar um novo escopo de metadados ou abrir um existente.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método DefineScope](imetadatadispenser-definescope-method.md)|Cria uma nova área na memória na qual você pode criar novos metadados.|  
|[Método OpenScope](imetadatadispenser-openscope-method.md)|Abre um arquivo existente em disco e mapeia seus metadados na memória.|  
|[Método OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md)|Abre uma área de memória que contém os metadados existentes. Ou seja, esse método abre uma área especificada de memória na qual os dados existentes são tratados como metadados.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaces de metadados](metadata-interfaces.md)
