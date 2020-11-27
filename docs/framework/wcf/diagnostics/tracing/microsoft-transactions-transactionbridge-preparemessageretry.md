---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: d5ebe3e1ccce7a85073e2de19d915d116f709b2d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286962"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="05059-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="05059-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>

<span data-ttu-id="05059-103">Uma repetição de mensagem de preparação foi enviada a um participante sem resposta.</span><span class="sxs-lookup"><span data-stu-id="05059-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="05059-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="05059-104">Description</span></span>  

 <span data-ttu-id="05059-105">Rastreado se o Gerenciador de transações local precisar reenviar uma mensagem de preparação a um participante subordinado, pois ele não recebeu uma resposta em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="05059-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="05059-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="05059-106">Troubleshooting</span></span>  

 <span data-ttu-id="05059-107">Investigue possíveis problemas de rede ou de produtos que impedem que a resposta seja entregue no prazo.</span><span class="sxs-lookup"><span data-stu-id="05059-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="05059-108">Se muitas dessas mensagens forem vistas, isso poderá indicar problemas de infraestrutura ou tempos de resposta muito longos.</span><span class="sxs-lookup"><span data-stu-id="05059-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="05059-109">Ambos os problemas podem reduzir drasticamente a taxa de transferência de transações no sistema.</span><span class="sxs-lookup"><span data-stu-id="05059-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05059-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="05059-110">See also</span></span>

- [<span data-ttu-id="05059-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="05059-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="05059-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="05059-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="05059-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="05059-113">Administration and Diagnostics</span></span>](../index.md)
