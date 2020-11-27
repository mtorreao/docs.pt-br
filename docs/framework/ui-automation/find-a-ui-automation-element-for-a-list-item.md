---
title: Encontrar um Elemento de Automação de Interface de Usuário para um Item de Lista
description: Veja um exemplo que mostra como localizar um elemento de automação da interface do usuário para um item de lista quando o índice do item é conhecido.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 95f6b558cc53b00701232f247f8de7f8c603e3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276471"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="e6904-103">Encontrar um Elemento de Automação de Interface de Usuário para um Item de Lista</span><span class="sxs-lookup"><span data-stu-id="e6904-103">Find a UI Automation Element for a List Item</span></span>

> [!NOTE]
> <span data-ttu-id="e6904-104">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="e6904-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e6904-105">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="e6904-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e6904-106">Este tópico mostra como recuperar um <xref:System.Windows.Automation.AutomationElement> para um item dentro de uma lista quando o índice do item é conhecido.</span><span class="sxs-lookup"><span data-stu-id="e6904-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6904-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e6904-107">Example</span></span>  

 <span data-ttu-id="e6904-108">O exemplo a seguir mostra duas maneiras de recuperar um item especificado de uma lista, um usando <xref:System.Windows.Automation.TreeWalker> o e o outro usando <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .</span><span class="sxs-lookup"><span data-stu-id="e6904-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="e6904-109">A primeira técnica tende a ser mais rápida para controles do Win32, mas a segunda é mais rápida para controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e6904-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="e6904-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="e6904-110">See also</span></span>

- [<span data-ttu-id="e6904-111">Obtendo elementos da automação interface do usuário</span><span class="sxs-lookup"><span data-stu-id="e6904-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
