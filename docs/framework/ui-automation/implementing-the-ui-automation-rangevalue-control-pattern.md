---
title: Implementando o padrão de controle RangeValue de interface de usuário
description: Examine as diretrizes e convenções para implementar o padrão de controle RangeValue na automação da interface do usuário. Consulte membros necessários para a interface IRangeValueProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: 9b5bfd571b078b7aeab149f5371004ac832fadcc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239556"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="519ac-104">Implementando o padrão de controle RangeValue de interface de usuário</span><span class="sxs-lookup"><span data-stu-id="519ac-104">Implementing the UI Automation RangeValue Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="519ac-105">Esta documentação destina-se a desenvolvedores do .NET Framework que querem usar as classes da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gerenciadas definidas no namespace <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="519ac-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="519ac-106">Para obter as informações mais recentes sobre a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32) (API de Automação do Windows: Automação da Interface do Usuário).</span><span class="sxs-lookup"><span data-stu-id="519ac-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="519ac-107">Este tópico apresenta diretrizes e convenções para implementação <xref:System.Windows.Automation.Provider.IRangeValueProvider> , incluindo informações sobre eventos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="519ac-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="519ac-108">Links para referências adicionais são listados no final do tópico.</span><span class="sxs-lookup"><span data-stu-id="519ac-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="519ac-109">O <xref:System.Windows.Automation.RangeValuePattern> padrão de controle é usado para dar suporte a controles que podem ser definidos para um valor dentro de um intervalo.</span><span class="sxs-lookup"><span data-stu-id="519ac-109">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="519ac-110">Para obter exemplos de controles que implementam esse padrão de controle, consulte [mapeamento de padrão de controle para clientes de automação da interface do usuário](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="519ac-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="519ac-111">Diretrizes e convenções de implementação</span><span class="sxs-lookup"><span data-stu-id="519ac-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="519ac-112">Ao implementar o padrão de controle de valor de intervalo, observe as seguintes diretrizes e convenções:</span><span class="sxs-lookup"><span data-stu-id="519ac-112">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="519ac-113">Os controles permitem a recalibração de suas propriedades com suporte com base na localidade ou na preferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="519ac-113">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="519ac-114">Um exemplo disso é um controle de termômetro que pode ser definido para exibir a temperatura em Fahrenheit ou Celsius.</span><span class="sxs-lookup"><span data-stu-id="519ac-114">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="519ac-115">Controles que têm valores de intervalo ambíguos, como barras de progresso ou controles deslizantes, devem ter esses valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="519ac-115">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="519ac-116">![Barra de progresso.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="519ac-116">![Progress bar.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="519ac-117">Exemplo de uma barra de progresso em que o valor é do tipo inteiro e os valores de propriedade mínimo e máximo são normalizados para 0 e 100, respectivamente</span><span class="sxs-lookup"><span data-stu-id="519ac-117">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>

## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="519ac-118">Membros necessários para IRangeValueProvider</span><span class="sxs-lookup"><span data-stu-id="519ac-118">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="519ac-119">Membro necessário</span><span class="sxs-lookup"><span data-stu-id="519ac-119">Required member</span></span>|<span data-ttu-id="519ac-120">Tipo de membro</span><span class="sxs-lookup"><span data-stu-id="519ac-120">Member type</span></span>|<span data-ttu-id="519ac-121">Observações</span><span class="sxs-lookup"><span data-stu-id="519ac-121">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="519ac-122">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-122">Property</span></span>|<span data-ttu-id="519ac-123">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="519ac-124">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-124">Property</span></span>|<span data-ttu-id="519ac-125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="519ac-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-126">Property</span></span>|<span data-ttu-id="519ac-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="519ac-128">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-128">Property</span></span>|<span data-ttu-id="519ac-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="519ac-130">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-130">Property</span></span>|<span data-ttu-id="519ac-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="519ac-132">Propriedade</span><span class="sxs-lookup"><span data-stu-id="519ac-132">Property</span></span>|<span data-ttu-id="519ac-133">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-133">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="519ac-134">Métodos</span><span class="sxs-lookup"><span data-stu-id="519ac-134">Methods</span></span>|<span data-ttu-id="519ac-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="519ac-135">None</span></span>|  
  
 <span data-ttu-id="519ac-136">Este padrão de controle não tem eventos associados.</span><span class="sxs-lookup"><span data-stu-id="519ac-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="519ac-137">Exceções</span><span class="sxs-lookup"><span data-stu-id="519ac-137">Exceptions</span></span>  

 <span data-ttu-id="519ac-138">Os provedores devem lançar as seguintes exceções.</span><span class="sxs-lookup"><span data-stu-id="519ac-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="519ac-139">Tipo de exceção</span><span class="sxs-lookup"><span data-stu-id="519ac-139">Exception type</span></span>|<span data-ttu-id="519ac-140">Condição</span><span class="sxs-lookup"><span data-stu-id="519ac-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="519ac-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> é chamado com um valor que é maior <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> ou menor que <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty> .</span><span class="sxs-lookup"><span data-stu-id="519ac-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="519ac-142">Veja também</span><span class="sxs-lookup"><span data-stu-id="519ac-142">See also</span></span>

- [<span data-ttu-id="519ac-143">Visão Geral de Padrões de Controle de Automação de Interface de Usuário</span><span class="sxs-lookup"><span data-stu-id="519ac-143">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="519ac-144">Padrões de controle de suporte em um provedor de automação da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="519ac-144">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="519ac-145">Padrões de Controle para Clientes de Automação de IU</span><span class="sxs-lookup"><span data-stu-id="519ac-145">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="519ac-146">Visão geral da árvore de automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="519ac-146">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="519ac-147">Usar armazenamento em cache em automação de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="519ac-147">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
