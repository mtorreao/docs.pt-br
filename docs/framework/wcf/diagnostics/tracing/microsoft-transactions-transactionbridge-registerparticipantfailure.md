---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252017"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="d9016-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="d9016-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="d9016-103">Falha do serviço de protocolo WS-AT ao registrar um participante para um protocolo de controle.</span><span class="sxs-lookup"><span data-stu-id="d9016-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9016-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9016-104">Description</span></span>  

 <span data-ttu-id="d9016-105">Rastreado se o MSDTC detectar uma solicitação de registro inválida.</span><span class="sxs-lookup"><span data-stu-id="d9016-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="d9016-106">Isso pode ser causado por várias solicitações de registro de conclusão e erros internos.</span><span class="sxs-lookup"><span data-stu-id="d9016-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d9016-107">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="d9016-107">Troubleshooting</span></span>  

 <span data-ttu-id="d9016-108">Não tente se registrar para conclusão mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="d9016-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="d9016-109">Além disso, inspecione a cadeia de caracteres de status na mensagem de rastreamento para determinar se existe algum item acionável.</span><span class="sxs-lookup"><span data-stu-id="d9016-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9016-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="d9016-110">See also</span></span>

- [<span data-ttu-id="d9016-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="d9016-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="d9016-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="d9016-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d9016-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d9016-113">Administration and Diagnostics</span></span>](../index.md)
