---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234837"
---
# <a name="transportbindingelement"></a>TransportBindingElement

TransportBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe TransportBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe TransportBindingElement tem as seguintes propriedades:  
  
### <a name="manualaddressing"></a>ManualAddressing  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Um valor booliano que especifica se o usuário deseja assumir o controle do endereçamento de mensagens.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  

 Tipo de dados: sint64  
  
 Tipo de acesso: Somente leitura  
  
 O tamanho máximo do pool de buffers para a associação.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  

 Tipo de dados: sint64  
  
 Tipo de acesso: Somente leitura  
  
 O tamanho máximo de uma mensagem que é processada por essa associação.  
  
### <a name="scheme"></a>Esquema  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O esquema de URI para o transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.TransportBindingElement>
