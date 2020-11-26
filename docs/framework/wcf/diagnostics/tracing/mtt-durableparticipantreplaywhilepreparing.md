---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236605"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="5f31a-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="5f31a-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="5f31a-103">O serviço de protocolo WS-AT recebeu uma mensagem de reprodução de um participante durável, que não respondeu à preparação.</span><span class="sxs-lookup"><span data-stu-id="5f31a-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="5f31a-104">Consequentemente, a transação foi anulada.</span><span class="sxs-lookup"><span data-stu-id="5f31a-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5f31a-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f31a-105">Description</span></span>  

 <span data-ttu-id="5f31a-106">Rastreado se uma mensagem de reprodução for recebida enquanto um participante durável ainda estiver se preparando.</span><span class="sxs-lookup"><span data-stu-id="5f31a-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="5f31a-107">Esta é uma mensagem ilegal para esse Estado e a transação será anulada.</span><span class="sxs-lookup"><span data-stu-id="5f31a-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="5f31a-108">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="5f31a-108">Troubleshooting</span></span>

<span data-ttu-id="5f31a-109">Receber esse erro pode indicar que um participante durável (incluindo TransactionManagers subordinados) se recuperou de uma falha; no entanto, não há certeza do resultado da transação e solicita seu status.</span><span class="sxs-lookup"><span data-stu-id="5f31a-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f31a-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="5f31a-110">See also</span></span>

- [<span data-ttu-id="5f31a-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="5f31a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="5f31a-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="5f31a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5f31a-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5f31a-113">Administration and Diagnostics</span></span>](../index.md)
