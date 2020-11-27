---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: c6ebb585454054ca9a03c46cf738001c58f9b18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273406"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement

PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe PrivacyNoticeBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe PrivacyNoticeBindingElement tem as seguintes propriedades:  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 A versão do aviso de privacidade.  
  
### <a name="url"></a>Url  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 A URL na qual o aviso de privacidade está localizado.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
