---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: b4d8503543c93d0112fc39e4b2dba5434bc56472
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237398"
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement

MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe MtomMessageEncodingBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe MtomMessageEncodingBindingElement tem as seguintes propriedades:  
  
### <a name="encoding"></a>Codificação  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 A codificação do conjunto de caracteres a ser usada para emitir mensagens na associação.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens podem ser lidas simultaneamente sem alocar novos leitores.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens podem ser enviadas simultaneamente sem alocar novos gravadores.  
  
### <a name="readerquotas"></a>ReaderQuotas  

 Tipo de dados: XmlDictionaryReaderQuotas  
  
 Tipo de acesso: Somente leitura  
  
 As cotas dos leitores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
