---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269009"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement

PeerTransportBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe PeerTransportBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe PeerTransportBindingElement tem as seguintes propriedades:  
  
### <a name="listenipaddress"></a>ListenIPAddress  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O endereço IP no qual o nó par escuta mensagens.  
  
### <a name="port"></a>Porta  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A porta da interface de rede na qual essa associação processa mensagens de canal de mesmo nível.  
  
### <a name="security"></a>Segurança  

 Tipo de dados: PeerSecuritySettings  
  
 Tipo de acesso: Somente leitura  
  
 Configurações de segurança de transporte de pares.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
