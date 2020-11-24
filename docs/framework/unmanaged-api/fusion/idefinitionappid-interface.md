---
title: Interface IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
ms.openlocfilehash: 1e6c42d8e74d2d3e7925c657c67832f662416e64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673859"
---
# <a name="idefinitionappid-interface"></a>Interface IDefinitionAppId

Representa um identificador exclusivo para o código que define o aplicativo no escopo atual.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Obtém uma cadeia de caracteres formatada que representa o código neste `IDefinitionAppId` objeto.|  
|`IDefinitionAppId::put_Codebase`|Define o código desse `IDefinitionAppId` objeto como o valor de cadeia de caracteres formatado especificado.|  
|`IDefinitionAppId::EnumAppPath`|Obtém um ponteiro de interface para um objeto [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) que contém os assemblies no caminho do aplicativo atual.|  
|`IDefinitionAppId::SetAppPath`|Define o caminho do aplicativo para o assembly no escopo atual como o valor referenciado pelo objeto [IDefinitionIdentity](idefinitionidentity-interface.md) especificado.|  
|`IDefinitionAppId::get_SubscriptionId`|Obtém um ponteiro para uma representação de cadeia de caracteres do identificador de token para uma assinatura para este `IDefinitionAppId` objeto.|  
|`IDefinitionAppId::put_SubscriptionId`|Define o identificador de token de uma assinatura para esse `IDefinitionAppId` objeto para o valor de cadeia de caracteres especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Isolamento. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de fusão](fusion-interfaces.md)
