---
title: Disparar Eventos de um Provedor de Automação UI
description: Consulte um exemplo que mostra como gerar um evento de um provedor de automação de interface do usuário. Ele gera um evento de automação da interface do usuário na implementação de um controle de botão personalizado.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 73be7fd92f3fde90255326c51bed03427fd68e8d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250483"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="9af2e-104">Disparar Eventos de um Provedor de Automação UI</span><span class="sxs-lookup"><span data-stu-id="9af2e-104">Raise Events from a UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="9af2e-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="9af2e-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="9af2e-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="9af2e-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="9af2e-107">Este tópico contém um código de exemplo que mostra como gerar um evento de um provedor de automação de interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9af2e-107">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9af2e-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9af2e-108">Example</span></span>  

 <span data-ttu-id="9af2e-109">No exemplo a seguir, um [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] evento é gerado na implementação de um controle de botão personalizado.</span><span class="sxs-lookup"><span data-stu-id="9af2e-109">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="9af2e-110">A implementação permite que um aplicativo cliente de automação da interface do usuário simule um clique de botão.</span><span class="sxs-lookup"><span data-stu-id="9af2e-110">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="9af2e-111">Para evitar o processamento desnecessário, o exemplo verifica <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> se os eventos devem ser gerados.</span><span class="sxs-lookup"><span data-stu-id="9af2e-111">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="9af2e-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="9af2e-112">See also</span></span>

- [<span data-ttu-id="9af2e-113">Visão Geral dos Provedores de Automação de Interface do Usuário</span><span class="sxs-lookup"><span data-stu-id="9af2e-113">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
