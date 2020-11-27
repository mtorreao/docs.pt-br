---
title: Comparando transações em COM+ e ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 30ecbd374e909141dbc944740f90c1b41ac44ed2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264902"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Comparando transações em COM+ e ServiceModel

Este tópico discute como simular o comportamento de um serviço COM+ transacional usando os atributos de Windows Communication Foundation (WCF) que o <xref:System.ServiceModel> namespace fornece.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulando COM+ usando atributos de ServiceModel  

 A tabela a seguir compara a <xref:System.EnterpriseServices.TransactionOption> enumeração usada para criar uma `EnterpriseServices` transação e como elas se correlacionam aos atributos do WCF que o <xref:System.ServiceModel> namespace fornece.  
  
|Atributo COM+|Atributos do WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute> é definido como <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> é `true`.<br /><br /> O `TransactionFlow` atributo no elemento de associação é `false` .|  
|Necessária|<xref:System.ServiceModel.TransactionFlowAttribute> é definido como <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> é `true`.<br /><br /> O `TransactionFlow` atributo no elemento de associação é `true` .|  
|Com suporte|Não há equivalente direto. Em geral, você deve adotar o comportamento especificado para `Required` , em vez disso.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> é `false`.<br /><br /> O `TransactionFlow` atributo no elemento de associação é `false` .|  
|Desabilitado|Não há equivalente direto. Em geral, você deve adotar o comportamento especificado para `NotSupported` , em vez disso.|
