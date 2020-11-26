---
title: 'Serviço: falhas de autenticação e validação de segurança por segundo'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: f66e6b90622cf181229938bc4fd877a98cd23a48
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236878"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="20f20-102">Serviço: falhas de autenticação e validação de segurança por segundo</span><span class="sxs-lookup"><span data-stu-id="20f20-102">Service: Security Validation and Authentication Failures Per Second</span></span>

<span data-ttu-id="20f20-103">Nome do contador: falhas de validação e autenticação de segurança por segundo.</span><span class="sxs-lookup"><span data-stu-id="20f20-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="20f20-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="20f20-104">Description</span></span>  

 <span data-ttu-id="20f20-105">Esse contador é incrementado sempre que uma mensagem é rejeitada devido a um problema de segurança não coberto pelo contador "chamadas de segurança não autorizadas".</span><span class="sxs-lookup"><span data-stu-id="20f20-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="20f20-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="20f20-106">Such problems include:</span></span>  
  
- <span data-ttu-id="20f20-107">O token do cliente não pode ser lido a partir da mensagem.</span><span class="sxs-lookup"><span data-stu-id="20f20-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="20f20-108">Falha na autenticação do token do cliente (por exemplo, senha inadequada).</span><span class="sxs-lookup"><span data-stu-id="20f20-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="20f20-109">Falha na verificação da assinatura (por exemplo, a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="20f20-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="20f20-110">A mensagem é uma duplicata de uma anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="20f20-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="20f20-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="20f20-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="20f20-112">Alguns elementos necessários (por exemplo, carimbo de data/hora ausente ou bloco de dados criptografados) estão ausentes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="20f20-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="20f20-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="20f20-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="20f20-114">Este contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), cujo valor é calculado usando a fórmula a seguir,</span><span class="sxs-lookup"><span data-stu-id="20f20-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="20f20-115">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="20f20-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
