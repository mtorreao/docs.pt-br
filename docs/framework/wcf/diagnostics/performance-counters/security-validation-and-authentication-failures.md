---
title: Falhas de Validação e Autenticação de Segurança
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 3bcc6111f322a3bd8169567e8f436871eb19f879
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253044"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="c7c4a-102">Falhas de Validação e Autenticação de Segurança</span><span class="sxs-lookup"><span data-stu-id="c7c4a-102">Security Validation and Authentication Failures</span></span>

<span data-ttu-id="c7c4a-103">Nome do contador: falhas de validação e autenticação de segurança</span><span class="sxs-lookup"><span data-stu-id="c7c4a-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7c4a-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7c4a-104">Description</span></span>  

 <span data-ttu-id="c7c4a-105">Esse contador é incrementado sempre que uma mensagem é rejeitada devido a um problema de segurança não coberto pelo contador "chamadas de segurança não autorizadas".</span><span class="sxs-lookup"><span data-stu-id="c7c4a-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="c7c4a-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="c7c4a-106">Such problems include:</span></span>  
  
- <span data-ttu-id="c7c4a-107">O token do cliente não pode ser lido a partir da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="c7c4a-108">Falha na autenticação do token do cliente (por exemplo, senha inadequada).</span><span class="sxs-lookup"><span data-stu-id="c7c4a-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="c7c4a-109">Falha na verificação da assinatura (por exemplo, a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="c7c4a-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="c7c4a-110">A mensagem é uma duplicata de uma anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="c7c4a-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="c7c4a-112">Alguns elementos necessários (por exemplo, carimbo de data/hora ausente ou bloco de dados criptografados) estão ausentes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="c7c4a-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="c7c4a-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
