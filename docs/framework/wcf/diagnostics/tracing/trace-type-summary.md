---
title: Resumo de tipo de rastreamento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259239"
---
# <a name="trace-type-summary"></a>Resumo de tipo de rastreamento

[Os níveis de origem](xref:System.Diagnostics.SourceLevels) definem vários níveis de rastreamento: crítico, erro, aviso, informações e detalhados, além de fornecer uma descrição do `ActivityTracing` sinalizador, que alterna a saída dos eventos de limite de rastreamento e de transferência de atividade.  
  
 Você também pode examinar <xref:System.Diagnostics.TraceEventType> os tipos de rastreamentos que podem ser emitidos <xref:System.Diagnostics> .  
  
 A tabela a seguir lista os mais importantes.  
  
|Tipo de rastreamento|Descrição|  
|----------------|-----------------|  
|Crítico|Erro fatal ou falha do aplicativo.|  
|Erro do|Erro recuperável.|  
|Aviso|Mensagem informativa.|  
|Informações do|Problema não crítico.|  
|Detalhado|Rastreamento de depuração.|  
|Inicie o|Início de uma unidade lógica de processamento.|  
|Suspend|Suspensão de uma unidade lógica de processamento.|  
|Retomar|Retomada de uma unidade lógica de processamento.|  
|Parar|Interrupção de uma unidade lógica de processamento.|  
|Transferência|Alteração da identidade de correlação.|  
  
 Uma atividade é definida como uma combinação dos tipos de rastreamento acima.  
  
 Veja a seguir uma expressão regular que define uma atividade ideal em um escopo local (origem do rastreamento),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Isso significa que uma atividade deve atender às condições a seguir.  
  
- Ele deve iniciar e parar respectivamente por um rastreamento de iniciar e parar  
  
- Ele deve ter um rastreamento de transferência imediatamente antes de um rastreamento de suspensão ou retomada  
  
- Ele não deve ter nenhum rastreamento entre os rastreamentos suspender e retomar se esses rastreamentos existirem  
  
- Ele pode ter qualquer e quantos rastreamentos crítico/erro/aviso/informações/detalhados/de transferência, desde que as condições anteriores sejam observadas  
  
 Veja a seguir uma expressão regular que define uma atividade ideal no escopo global,  
  
`R+`  
  
 o R é a expressão regular para uma atividade no escopo local. Isso se traduz em,  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
