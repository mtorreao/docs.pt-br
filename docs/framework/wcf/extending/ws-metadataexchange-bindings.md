---
title: WS-MetadataExchange Bindings
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293982"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="15b60-102">WS-MetadataExchange Bindings</span><span class="sxs-lookup"><span data-stu-id="15b60-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="15b60-103">Este tópico descreve como as associações de troca de metadados padrão são construídas para vários transportes.</span><span class="sxs-lookup"><span data-stu-id="15b60-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="15b60-104">As associações padrão</span><span class="sxs-lookup"><span data-stu-id="15b60-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="15b60-105">Nome de associação padrão</span><span class="sxs-lookup"><span data-stu-id="15b60-105">Default Binding Name</span></span>|<span data-ttu-id="15b60-106">Como a associação é construída</span><span class="sxs-lookup"><span data-stu-id="15b60-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="15b60-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="15b60-107">mexHttpBinding</span></span>|<span data-ttu-id="15b60-108">A <xref:System.ServiceModel.WSHttpBinding> com segurança em nível de transporte desabilitada.</span><span class="sxs-lookup"><span data-stu-id="15b60-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="15b60-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="15b60-109">mexHttpsBinding</span></span>|<span data-ttu-id="15b60-110">Um <xref:System.ServiceModel.WSHttpBinding> que dá suporte à segurança em nível de transporte.</span><span class="sxs-lookup"><span data-stu-id="15b60-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="15b60-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="15b60-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="15b60-112">Um  <xref:System.ServiceModel.Channels.CustomBinding> com um <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> usando os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="15b60-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="15b60-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="15b60-113">mexTcpBinding</span></span>|<span data-ttu-id="15b60-114">Um <xref:System.ServiceModel.Channels.CustomBinding> com um <xref:System.ServiceModel.Channels.TcpTransportBindingElement> usando valores padrão.</span><span class="sxs-lookup"><span data-stu-id="15b60-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
