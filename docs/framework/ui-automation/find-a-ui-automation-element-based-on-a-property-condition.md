---
title: Localizar um elemento de automação de interface do usuário com base na condição de uma propriedade
description: Localizar um elemento de automação da interface do usuário com base em uma condição de propriedade. Localize um elemento dentro da árvore de automação da interface do usuário com base em uma propriedade ou propriedades específicas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 603ecf5375af919a558168e14792035a16fb20f2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276484"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="a413e-104">Localizar um elemento de automação de interface do usuário com base na condição de uma propriedade</span><span class="sxs-lookup"><span data-stu-id="a413e-104">Find a UI Automation Element Based on a Property Condition</span></span>

> [!NOTE]
> <span data-ttu-id="a413e-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a413e-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a413e-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="a413e-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a413e-107">Este tópico contém um código de exemplo que mostra como localizar um elemento dentro da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] árvore com base em uma propriedade ou propriedades específicas.</span><span class="sxs-lookup"><span data-stu-id="a413e-107">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a413e-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a413e-108">Example</span></span>  

 <span data-ttu-id="a413e-109">No exemplo a seguir, são especificados um conjunto de condições de propriedade que identificam um determinado elemento (ou elementos) de interesse na <xref:System.Windows.Automation.AutomationElement> árvore.</span><span class="sxs-lookup"><span data-stu-id="a413e-109">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="a413e-110">Uma pesquisa por todos os elementos correspondentes é então executada com o <xref:System.Windows.Automation.AutomationElement.FindAll%2A> método que incorpora uma série de <xref:System.Windows.Automation.AndCondition> operações booleanas para limitar o número de elementos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a413e-110">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a413e-111">Ao pesquisar no <xref:System.Windows.Automation.AutomationElement.RootElement%2A> , você deve tentar obter apenas os filhos diretos.</span><span class="sxs-lookup"><span data-stu-id="a413e-111">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="a413e-112">Uma pesquisa por descendentes pode iterar por centenas ou até milhares de elementos, possivelmente resultando em um estouro de pilha.</span><span class="sxs-lookup"><span data-stu-id="a413e-112">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="a413e-113">Se você estiver tentando obter um elemento específico em um nível inferior, deverá iniciar a pesquisa na janela do aplicativo ou em um contêiner em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="a413e-113">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="a413e-114">Veja também</span><span class="sxs-lookup"><span data-stu-id="a413e-114">See also</span></span>

- <span data-ttu-id="a413e-115">[Exemplo de item de menu InvokePattern e ExpandCollapsePattern](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="a413e-115">[InvokePattern and ExpandCollapsePattern Menu Item Sample](/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="a413e-116">Obtendo elementos da automação interface do usuário</span><span class="sxs-lookup"><span data-stu-id="a413e-116">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="a413e-117">Usar a propriedade AutomationID</span><span class="sxs-lookup"><span data-stu-id="a413e-117">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
