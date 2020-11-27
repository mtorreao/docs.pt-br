---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 76cc619aed4ba2b944a8d11dc454a40368a4068c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269074"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute

OperationBehaviorAttribute  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe OperationBehaviorAttribute não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe OperationBehaviorAttribute tem as seguintes propriedades:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 O estado do recurso de disposição automática para parâmetros.  
  
### <a name="impersonation"></a>Representação  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Indica o nível de representação do chamador ao qual a operação dá suporte.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Indica quando no decorrer de uma invocação de operação para reciclar o objeto.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Indica se a transação atual deve ser confirmada automaticamente se não ocorrer nenhuma exceção não tratada.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Indica se a operação requer uma transação.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.OperationBehaviorAttribute>
