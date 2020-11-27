---
title: Implantando serviços
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 07bd2a3938f238336dc00fa2e0826a28a9363a4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294801"
---
# <a name="deploying-services"></a><span data-ttu-id="38bd1-102">Implantando serviços</span><span class="sxs-lookup"><span data-stu-id="38bd1-102">Deploying Services</span></span>

<span data-ttu-id="38bd1-103">Este tópico descreve como você pode implantar um aplicativo Windows Communication Foundation (WCF) em um ambiente de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="38bd1-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="38bd1-104">Escolhendo o ambiente de hospedagem para seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="38bd1-104">Choosing the Hosting Environment for Your Application</span></span>  

 <span data-ttu-id="38bd1-105">Os serviços WCF são projetados para serem executados em qualquer processo do Windows que ofereça suporte a código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="38bd1-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="38bd1-106">Para se tornar ativo, um serviço deve ser hospedado em um ambiente de tempo de execução que o cria e controla seu contexto e vida útil.</span><span class="sxs-lookup"><span data-stu-id="38bd1-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="38bd1-107">As opções de hospedagem variam da execução dentro do aplicativo de console mais simples para ambientes de servidor como um serviço do Windows, Serviços de Informações da Internet (IIS) ou dentro de um processo de trabalho gerenciado pelo WAS (serviço de ativação do Windows).</span><span class="sxs-lookup"><span data-stu-id="38bd1-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="38bd1-108">Para examinar as diferentes opções de hospedagem para seu aplicativo WCF, consulte [serviços de hospedagem](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="38bd1-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38bd1-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="38bd1-109">See also</span></span>

- [<span data-ttu-id="38bd1-110">Hosting</span><span class="sxs-lookup"><span data-stu-id="38bd1-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="38bd1-111">Serviços de hospedagem</span><span class="sxs-lookup"><span data-stu-id="38bd1-111">Hosting Services</span></span>](../hosting-services.md)
