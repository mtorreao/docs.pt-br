---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294671"
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings

TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe TcpConnectionPoolSettings não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe TcpConnectionPoolSettings tem as seguintes propriedades:  
  
### <a name="groupname"></a>GroupName  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O nome do grupo do pool de conexão usado pelo elemento de associação.  
  
### <a name="idletimeout"></a>IdleTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O tempo máximo que a conexão pode ficar ociosa antes de ser desconectada.  
  
### <a name="leasetimeout"></a>LeaseTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O tempo máximo para que a operação de concessão seja concluída antes de atingir o tempo limite.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de conexões de saída para cada ponto de extremidade.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
