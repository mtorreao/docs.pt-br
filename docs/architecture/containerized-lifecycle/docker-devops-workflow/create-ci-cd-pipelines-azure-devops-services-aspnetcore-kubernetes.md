---
title: Criar pipelines de CI/CD no Azure DevOps Services para um aplicativo .NET em contêineres e implantar em um cluster kubernetes
description: Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Ciclo de vida de aplicativo do Docker em contêineres com a plataforma e as ferramentas da Microsoft)
ms.date: 01/06/2021
ms.openlocfilehash: ef994f132716547ee402237016ee71013528d779
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970480"
---
# <a name="create-cicd-pipelines-in-azure-devops-services-for-a-net-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="f7373-103">Criar pipelines de CI/CD no Azure DevOps Services para um aplicativo .NET em contêineres e implantar em um cluster kubernetes</span><span class="sxs-lookup"><span data-stu-id="f7373-103">Create CI/CD pipelines in Azure DevOps Services for a .NET application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="f7373-104">Na Figura 5-12, você pode ver o cenário de DevOps de ponta a ponta, que abrange o gerenciamento de código, a compilação de código, o build de imagens do Docker, o push de imagens do Docker para um registro de Docker e, por fim, a implantação em um cluster do Kubernetes no Azure.</span><span class="sxs-lookup"><span data-stu-id="f7373-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![Fluxo de trabalho: inicia no computador de desenvolvimento.](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="f7373-107">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="f7373-107">**Figure 5-12**.</span></span> <span data-ttu-id="f7373-108">Cenário de CI/CD criando imagens do Docker e implantando em um cluster do Kubernetes no Azure</span><span class="sxs-lookup"><span data-stu-id="f7373-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="f7373-109">É importante destacar que os dois pipelines, build/CI e lançamento/CD, são conectados por meio do Registro do Docker (como o Docker Hub ou o Registro de Contêiner do Azure).</span><span class="sxs-lookup"><span data-stu-id="f7373-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="f7373-110">O registro do Docker é uma das principais diferenças em comparação com um processo de CI/CD tradicional sem o Docker.</span><span class="sxs-lookup"><span data-stu-id="f7373-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="f7373-111">Conforme mostrado na Figura 5-13, a primeira fase é o pipeline de build/CI.</span><span class="sxs-lookup"><span data-stu-id="f7373-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="f7373-112">No Azure DevOps Services, você pode criar pipelines de build/CI que compilarão o código, criar as imagens do Docker e efetuar push delas para um Registro do Docker, como o Docker Hub ou o Registro de Contêiner do Azure.</span><span class="sxs-lookup"><span data-stu-id="f7373-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Modo de exibição de navegador do Azure DevOps, com a definição da tarefa do processo de build.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="f7373-114">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="f7373-114">**Figure 5-13**.</span></span> <span data-ttu-id="f7373-115">Pipeline de build/CI no Azure DevOps, compilando imagens do Docker e enviando as imagens por push a um registro do Docker</span><span class="sxs-lookup"><span data-stu-id="f7373-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="f7373-116">A segunda fase é criar um pipeline de implantação/lançamento.</span><span class="sxs-lookup"><span data-stu-id="f7373-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="f7373-117">No Azure DevOps Services, você pode criar facilmente um pipeline de implantação direcionado a um cluster do Kubernetes usando as tarefas do Kubernetes para Azure DevOps Services, conforme mostrado na Figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="f7373-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Modo de exibição de navegador do Azure DevOps, com a definição da tarefa de implantação no Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="f7373-119">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="f7373-119">**Figure 5-14**.</span></span> <span data-ttu-id="f7373-120">Pipeline de lançamento/CD na implantação do Azure DevOps Services em um cluster do Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f7373-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> <span data-ttu-id="f7373-121">[!Instruções passo a passo] Implantando eShopModernized no Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="f7373-121">[!Walkthrough] Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="f7373-122">Para obter uma explicação detalhada dos pipelines de CI/CD do Azure DevOps implantados no Kubernetes, consulte esta postagem: </span><span class="sxs-lookup"><span data-stu-id="f7373-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: </span></span>\
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="f7373-123">[Anterior](docker-application-outer-loop-devops-workflow.md) 
> [Avançar](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="f7373-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
