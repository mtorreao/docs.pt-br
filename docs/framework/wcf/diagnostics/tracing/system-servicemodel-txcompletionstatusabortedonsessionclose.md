---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274316"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose

A transação especificada foi anulada porque estava incompleta quando a sessão foi fechada e o TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute foi definido como falso.  
  
## <a name="description"></a>Descrição  

 Rastreado se a sessão ativa atual foi fechada e a transação não foi concluída e a TransactionAutoCompleteOnSessionClose está definida como `false` .  
  
## <a name="troubleshooting"></a>Solução de problemas  

 Esse rastreamento indica um possível bug de aplicativo que deve ser investigado.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
