---
title: Atividades do computador de estado em WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: dd0bfae1f24ecd9f98c0a2f04265581f880202a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261716"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="94823-102">Atividades do computador de estado em WF</span><span class="sxs-lookup"><span data-stu-id="94823-102">State Machine Activities in WF</span></span>

<span data-ttu-id="94823-103">O .NET Framework 4,5 fornece várias atividades fornecidas pelo sistema e designers de atividade para a criação de fluxos de trabalho de máquina de estado.</span><span class="sxs-lookup"><span data-stu-id="94823-103">.NET Framework 4.5 provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="94823-104">Executes continha atividades usando o paradigma familiar do computador de estado.</span><span class="sxs-lookup"><span data-stu-id="94823-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="94823-105">Representa um estado em uma máquina de estado.</span><span class="sxs-lookup"><span data-stu-id="94823-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="94823-106">Representa um estado de terminação em um computador de estado.</span><span class="sxs-lookup"><span data-stu-id="94823-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="94823-107"><xref:System.Activities.Core.Presentation.FinalState> é um designer de atividade que quando usado criar <xref:System.Activities.Statements.State> pré-configurado como um estado de terminação.</span><span class="sxs-lookup"><span data-stu-id="94823-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="94823-108">Para obter mais informações, consulte o [Designer de atividade FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="94823-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="94823-109">Representa a transição entre dois estados.</span><span class="sxs-lookup"><span data-stu-id="94823-109">Represents the transition between two states.</span></span> <span data-ttu-id="94823-110">Não há nenhum item de **caixa de ferramentas** para <xref:System.Activities.Statements.Transition> ; as transições são criadas no designer de fluxo de trabalho arrastando e soltando uma linha entre dois Estados ou removendo um estado nos triângulos que aparecem quando um estado é focalizado sobre outro.</span><span class="sxs-lookup"><span data-stu-id="94823-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="94823-111">Para obter mais informações, consulte o [Designer de atividade de transição](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="94823-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94823-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="94823-112">See also</span></span>

- [<span data-ttu-id="94823-113">Guia de introdução ao tutorial</span><span class="sxs-lookup"><span data-stu-id="94823-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
