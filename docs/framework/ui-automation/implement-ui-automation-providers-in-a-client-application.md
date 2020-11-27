---
title: Implementar provedores de automação de interface do usuário em um aplicativo cliente
description: Consulte um exemplo de como implementar um provedor de automação de interface do usuário no lado do cliente em um aplicativo. Observe que esse é um cenário incomum.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: 486e05f9080b686c48454dfcfceaaa666fa57f67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269581"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="01c81-104">Implementar provedores de automação de interface do usuário em um aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="01c81-104">Implement UI Automation Providers in a Client Application</span></span>

> [!NOTE]
> <span data-ttu-id="01c81-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="01c81-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="01c81-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="01c81-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="01c81-107">Este tópico contém um código de exemplo que mostra como implementar um provedor de automação de interface do usuário no lado do cliente em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="01c81-107">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="01c81-108">Esse é um cenário incomum.</span><span class="sxs-lookup"><span data-stu-id="01c81-108">This is an uncommon scenario.</span></span> <span data-ttu-id="01c81-109">Geralmente, um aplicativo cliente de automação de interface do usuário usa provedores do lado do servidor ou provedores do lado do cliente que residem em uma DLL.</span><span class="sxs-lookup"><span data-stu-id="01c81-109">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01c81-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="01c81-110">Example</span></span>  

 <span data-ttu-id="01c81-111">O código de exemplo a seguir implementa um provedor simples para uma janela de console.</span><span class="sxs-lookup"><span data-stu-id="01c81-111">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="01c81-112">O código não tem nenhuma funcionalidade útil, mas destina-se a demonstrar as etapas básicas na configuração de um provedor dentro do código do cliente e seu registro usando o <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A> .</span><span class="sxs-lookup"><span data-stu-id="01c81-112">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="01c81-113">Veja também</span><span class="sxs-lookup"><span data-stu-id="01c81-113">See also</span></span>

- [<span data-ttu-id="01c81-114">Visão Geral dos Provedores de Automação de Interface do Usuário</span><span class="sxs-lookup"><span data-stu-id="01c81-114">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="01c81-115">Registrar um Módulo Provedor do Lado do Cliente</span><span class="sxs-lookup"><span data-stu-id="01c81-115">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="01c81-116">Criar um Provedor de Automação de Interface de Usuário do Lado do Cliente</span><span class="sxs-lookup"><span data-stu-id="01c81-116">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="01c81-117">Implementação de Provedor de Automação de Interface de Usuário do Lado do Cliente</span><span class="sxs-lookup"><span data-stu-id="01c81-117">Client-Side UI Automation Provider Implementation</span></span>](client-side-ui-automation-provider-implementation.md)
