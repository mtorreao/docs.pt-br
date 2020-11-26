---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9ad9dc9fd078f7ad4c0934c8bf9bb73feb935014
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236644"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="ac713-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="ac713-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>

<span data-ttu-id="ac713-103">O serviço de protocolo WS-AT recebeu uma mensagem preparada ou de reprodução de um participante volátil não reconhecido.</span><span class="sxs-lookup"><span data-stu-id="ac713-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="ac713-104">Uma falha foi retornada ao participante, declara que o resultado da transação está em dúvida.</span><span class="sxs-lookup"><span data-stu-id="ac713-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac713-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="ac713-105">Description</span></span>  

 <span data-ttu-id="ac713-106">Rastreado quando o Gerenciador de transações local recebe uma mensagem preparada ou Replay de uma inscrição volátil que ela já esqueceu.</span><span class="sxs-lookup"><span data-stu-id="ac713-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ac713-107">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="ac713-107">Troubleshooting</span></span>  

 <span data-ttu-id="ac713-108">Investigue as possíveis causas de mensagens tardias provenientes do participante volátil.</span><span class="sxs-lookup"><span data-stu-id="ac713-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac713-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="ac713-109">See also</span></span>

- [<span data-ttu-id="ac713-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="ac713-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="ac713-111">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac713-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ac713-112">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ac713-112">Administration and Diagnostics</span></span>](../index.md)
