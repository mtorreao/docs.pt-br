---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f7b3ca5e049adbb773cb6a3054de0a1520300586
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291733"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="f0c26-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="f0c26-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>

<span data-ttu-id="f0c26-103">A transação especificada para a operação especificada foi concluída devido a anulação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="f0c26-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0c26-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0c26-104">Description</span></span>  

 <span data-ttu-id="f0c26-105">A transação atual foi anulada devido a outro participante aguardando anulação, tempos limite estão ocorrendo ou outro erro dentro do participante de uma transação.</span><span class="sxs-lookup"><span data-stu-id="f0c26-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f0c26-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f0c26-106">Troubleshooting</span></span>  

 <span data-ttu-id="f0c26-107">Se essa anulação for inesperada, verifique todos os logs do sistema para determinar o motivo real para a anulação.</span><span class="sxs-lookup"><span data-stu-id="f0c26-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c26-108">Veja também</span><span class="sxs-lookup"><span data-stu-id="f0c26-108">See also</span></span>

- [<span data-ttu-id="f0c26-109">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="f0c26-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="f0c26-110">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="f0c26-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f0c26-111">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f0c26-111">Administration and Diagnostics</span></span>](../index.md)
