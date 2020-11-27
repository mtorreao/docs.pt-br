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
# <a name="state-machine-activities-in-wf"></a>Atividades do computador de estado em WF

O .NET Framework 4,5 fornece várias atividades fornecidas pelo sistema e designers de atividade para a criação de fluxos de trabalho de máquina de estado.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Executes continha atividades usando o paradigma familiar do computador de estado.|  
|<xref:System.Activities.Statements.State>|Representa um estado em uma máquina de estado.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa um estado de terminação em um computador de estado. <xref:System.Activities.Core.Presentation.FinalState> é um designer de atividade que quando usado criar <xref:System.Activities.Statements.State> pré-configurado como um estado de terminação. Para obter mais informações, consulte o [Designer de atividade FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Representa a transição entre dois estados. Não há nenhum item de **caixa de ferramentas** para <xref:System.Activities.Statements.Transition> ; as transições são criadas no designer de fluxo de trabalho arrastando e soltando uma linha entre dois Estados ou removendo um estado nos triângulos que aparecem quando um estado é focalizado sobre outro. Para obter mais informações, consulte o [Designer de atividade de transição](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Veja também

- [Guia de introdução ao tutorial](getting-started-tutorial.md)
