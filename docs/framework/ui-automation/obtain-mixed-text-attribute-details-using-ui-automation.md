---
title: Obter detalhes de atributos de texto misto usando automação de interface do usuário
description: Obtenha detalhes de atributo de texto misto usando as classes de automação da interface do usuário gerenciada no namespace System. Windows. Automation da API do .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: ac6b212a8cb3f2f0cfa0d645aba2f0984ed8eb60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274641"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a><span data-ttu-id="981a9-103">Obter detalhes de atributos de texto misto usando automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="981a9-103">Obtain Mixed Text Attribute Details Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="981a9-104">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="981a9-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="981a9-105">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="981a9-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="981a9-106">Este tópico mostra como usar o [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obter detalhes de atributo de texto de um intervalo de texto que abrange vários valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="981a9-106">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attribute details from a text range that spans multiple attribute values.</span></span> <span data-ttu-id="981a9-107">Um intervalo de texto pode corresponder ao local atual do cursor (ou degenerar a seleção) dentro de um documento, uma seleção de texto contígua, uma coleção de seleções de texto não contíguos ou todo o conteúdo textual de um documento.</span><span class="sxs-lookup"><span data-stu-id="981a9-107">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="981a9-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="981a9-108">Example</span></span>  

 <span data-ttu-id="981a9-109">O exemplo de código a seguir demonstra como obter o <xref:System.Windows.Automation.TextPattern.FontNameAttribute> de um intervalo de texto em que <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> retorna um <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> objeto.</span><span class="sxs-lookup"><span data-stu-id="981a9-109">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range where <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> returns a <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> object.</span></span>  
  
[!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
[!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 <span data-ttu-id="981a9-110">O <xref:System.Windows.Automation.TextPattern> padrão de controle, em conjunto com a <xref:System.Windows.Automation.Text.TextPatternRange> classe, dá suporte a atributos, propriedades e métodos de texto básico.</span><span class="sxs-lookup"><span data-stu-id="981a9-110">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="981a9-111">Para funcionalidade específica de controle que não é suportada pelo <xref:System.Windows.Automation.TextPattern> ou <xref:System.Windows.Automation.Text.TextPatternRange> , a <xref:System.Windows.Automation.AutomationElement> classe fornece métodos para um cliente de automação da interface do usuário acessar o modelo de objeto nativo correspondente.</span><span class="sxs-lookup"><span data-stu-id="981a9-111">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange>, the <xref:System.Windows.Automation.AutomationElement> class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981a9-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="981a9-112">See also</span></span>

- [<span data-ttu-id="981a9-113">Visão geral de TextPattern de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="981a9-113">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="981a9-114">Acrescentar Conteúdo a um Text Box Utilizando Automação de IU</span><span class="sxs-lookup"><span data-stu-id="981a9-114">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="981a9-115">Encontre e destaque texto usando automação de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="981a9-115">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="981a9-116">Visão Geral de Padrões de Controle de Automação de Interface de Usuário</span><span class="sxs-lookup"><span data-stu-id="981a9-116">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="981a9-117">Padrões de Controle para Clientes de Automação de IU</span><span class="sxs-lookup"><span data-stu-id="981a9-117">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="981a9-118">Obter atributos de texto usando automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="981a9-118">Obtain Text Attributes Using UI Automation</span></span>](obtain-text-attributes-using-ui-automation.md)
