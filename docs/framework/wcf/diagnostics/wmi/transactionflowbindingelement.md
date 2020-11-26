---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234889"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement

TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe TransactionFlowBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe TransactionFlowBindingElement tem as seguintes propriedades:  
  
### <a name="issuedtokens"></a>IssuedTokens  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Especifica o requisito para um cabeçalho de tokens de segurança emitidos (IssuedTokens de WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O protocolo de transações usado pelo serviço para o fluxo de transações.  
  
### <a name="transactions"></a>Transactions  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Indica se há suporte para a transação de entrada.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
