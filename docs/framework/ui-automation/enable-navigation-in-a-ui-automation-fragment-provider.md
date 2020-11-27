---
title: Permitir navegação em um fragmento por um provedor de automação de interface do usuário
description: Leia um exemplo que mostra como habilitar a navegação em um provedor de automação de interface do usuário para um elemento que está dentro de um fragmento.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: d8fb67a84b7cba84fe65cd2f87baa6549122d2a2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276497"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="36781-103">Permitir navegação em um fragmento por um provedor de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="36781-103">Enable Navigation in a UI Automation Fragment Provider</span></span>

> [!NOTE]
> <span data-ttu-id="36781-104">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="36781-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="36781-105">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="36781-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="36781-106">Este tópico contém um código de exemplo que mostra como habilitar a navegação em um provedor de automação de interface do usuário para um elemento que está dentro de um fragmento.</span><span class="sxs-lookup"><span data-stu-id="36781-106">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36781-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="36781-107">Example</span></span>  

 <span data-ttu-id="36781-108">O código de exemplo a seguir implementa <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> para um item de lista em uma lista.</span><span class="sxs-lookup"><span data-stu-id="36781-108">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="36781-109">O elemento pai é o elemento da caixa de listagem e os elementos irmãos são outros itens na coleção de listas.</span><span class="sxs-lookup"><span data-stu-id="36781-109">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="36781-110">O método retorna `null` ( `Nothing` em Visual Basic) para direções que não são válidas; nesse caso, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> e <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild> , porque o elemento não tem filhos.</span><span class="sxs-lookup"><span data-stu-id="36781-110">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="36781-111">Veja também</span><span class="sxs-lookup"><span data-stu-id="36781-111">See also</span></span>

- [<span data-ttu-id="36781-112">Visão Geral dos Provedores de Automação de Interface do Usuário</span><span class="sxs-lookup"><span data-stu-id="36781-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="36781-113">Implementação do provedor de automação de interface do usuário no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="36781-113">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
