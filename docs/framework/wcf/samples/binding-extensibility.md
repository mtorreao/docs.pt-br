---
title: Extensibilidade de associação
ms.date: 03/30/2017
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
ms.openlocfilehash: c99713416181aed8a8800c819e0f5786411187ab
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283595"
---
# <a name="binding-extensibility"></a>Extensibilidade de associação

Esta seção contém exemplos que demonstram a associação personalizada no Windows Communication Foundation (WCF).  
  
## <a name="in-this-section"></a>Nesta seção  

 <xref:System.ServiceModel.NetHttpBinding>  
 Demonstra como implementar uma ligação que empilha <xref:System.ServiceModel.Channels.HttpTransportBindingElement> ou <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> na parte superior do <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> .  
  
 [WSStreamedHttpBinding](wsstreamedhttpbinding.md)  
 Demonstra como criar uma associação que é projetada para dar suporte a cenários de streaming quando o transporte HTTP é usado.  
