---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 3e4e1ff7ea8d8768c8d902dc09bd3b78646c2caf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256320"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure

Falha do serviço de protocolo WS-AT ao inscrever-se em uma transação usando o contexto de coordenação fornecido.  
  
## <a name="description"></a>Descrição  

 Rastreado quando o MSDTC não pode se inscrever em uma transação para um determinado protocolo 2PC.  Isso pode acontecer porque a transação não existe mais, a lista de inlistagem não é mais permitida ou muitas inlistagens já estão presentes.  
  
## <a name="troubleshooting"></a>Solução de problemas  

 Inspecione a cadeia de caracteres de status na mensagem de rastreamento para determinar se existe algum item acionável.  
  
## <a name="see-also"></a>Veja também

- [Rastreamento](index.md)
- [Utilizando o rastreamento para solucionar problemas em seu aplicativo](using-tracing-to-troubleshoot-your-application.md)
- [Administração e diagnóstico](../index.md)
