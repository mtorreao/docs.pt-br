---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 3c69b73cc05a56a7556630de0f83675590442293
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274147"
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement

ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe ConnectionOrientedTransportBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe ConnectionOrientedTransportBindingElement tem as seguintes propriedades:  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O TimeSpan que especifica por quanto tempo a inicialização do canal deve ser concluída antes de atingir o tempo limite.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O tamanho do buffer usado para transmitir uma parte da mensagem serializada na conexão do cliente ou serviço.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Um valor que indica se o nome do host é usado para acessar o serviço ao fazer a correspondência no URI.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O tamanho máximo do buffer a ser usado.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O intervalo máximo de tempo que uma parte de uma mensagem ou uma mensagem completa pode permanecer armazenada em buffer na memória antes de ser enviada.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de threads de aceitação assíncrona pendentes que estão disponíveis para processar conexões de entrada no serviço.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de conexões pendentes.  
  
### <a name="transfermode"></a>TransferMode  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Um valor que especifica se as mensagens são armazenadas em buffer ou transmitidas com o transporte orientado a conexão.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
