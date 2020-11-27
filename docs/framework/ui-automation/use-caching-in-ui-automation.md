---
title: Usar armazenamento em cache em automação de interface do usuário
description: Consulte como usar o Caching na automação da interface do usuário. Examine as etapas para ativar uma solicitação de cache, armazenar em cache as propriedades AutomationElement e obter padrões armazenados em cache.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: f99fb724130c359a77c72db66dd9f837ef1a2219
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258602"
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="41d43-104">Usar armazenamento em cache em automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="41d43-104">Use Caching in UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="41d43-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="41d43-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="41d43-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="41d43-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="41d43-107">Esta seção mostra como implementar o cache de <xref:System.Windows.Automation.AutomationElement> Propriedades e padrões de controle.</span><span class="sxs-lookup"><span data-stu-id="41d43-107">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="41d43-108">Ativar uma solicitação de cache</span><span class="sxs-lookup"><span data-stu-id="41d43-108">Activate a Cache Request</span></span>  
  
1. <span data-ttu-id="41d43-109">Criará um <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="41d43-109">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="41d43-110">Especifique propriedades e padrões para armazenar em cache usando <xref:System.Windows.Automation.CacheRequest.Add%2A> .</span><span class="sxs-lookup"><span data-stu-id="41d43-110">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3. <span data-ttu-id="41d43-111">Especifique o escopo do cache definindo a <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="41d43-111">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4. <span data-ttu-id="41d43-112">Especifique a exibição da subárvore definindo a <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="41d43-112">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5. <span data-ttu-id="41d43-113">Defina a <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> propriedade como <xref:System.Windows.Automation.AutomationElementMode.None> se você quiser aumentar a eficiência ao não recuperar uma referência completa para objetos.</span><span class="sxs-lookup"><span data-stu-id="41d43-113">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="41d43-114">(Isso fará com que seja impossível recuperar os valores atuais desses objetos.)</span><span class="sxs-lookup"><span data-stu-id="41d43-114">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6. <span data-ttu-id="41d43-115">Ative a solicitação usando <xref:System.Windows.Automation.CacheRequest.Activate%2A> dentro de um `using` bloco ( `Using` no Microsoft Visual Basic .net).</span><span class="sxs-lookup"><span data-stu-id="41d43-115">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="41d43-116">Depois de obter <xref:System.Windows.Automation.AutomationElement> objetos ou assinar eventos, desative a solicitação usando <xref:System.Windows.Automation.CacheRequest.Pop%2A> (se <xref:System.Windows.Automation.CacheRequest.Push%2A> tiver sido usado) ou descartando o objeto criado pelo <xref:System.Windows.Automation.CacheRequest.Activate%2A> .</span><span class="sxs-lookup"><span data-stu-id="41d43-116">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="41d43-117">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> em um `using` bloco ( `Using` no Microsoft Visual Basic .net).</span><span class="sxs-lookup"><span data-stu-id="41d43-117">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in Microsoft Visual Basic .NET).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="41d43-118">Propriedades AutomationElement do cache</span><span class="sxs-lookup"><span data-stu-id="41d43-118">Cache AutomationElement Properties</span></span>  
  
1. <span data-ttu-id="41d43-119">Enquanto um <xref:System.Windows.Automation.CacheRequest> estiver ativo, obtenha <xref:System.Windows.Automation.AutomationElement> objetos usando <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> ou <xref:System.Windows.Automation.AutomationElement.FindAll%2A> ; ou obtenha um <xref:System.Windows.Automation.AutomationElement> como a origem de um evento que você registrou para quando o <xref:System.Windows.Automation.CacheRequest> estava ativo.</span><span class="sxs-lookup"><span data-stu-id="41d43-119">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="41d43-120">(Você também pode criar um cache passando um <xref:System.Windows.Automation.CacheRequest> para GetUpdatedCache ou um dos <xref:System.Windows.Automation.TreeWalker> métodos.)</span><span class="sxs-lookup"><span data-stu-id="41d43-120">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="41d43-121">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> ou recupere uma propriedade da <xref:System.Windows.Automation.AutomationElement.Cached%2A> Propriedade do <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="41d43-121">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="41d43-122">Obter padrões armazenados em cache e suas propriedades</span><span class="sxs-lookup"><span data-stu-id="41d43-122">Obtain Cached Patterns and Their Properties</span></span>  
  
1. <span data-ttu-id="41d43-123">Enquanto um <xref:System.Windows.Automation.CacheRequest> estiver ativo, obtenha <xref:System.Windows.Automation.AutomationElement> objetos usando <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> ou <xref:System.Windows.Automation.AutomationElement.FindAll%2A> ; ou obtenha um <xref:System.Windows.Automation.AutomationElement> como a origem de um evento que você registrou para quando o <xref:System.Windows.Automation.CacheRequest> estava ativo.</span><span class="sxs-lookup"><span data-stu-id="41d43-123">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="41d43-124">(Você também pode criar um cache passando um <xref:System.Windows.Automation.CacheRequest> para GetUpdatedCache ou um dos <xref:System.Windows.Automation.TreeWalker> métodos.)</span><span class="sxs-lookup"><span data-stu-id="41d43-124">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2. <span data-ttu-id="41d43-125">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> ou <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> para recuperar um padrão armazenado em cache.</span><span class="sxs-lookup"><span data-stu-id="41d43-125">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3. <span data-ttu-id="41d43-126">Recupere os valores de propriedade da `Cached` Propriedade do padrão de controle.</span><span class="sxs-lookup"><span data-stu-id="41d43-126">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d43-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="41d43-127">Example</span></span>  

 <span data-ttu-id="41d43-128">O exemplo de código a seguir mostra vários aspectos do cache, usando <xref:System.Windows.Automation.CacheRequest.Activate%2A> o para ativar o <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="41d43-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="41d43-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="41d43-129">Example</span></span>  

 <span data-ttu-id="41d43-130">O exemplo de código a seguir mostra vários aspectos do cache, usando <xref:System.Windows.Automation.CacheRequest.Push%2A> o para ativar o <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="41d43-130">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="41d43-131">Exceto quando você deseja aninhar solicitações de cache, é preferível usar <xref:System.Windows.Automation.CacheRequest.Activate%2A> .</span><span class="sxs-lookup"><span data-stu-id="41d43-131">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="41d43-132">Veja também</span><span class="sxs-lookup"><span data-stu-id="41d43-132">See also</span></span>

- [<span data-ttu-id="41d43-133">Armazenando em cache em clientes de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="41d43-133">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
