---
title: Interface IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701842"
---
# <a name="imetadatafilter-interface"></a>Interface IMetaDataFilter

Fornece métodos para marcação e filtragem de tokens de metadados para evitar ações repetidas que já foram realizadas.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método IsTokenMarked](imetadatafilter-istokenmarked-method.md)|Obtém um valor que indica se o token de metadados especificado foi processado.|  
|[Método MarkToken](imetadatafilter-marktoken-method.md)|Define um valor que indica que o token de metadados especificado foi processado.|  
|[Método UnmarkAll](imetadatafilter-unmarkall-method.md)|Remove as marcas de processamento de todos os tokens no escopo de metadados atual.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de metadados](metadata-interfaces.md)
