---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290082"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement

TcpTransportBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe TcpTransportBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe TcpTransportBindingElement tem as seguintes propriedades:  
  
### <a name="connectionpoolsettings"></a>ConnectionPoolSettings  

 Tipo de dados: TcpConnectionPoolSettings  
  
 Tipo de acesso: Somente leitura  
  
 As configurações do pool de conexões.  
  
### <a name="listenbacklog"></a>ListenBacklog  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 O número máximo de solicitações de conexão em fila que podem estar pendentes.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Um valor booliano que especifica se o compartilhamento de porta TCP está habilitado para esta conexão.  
  
### <a name="teredoenabled"></a>TeredoEnabled  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Um valor booliano que especifica se Teredo (uma tecnologia para endereçar clientes que estão atrás de firewalls) está habilitado.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
