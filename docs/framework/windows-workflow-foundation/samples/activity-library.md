---
title: Biblioteca de Atividades
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 1a0c289315d7181645573098916788f18493abb8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245685"
---
# <a name="activity-library"></a>Biblioteca de Atividades

Esta seção contém exemplos que demonstram atividades personalizadas avançadas no Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>Nesta seção

 [Atividade personalizado de SendMail](sendmail-custom-activity.md)  
 Demonstra como criar uma atividade personalizada que derive de <xref:System.Activities.AsyncCodeActivity> para enviar email SMTP usando para uso em um aplicativo de fluxo de trabalho.  
  
 [Paralelo estrangulado ForEach](throttled-parallel-foreach.md)  
 Demonstra como atividade de `ThrottleParallelForEach` é semelhante à atividade de <xref:System.Activities.Statements.ParallelForEach%601> com uma exceção que permite que define um fator de simultaneidade para restringir o número de ramificações simultâneas para executar.
  
 [Atividades de acesso a base de dados](database-access-activities.md)  
 Demonstra como criar atividades que permitem o acesso a bancos de dados para recuperar ou modificar informações e usar o [ADO.net](../../data/adonet/index.md) para acessar o Database.  
  
 [Atividade exteriorizada de política no .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Demonstra como a atividade ExternalizedPolicy4 permite a execução de Windows Workflow Foundation existentes nos objetos .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> no Windows Workflow Foundation no [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) diretamente usando o mecanismo de regras que é enviado no WF 3,5.
  
 [ForEach não genéricos](non-generic-foreach.md)  
 Demonstra como criar uma versão não genérico de atividade de <xref:System.Activities.Statements.ForEach%601> .  
  
 [ParallelForEach não genérico](non-generic-parallelforeach.md)  
 Demonstra como criar uma versão não genérico de atividade de <xref:System.Activities.Statements.ParallelForEach%601> .  
  
 [Obter WorkflowInstanceId](get-workflowinstanceid.md)  
 Demonstra como usar a atividade personalizado, `GetWorkflowInstanceId`, para retornar a identificação de instância de fluxo de trabalho
