---
title: Atividades em runtime de WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: b0472c669d69d9397843a004bee1bb2c15e139c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245687"
---
# <a name="runtime-activities-in-wf"></a>Atividades em runtime de WF

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] fornece vários sistema forneceu atividades acessando recursos de runtime de fluxo de trabalho, como a persistência e o encerramento.  
  
|Atividade|Descrição|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Solicita explicitamente que o fluxo de trabalho persiste seu estado.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Finaliza a instância em execução de fluxo de trabalho.|  
|<xref:System.Activities.Statements.NoPersistScope>|Uma atividade do contêiner que impede que as atividades filhos persistam.|
