---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 867219130fc853f3ba2c1c2f807b1651f6480f13
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273965"
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior

ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe ServiceTimeoutsBehavior não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe ServiceTimeoutsBehavior tem a seguinte propriedade:  
  
### <a name="transactiontimeout"></a>TransactionTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O período no qual uma transação deve ser concluída.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
