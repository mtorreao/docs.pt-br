---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: d8abfe6e34439ccf399e37c1285b7b71cebf9870
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258030"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="4d260-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="4d260-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>

<span data-ttu-id="4d260-103">O handshake de segurança com um vizinho potencial não foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4d260-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4d260-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d260-104">Description</span></span>  

 <span data-ttu-id="4d260-105">Esse rastreamento ocorre durante a tentativa de estabelecer uma conexão de vizinho segura.</span><span class="sxs-lookup"><span data-stu-id="4d260-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="4d260-106">Isso pode ocorrer devido a credenciais insuficientes ou incorretas.</span><span class="sxs-lookup"><span data-stu-id="4d260-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="4d260-107">O PeerChannel reconhece um único tipo de token para certificados de identificação forte, X. 509, que fornecem um modelo de identidade forte baseado no tipo de autenticação e autorização que podem ser implementados.</span><span class="sxs-lookup"><span data-stu-id="4d260-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="4d260-108">O PeerChannel também oferece suporte a aplicativos simples por meio do uso de senhas.</span><span class="sxs-lookup"><span data-stu-id="4d260-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="4d260-109">As senhas só podem ser usadas para permitir a entrada na sessão; Eles não podem ser usados para executar a autenticação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4d260-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="4d260-110">Isso ocorre porque um token simétrico que um grupo de colegas compartilha é difícil e inadequado para a autenticação de origem.</span><span class="sxs-lookup"><span data-stu-id="4d260-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4d260-111">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="4d260-111">Troubleshooting</span></span>  

 <span data-ttu-id="4d260-112">Verifique se todos os vizinhos têm as credenciais de segurança apropriadas.</span><span class="sxs-lookup"><span data-stu-id="4d260-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d260-113">Veja também</span><span class="sxs-lookup"><span data-stu-id="4d260-113">See also</span></span>

- [<span data-ttu-id="4d260-114">Segurança de canal par</span><span class="sxs-lookup"><span data-stu-id="4d260-114">Peer Channel Security</span></span>](../../feature-details/peer-channel-security.md)
- [<span data-ttu-id="4d260-115">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="4d260-115">Tracing</span></span>](index.md)
- [<span data-ttu-id="4d260-116">Utilizando o rastreamento para solucionar problemas em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="4d260-116">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4d260-117">Administração e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4d260-117">Administration and Diagnostics</span></span>](../index.md)
