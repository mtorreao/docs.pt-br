---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: 97f22a01df84c39915f74fa7677e5dd18154b952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256216"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="c97e7-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="c97e7-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>

<span data-ttu-id="c97e7-103">Falha ao receber uma mensagem por um canal HTTP.</span><span class="sxs-lookup"><span data-stu-id="c97e7-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c97e7-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="c97e7-104">Description</span></span>  

 <span data-ttu-id="c97e7-105">Esse rastreamento pode ser emitido como um aviso ou um erro.</span><span class="sxs-lookup"><span data-stu-id="c97e7-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="c97e7-106">Em ambos os casos, o rastreamento é emitido quando um ouvinte compatível não é encontrado para uma solicitação HTTP de entrada e a solicitação HTTP é descartada.</span><span class="sxs-lookup"><span data-stu-id="c97e7-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="c97e7-107">Isso pode acontecer porque o verbo HTTP da solicitação não foi reconhecido por nenhum ouvinte HTTP ou porque nenhum ouvinte estava escutando no endereço para o qual a solicitação foi destinada.</span><span class="sxs-lookup"><span data-stu-id="c97e7-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="c97e7-108">O rastreamento é emitido como um aviso no caso hospedado automaticamente e como um erro quando o serviço é hospedado no IIS.</span><span class="sxs-lookup"><span data-stu-id="c97e7-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97e7-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="c97e7-109">See also</span></span>

- [<span data-ttu-id="c97e7-110">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="c97e7-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="c97e7-111">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="c97e7-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c97e7-112">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c97e7-112">Administration and Diagnostics</span></span>](../index.md)
