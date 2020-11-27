---
title: 'Ponto de extremidade: falhas de autenticação e validação de segurança'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: a9a4758b26c744c55af200aee22a7e90c5a5cf57
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256463"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="6359d-102">Ponto de extremidade: falhas de autenticação e validação de segurança</span><span class="sxs-lookup"><span data-stu-id="6359d-102">Endpoint: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="6359d-103">Nome do contador: falhas de validação e autenticação de segurança</span><span class="sxs-lookup"><span data-stu-id="6359d-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="6359d-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="6359d-104">Description</span></span>  

 <span data-ttu-id="6359d-105">Esse contador é incrementado sempre que uma mensagem é rejeitada devido a um problema de segurança não coberto pelo contador "chamadas de segurança não autorizadas".</span><span class="sxs-lookup"><span data-stu-id="6359d-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="6359d-106">Esses problemas incluem:</span><span class="sxs-lookup"><span data-stu-id="6359d-106">Such problems include:</span></span>  
  
- <span data-ttu-id="6359d-107">O token do cliente não pode ser lido a partir da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6359d-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="6359d-108">Falha na autenticação do token do cliente (senha inadequada).</span><span class="sxs-lookup"><span data-stu-id="6359d-108">Client token has failed authentication (bad password).</span></span>  
  
- <span data-ttu-id="6359d-109">Falha na verificação da assinatura (a mensagem foi violada).</span><span class="sxs-lookup"><span data-stu-id="6359d-109">Signature verification has failed (the message has been tampered).</span></span>  
  
- <span data-ttu-id="6359d-110">A mensagem é uma duplicata de uma anterior, o que pode ocorrer durante um ataque de repetição.</span><span class="sxs-lookup"><span data-stu-id="6359d-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="6359d-111">Ocorreu uma falha de descriptografia.</span><span class="sxs-lookup"><span data-stu-id="6359d-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="6359d-112">Alguns elementos necessários (carimbo de data/hora ausente ou bloco de dados criptografados) estão ausentes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6359d-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="6359d-113">Ocorreram erros durante o handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="6359d-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
