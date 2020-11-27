---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: b72bd3903b7139c4adf2a8bd0ced6c34e7285640
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274290"
---
# <a name="binding"></a>Associação

Associação WMI  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe de associação não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe de associação tem as propriedades a seguir.  
  
### <a name="bindingelements"></a>BindingElements  

 Tipo de dados: matriz BindingElement  
  
 Tipo de acesso: Somente leitura  
  
 A coleção de elementos de associação implementados pela associação.  
  
### <a name="closetimeout"></a>CloseTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O intervalo de tempo fornecido para a conclusão de uma operação de fechamento.  
  
### <a name="name"></a>Nome  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O nome da associação.  
  
### <a name="namespace"></a>Namespace  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O namespace XML da associação.  
  
### <a name="opentimeout"></a>OpenTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O intervalo de tempo fornecido para a conclusão de uma operação de abertura.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O intervalo de tempo fornecido para a conclusão de uma operação de recebimento.  
  
### <a name="scheme"></a>Esquema  

 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O esquema de transporte de URI que é usado pelas fábricas de canal e ouvinte criadas pela associação.  
  
### <a name="sendtimeout"></a>SendTimeout  

 Tipo de dados: DateTime  
  
 Tipo de acesso: Somente leitura  
  
 O intervalo de tempo fornecido para a conclusão de uma operação de envio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Channels.Binding>
