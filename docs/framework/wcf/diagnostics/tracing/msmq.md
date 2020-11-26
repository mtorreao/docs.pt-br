---
title: MSMQ
ms.date: 03/30/2017
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
ms.openlocfilehash: 7ef31a188e1564da47ea1e7323cdd4cd5ef5be60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236670"
---
# <a name="msmq"></a><span data-ttu-id="98532-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="98532-102">MSMQ</span></span>

<span data-ttu-id="98532-103">Em um aplicativo MSMQ, nenhuma atividade adicional é transferida do canal enfileirado para MSMQ e do MSMQ para o canal em fila.</span><span class="sxs-lookup"><span data-stu-id="98532-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="98532-104">Além disso, a ID da mensagem do MSMQ e a ID da mensagem SOAP (juntamente com a ID da atividade, se houver) são rastreadas como parte dos rastreamentos de canal na fila em uma operação de envio.</span><span class="sxs-lookup"><span data-stu-id="98532-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="98532-105">A ID da mensagem do MSMQ e a ID da mensagem SOAP (juntamente com a ID da atividade, se houver) são rastreadas como parte dos rastreamentos de canal na fila em uma operação de recebimento.</span><span class="sxs-lookup"><span data-stu-id="98532-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="98532-106">As transferências necessárias na operação de recebimento são executadas de forma semelhante a qualquer outro transporte (>de mensagens de processo de recebimento de bytes-> operação).</span><span class="sxs-lookup"><span data-stu-id="98532-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
