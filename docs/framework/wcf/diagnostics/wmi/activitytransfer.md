---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291109"
---
# <a name="activitytransfer"></a>ActivityTransfer

Evento de transferência de atividade  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe ActivityTransfer não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe ActivityTransfer tem as seguintes propriedades:  
  
### <a name="activityid"></a>ActivityID  
  
- Tipo de dados: objeto  
    Tipo de acesso: Somente leitura  
  
- ID da atividade  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Tipo de dados: objeto  
    Tipo de acesso: Somente leitura  
  
- ID da atividade relacionada  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel.|
