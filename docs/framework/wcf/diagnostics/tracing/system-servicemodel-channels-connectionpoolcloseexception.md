---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: d8edb8e916578247e62e3a3eb3b11b80f93416cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286949"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="ea9b3-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="ea9b3-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>

<span data-ttu-id="ea9b3-103">Ocorreu uma exceção ao fechar as conexões nesse pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="ea9b3-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ea9b3-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="ea9b3-104">Description</span></span>  

 <span data-ttu-id="ea9b3-105">Esse rastreamento de nível de erro indica que ocorreu um erro ao fechar os pools de conexão usados pelo recurso de pool de conexões do Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ea9b3-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="ea9b3-106">Um motivo possível para isso é um fechamento malsucedido de uma conexão em pool ou um conjunto de conexões em pool dentro do CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="ea9b3-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="ea9b3-107">Quando essa exceção é lançada, todas as conexões não fechadas restantes dentro desse pool são anuladas; as conexões não fechadas em outros pools são abandonadas.</span><span class="sxs-lookup"><span data-stu-id="ea9b3-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9b3-108">Veja também</span><span class="sxs-lookup"><span data-stu-id="ea9b3-108">See also</span></span>

- [<span data-ttu-id="ea9b3-109">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="ea9b3-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="ea9b3-110">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="ea9b3-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ea9b3-111">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ea9b3-111">Administration and Diagnostics</span></span>](../index.md)
