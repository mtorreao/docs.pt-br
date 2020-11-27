---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: bd6c9124e6346437e2bb35df620e00bad13b60f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258940"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="303a7-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="303a7-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="303a7-103">A máquina de estado para uma inscrição de participante entrou no estado concluído.</span><span class="sxs-lookup"><span data-stu-id="303a7-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="303a7-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="303a7-104">Description</span></span>  

 <span data-ttu-id="303a7-105">Rastreado quando uma inscrição de participante subordinado concluiu o processamento de 2pc.</span><span class="sxs-lookup"><span data-stu-id="303a7-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="303a7-106">O resultado da inscrição pode ser confirmado ou anulado.</span><span class="sxs-lookup"><span data-stu-id="303a7-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="303a7-107">Ele também será rastreado se qualquer participante votar em ReadOnly durante a preparação.</span><span class="sxs-lookup"><span data-stu-id="303a7-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303a7-108">Veja também</span><span class="sxs-lookup"><span data-stu-id="303a7-108">See also</span></span>

- [<span data-ttu-id="303a7-109">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="303a7-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="303a7-110">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="303a7-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="303a7-111">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="303a7-111">Administration and Diagnostics</span></span>](../index.md)
