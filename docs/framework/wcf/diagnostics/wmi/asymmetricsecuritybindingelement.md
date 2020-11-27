---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255722"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement

AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe AsymmetricSecurityBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe AsymmetricSecurityBindingElement tem as seguintes propriedades:  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 A ordem de criptografia e assinatura de mensagem para esta associação.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Se a associação requer confirmação de assinatura.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
