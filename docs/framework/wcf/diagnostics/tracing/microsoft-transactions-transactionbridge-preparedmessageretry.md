---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: edab153123ae48702811532df3b5b5bf0849c26a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275912"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="6f627-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="6f627-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>

<span data-ttu-id="6f627-103">Uma nova tentativa de mensagem preparada foi enviada a um coordenador sem resposta.</span><span class="sxs-lookup"><span data-stu-id="6f627-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f627-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f627-104">Description</span></span>  

 <span data-ttu-id="6f627-105">Rastreado se o Gerenciador de transações local precisar reenviar uma mensagem preparada para um coordenador superior porque ele não recebeu uma resposta em um determinado período/</span><span class="sxs-lookup"><span data-stu-id="6f627-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6f627-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6f627-106">Troubleshooting</span></span>  

 <span data-ttu-id="6f627-107">Investigue possíveis problemas de rede ou de produtos que impedem que a resposta seja entregue no prazo.</span><span class="sxs-lookup"><span data-stu-id="6f627-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="6f627-108">Se muitas dessas mensagens forem vistas, isso poderá indicar problemas de infraestrutura ou tempos de resposta muito longos.</span><span class="sxs-lookup"><span data-stu-id="6f627-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="6f627-109">Os dois problemas reduzem drasticamente a taxa de transferência das transações no sistema.</span><span class="sxs-lookup"><span data-stu-id="6f627-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f627-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="6f627-110">See also</span></span>

- [<span data-ttu-id="6f627-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="6f627-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="6f627-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="6f627-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6f627-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6f627-113">Administration and Diagnostics</span></span>](../index.md)
