---
title: Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Ciclo de vida de aplicativo do Docker em contêineres com a plataforma e as ferramentas da Microsoft)
description: Obtenha uma visão geral de alto nível do processo de desenvolvimento e implantação para desenvolver e implantar aplicativos em contêineres com o Docker e a plataforma e as ferramentas da Microsoft.
ms.date: 01/06/2021
ms.openlocfilehash: 94c277e349bacee9b9fc7b160043005dd4135958
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970109"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="b143a-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Ciclo de vida de aplicativo do Docker em contêineres com a plataforma e as ferramentas da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="b143a-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Capa do livro](./media/devops-book-cover-large-we.png)

<span data-ttu-id="b143a-105">**Edição v 5.0** -atualizado para ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="b143a-105">**EDITION v5.0** - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="b143a-106">Consulte o [changelog](https://aka.ms/DockerLifecycleEbookChangelog) para obter as atualizações do livro e as contribuições da Comunidade.</span><span class="sxs-lookup"><span data-stu-id="b143a-106">Refer [changelog](https://aka.ms/DockerLifecycleEbookChangelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="b143a-107">Este guia é uma visão geral para desenvolver e implantar aplicativos ASP.NET Core em contêineres com o Docker, usando a plataforma e as ferramentas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b143a-107">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="b143a-108">O guia inclui uma introdução de alto nível ao Azure DevOps, para implementar pipelines de CI/CD, bem como o ACR (registro de contêiner do Azure) e os serviços Kubernetess do Azure AKS para implantação.</span><span class="sxs-lookup"><span data-stu-id="b143a-108">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="b143a-109">Para obter detalhes relacionados ao desenvolvimento de baixo nível, você pode ver o guia [microservices do .net: arquitetura para aplicativos em contêineres .net](../microservices/index.md) e o aplicativo de referência relacionado [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="b143a-109">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="b143a-110">Envie-nos seus comentários!</span><span class="sxs-lookup"><span data-stu-id="b143a-110">Send us your feedback!</span></span>

<span data-ttu-id="b143a-111">Escrevemos este guia para ajudá-lo a entender a arquitetura de aplicativos em contêineres e de microsserviços no .NET.</span><span class="sxs-lookup"><span data-stu-id="b143a-111">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="b143a-112">O guia e o aplicativo de referência relacionado continuarão sendo desenvolvidos, portanto seus comentários são bem-vindos!</span><span class="sxs-lookup"><span data-stu-id="b143a-112">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="b143a-113">Se você tiver comentários sobre como esse guia pode ser melhorado, envie comentários em <https://aka.ms/ebookfeedback> .</span><span class="sxs-lookup"><span data-stu-id="b143a-113">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="b143a-114">Credits</span><span class="sxs-lookup"><span data-stu-id="b143a-114">Credits</span></span>

<span data-ttu-id="b143a-115">Autor:</span><span class="sxs-lookup"><span data-stu-id="b143a-115">Author:</span></span>

> <span data-ttu-id="b143a-116">**Cesar de la Torre**, Gerente sênior de produtos , equipe de produto do .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="b143a-116">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="b143a-117">Editor de aquisições:</span><span class="sxs-lookup"><span data-stu-id="b143a-117">Acquisitions Editor:</span></span>

> <span data-ttu-id="b143a-118">**Janine Patrick**</span><span class="sxs-lookup"><span data-stu-id="b143a-118">**Janine Patrick**</span></span>

<span data-ttu-id="b143a-119">Editor de desenvolvimento:</span><span class="sxs-lookup"><span data-stu-id="b143a-119">Developmental Editor:</span></span>

> <span data-ttu-id="b143a-120">**Bob Russell**, profissional de soluções na Microsoft</span><span class="sxs-lookup"><span data-stu-id="b143a-120">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="b143a-121">**Publicação octal, Inc.**</span><span class="sxs-lookup"><span data-stu-id="b143a-121">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="b143a-122">Produção editorial:</span><span class="sxs-lookup"><span data-stu-id="b143a-122">Editorial Production:</span></span>

> [<span data-ttu-id="b143a-123">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="b143a-123">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="b143a-124">**Publicação octal, Inc.**</span><span class="sxs-lookup"><span data-stu-id="b143a-124">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="b143a-125">Copyeditor:</span><span class="sxs-lookup"><span data-stu-id="b143a-125">Copyeditor:</span></span>

> <span data-ttu-id="b143a-126">**Bob Russell**, profissional de soluções na Microsoft</span><span class="sxs-lookup"><span data-stu-id="b143a-126">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="b143a-127">Participantes e revisores:</span><span class="sxs-lookup"><span data-stu-id="b143a-127">Participants and reviewers:</span></span>

> <span data-ttu-id="b143a-128">**Nish Anil**, Gerente de Programa Sênior, Equipe .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="b143a-128">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="b143a-129">**Miguel Veloso**, engenheiro de desenvolvimento de software em conceitos simples</span><span class="sxs-lookup"><span data-stu-id="b143a-129">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="b143a-130">**Pedro Ghosh**, consultor principal da Neudesic</span><span class="sxs-lookup"><span data-stu-id="b143a-130">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="b143a-131">Direitos autorais</span><span class="sxs-lookup"><span data-stu-id="b143a-131">Copyright</span></span>

<span data-ttu-id="b143a-132">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="b143a-132">PUBLISHED BY</span></span>

<span data-ttu-id="b143a-133">Divisão de Desenvolvedores Microsoft, equipes dos produtos .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b143a-133">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="b143a-134">Uma divisão da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="b143a-134">A division of Microsoft Corporation</span></span>

<span data-ttu-id="b143a-135">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="b143a-135">One Microsoft Way</span></span>

<span data-ttu-id="b143a-136">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="b143a-136">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="b143a-137">Copyright &copy; 2021 da Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="b143a-137">Copyright &copy; 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="b143a-138">Todos os direitos reservados.</span><span class="sxs-lookup"><span data-stu-id="b143a-138">All rights reserved.</span></span> <span data-ttu-id="b143a-139">Nenhuma parte do conteúdo deste guia pode ser reproduzida ou transmitida de nenhuma forma nem por nenhum meio sem a permissão por escrito do publicador.</span><span class="sxs-lookup"><span data-stu-id="b143a-139">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="b143a-140">Este livro é fornecido “no estado em que se encontra” e expressa os pontos de vista e as opiniões do autor.</span><span class="sxs-lookup"><span data-stu-id="b143a-140">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="b143a-141">Os pontos de vista, as opiniões e as informações expressos neste guia, incluindo URLs e outras referências a sites da Internet, podem ser alteradas sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="b143a-141">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="b143a-142"> Alguns exemplos aqui representados são fornecidos somente para fins de ilustração e são fictícios.</span><span class="sxs-lookup"><span data-stu-id="b143a-142">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="b143a-143">Nenhuma associação ou conexão real é intencional ou deve ser inferida.</span><span class="sxs-lookup"><span data-stu-id="b143a-143">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="b143a-144">A Microsoft e as marcas listadas em <https://www.microsoft.com> na página da Web "Marcas" são marcas comerciais do grupo de empresas Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b143a-144">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="b143a-145">Mac e macOS são marcas comerciais da Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="b143a-145">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="b143a-146">O logotipo de redistribuição do Docker é uma marca registrada do Docker, Inc. usada pela permissão.</span><span class="sxs-lookup"><span data-stu-id="b143a-146">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="b143a-147">Todas as outras marcas e logotipos são propriedade de seus respectivos proprietários.</span><span class="sxs-lookup"><span data-stu-id="b143a-147">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="b143a-148">Próximo</span><span class="sxs-lookup"><span data-stu-id="b143a-148">Next</span></span>](introduction-to-containers-and-docker.md)
