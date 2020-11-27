---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274043"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe DeliveryRequirementsAttribute não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe DeliveryRequirementsAttribute tem as seguintes propriedades:  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Especifica se a associação de um serviço dá suporte a contratos.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Especifica se a associação oferece suporte a mensagens ordenadas.  
  
### <a name="targetcontract"></a>TargetContract  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O contrato ao qual se aplica.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
