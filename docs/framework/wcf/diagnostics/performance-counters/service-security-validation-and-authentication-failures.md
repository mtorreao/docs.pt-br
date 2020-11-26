---
title: 'Serviço: falhas de autenticação e validação de segurança'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: d89419d7d579d29a1c57370d61eefb8b26333a40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236852"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="fcad8-102">Serviço: falhas de autenticação e validação de segurança</span><span class="sxs-lookup"><span data-stu-id="fcad8-102">Service: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="fcad8-103">Nome do contador: falhas de validação e autenticação de segurança</span><span class="sxs-lookup"><span data-stu-id="fcad8-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="fcad8-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcad8-104">Description</span></span>  

 <span data-ttu-id="fcad8-105">Esse contador é incrementado sempre que uma mensagem é rejeitada devido a um problema de segurança não coberto pelo contador "chamadas de segurança não autorizadas".</span><span class="sxs-lookup"><span data-stu-id="fcad8-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="fcad8-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="fcad8-106">Such problems include:</span></span>  
  
- <span data-ttu-id="fcad8-107">O token do cliente não pode ser lido a partir da mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcad8-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="fcad8-108">Falha na autenticação do token do cliente (por exemplo, senha inadequada).</span><span class="sxs-lookup"><span data-stu-id="fcad8-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="fcad8-109">Falha na verificação da assinatura (por exemplo, a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="fcad8-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="fcad8-110">A mensagem é uma duplicata de uma anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="fcad8-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="fcad8-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="fcad8-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="fcad8-112">Alguns elementos necessários (por exemplo, carimbo de data/hora ausente ou bloco de dados criptografados) estão ausentes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="fcad8-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="fcad8-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="fcad8-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
