---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269789"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement

BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe BinaryMessageEncodingBindingElement não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe BinaryMessageEncodingBindingElement tem as propriedades a seguir.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens podem ser lidas simultaneamente sem alocar novos leitores.  
  
## <a name="maxsessionsize"></a>MaxSessionSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um valor que especifica o tamanho, em bytes, do buffer usado para codificação.  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  

 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens podem ser enviadas simultaneamente sem alocar novos gravadores.  
  
## <a name="readerquotas"></a>ReaderQuotas  

 Tipo de dados: XmlDictionaryReaderQuotas  
  
 Tipo de acesso: Somente leitura  
  
 As cotas dos leitores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
