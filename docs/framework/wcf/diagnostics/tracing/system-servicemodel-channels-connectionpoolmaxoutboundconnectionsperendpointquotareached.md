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
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="2c0ea-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="2c0ea-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>

<span data-ttu-id="2c0ea-103">Falha do serviço de protocolo WS-AT ao inscrever-se em uma transação usando o contexto de coordenação fornecido.</span><span class="sxs-lookup"><span data-stu-id="2c0ea-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2c0ea-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="2c0ea-104">Description</span></span>  

 <span data-ttu-id="2c0ea-105">Rastreado quando o MSDTC não pode se inscrever em uma transação para um determinado protocolo 2PC.</span><span class="sxs-lookup"><span data-stu-id="2c0ea-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="2c0ea-106">Isso pode acontecer porque a transação não existe mais, a lista de inlistagem não é mais permitida ou muitas inlistagens já estão presentes.</span><span class="sxs-lookup"><span data-stu-id="2c0ea-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2c0ea-107">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="2c0ea-107">Troubleshooting</span></span>  

 <span data-ttu-id="2c0ea-108">Inspecione a cadeia de caracteres de status na mensagem de rastreamento para determinar se existe algum item acionável.</span><span class="sxs-lookup"><span data-stu-id="2c0ea-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0ea-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="2c0ea-109">See also</span></span>

- [<span data-ttu-id="2c0ea-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="2c0ea-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="2c0ea-111">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="2c0ea-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2c0ea-112">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2c0ea-112">Administration and Diagnostics</span></span>](../index.md)
