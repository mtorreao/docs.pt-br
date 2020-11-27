---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 28b83b293570adf3b1cfdc15c77afd0f0cf768eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259019"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="3cde0-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="3cde0-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>

<span data-ttu-id="3cde0-103">Uma nova tentativa de mensagem de confirmação foi enviada a um participante sem resposta.</span><span class="sxs-lookup"><span data-stu-id="3cde0-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3cde0-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="3cde0-104">Description</span></span>  

 <span data-ttu-id="3cde0-105">Rastreado se o Gerenciador de transações local precisar reenviar uma mensagem de confirmação para um participante subordinado porque ele não recebeu uma resposta em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3cde0-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3cde0-106">Troubleshooting</span></span>  

 <span data-ttu-id="3cde0-107">Investigue possíveis problemas de rede ou de produtos que impedem que a resposta seja entregue no prazo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="3cde0-108">Se muitas dessas mensagens forem vistas, isso poderá indicar problemas de infraestrutura ou tempos de resposta muito longos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="3cde0-109">Os dois problemas reduzem drasticamente a taxa de transferência das transações no sistema.</span><span class="sxs-lookup"><span data-stu-id="3cde0-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cde0-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="3cde0-110">See also</span></span>

- [<span data-ttu-id="3cde0-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="3cde0-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3cde0-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="3cde0-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3cde0-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="3cde0-113">Administration and Diagnostics</span></span>](../index.md)
