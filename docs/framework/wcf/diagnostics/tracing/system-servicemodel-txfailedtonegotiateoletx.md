---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 7b468a57409e9a473a5bbf8e3324435e65e8c60b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295308"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="e965f-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="e965f-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>

<span data-ttu-id="e965f-103">A negociação do protocolo OleTransactions não pôde ser concluída para o contexto de coordenação especificado.</span><span class="sxs-lookup"><span data-stu-id="e965f-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e965f-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="e965f-104">Description</span></span>  

 <span data-ttu-id="e965f-105">Rastreado quando uma transação de entrada com informações de OleTx não é capaz de usar as informações de OleTx anexadas e voltará a usar WS-AT em vez disso.</span><span class="sxs-lookup"><span data-stu-id="e965f-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e965f-106">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="e965f-106">Troubleshooting</span></span>  

 <span data-ttu-id="e965f-107">Indica um possível problema com a comunicação de RPC do MSDTC entre os computadores.</span><span class="sxs-lookup"><span data-stu-id="e965f-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="e965f-108">Se muitos desses rastreamentos aparecerem no log, uma diminuição drástica no desempenho poderá resultar.</span><span class="sxs-lookup"><span data-stu-id="e965f-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="e965f-109">Se OleTx não for desejado, defina `OleTxUpgradeEnabled` como 0 na configuração do registro WS-AT.</span><span class="sxs-lookup"><span data-stu-id="e965f-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e965f-110">Veja também</span><span class="sxs-lookup"><span data-stu-id="e965f-110">See also</span></span>

- [<span data-ttu-id="e965f-111">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="e965f-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e965f-112">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="e965f-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e965f-113">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e965f-113">Administration and Diagnostics</span></span>](../index.md)
