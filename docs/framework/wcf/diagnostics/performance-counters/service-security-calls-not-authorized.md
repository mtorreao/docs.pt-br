---
title: 'Serviço: chamadas de segurança não autorizadas'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: 32b0a62ecf9364270f5580787b7e129af5ac80b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236904"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="c7c26-102">Serviço: chamadas de segurança não autorizadas</span><span class="sxs-lookup"><span data-stu-id="c7c26-102">Service: Security Calls Not Authorized</span></span>

<span data-ttu-id="c7c26-103">Nome do contador: chamadas de segurança não autorizadas.</span><span class="sxs-lookup"><span data-stu-id="c7c26-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7c26-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="c7c26-104">Description</span></span>  

 <span data-ttu-id="c7c26-105">Esse contador é incrementado quando o <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> método retorna `false` .</span><span class="sxs-lookup"><span data-stu-id="c7c26-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="c7c26-106">Isso indica que a mensagem de entrada é de um usuário válido e protegida corretamente, mas o usuário não está autorizado a realizar tarefas específicas.</span><span class="sxs-lookup"><span data-stu-id="c7c26-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
