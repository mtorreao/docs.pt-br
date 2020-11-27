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
# <a name="binding-extensibility"></a><span data-ttu-id="cf278-102">Extensibilidade de associação</span><span class="sxs-lookup"><span data-stu-id="cf278-102">Binding Extensibility</span></span>

<span data-ttu-id="cf278-103">Esta seção contém exemplos que demonstram a associação personalizada no Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cf278-103">This section contains samples that demonstrate custom binding in Windows Communication Foundation (WCF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf278-104">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cf278-104">In This Section</span></span>  

 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="cf278-105">Demonstra como implementar uma ligação que empilha <xref:System.ServiceModel.Channels.HttpTransportBindingElement> ou <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> na parte superior do <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="cf278-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="cf278-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cf278-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="cf278-107">Demonstra como criar uma associação que é projetada para dar suporte a cenários de streaming quando o transporte HTTP é usado.</span><span class="sxs-lookup"><span data-stu-id="cf278-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
