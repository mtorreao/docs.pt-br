---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235110"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="b69ed-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b69ed-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="b69ed-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="b69ed-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="b69ed-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="b69ed-104">Description</span></span>  

 <span data-ttu-id="b69ed-105">Os threads foram alternados durante o processamento de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="b69ed-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="b69ed-106">O processamento de mensagens pode ser pausado pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="b69ed-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="b69ed-107">ConcurrencyMode é Single ou reentrante e o serviço está processando outra mensagem.</span><span class="sxs-lookup"><span data-stu-id="b69ed-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="b69ed-108">A transação está habilitada e o serviço está processando outra transação.</span><span class="sxs-lookup"><span data-stu-id="b69ed-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="b69ed-109">O contexto de sincronização não é atual.</span><span class="sxs-lookup"><span data-stu-id="b69ed-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69ed-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="b69ed-110">See also</span></span>

- [<span data-ttu-id="b69ed-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="b69ed-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="b69ed-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="b69ed-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b69ed-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b69ed-113">Administration and Diagnostics</span></span>](../index.md)
