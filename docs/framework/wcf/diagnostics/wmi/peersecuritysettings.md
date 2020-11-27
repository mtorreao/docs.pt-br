---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268996"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings

PeerSecuritySettings  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe PeerSecuritySettings não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe PeerSecuritySettings tem as seguintes propriedades:  
  
### <a name="mode"></a>Mode  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Se a segurança em nível de transporte e nível de mensagem são usadas por um ponto de extremidade configurado com a associação.  
  
### <a name="transport"></a>Transport  

 Tipo de dados: PeerTransportSecuritySettings  
  
 Tipo de acesso: Somente leitura  
  
 Configurações de segurança de transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.PeerSecuritySettings>
