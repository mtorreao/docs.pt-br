---
title: Fluxo de trabalho de desenvolvimento do loop interno para aplicativos do Docker
description: Saiba mais sobre o fluxo de trabalho de desenvolvimento de "loop interno" para aplicativos do Docker.
ms.date: 01/06/2021
ms.openlocfilehash: 78c593890d56a6888d4c4ea6752497918222ebee
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970547"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="ba1e4-103">Fluxo de trabalho de desenvolvimento do loop interno para aplicativos do Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="ba1e4-104">Antes de disparar o fluxo de trabalho de loop externo que abrange todo o ciclo de DevOps, tudo começa no computador de cada desenvolvedor, codificando o aplicativo em si, usando suas linguagens ou plataformas preferenciais e testando localmente (Figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="ba1e4-105">Mas, em todos os casos, você terá um ponto importante em comum, independentemente da linguagem, da estrutura ou das plataformas escolhidas.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="ba1e4-106">Neste fluxo de trabalho específico, você está sempre desenvolvendo e testando contêineres do Docker em nenhum outro ambiente, mas localmente.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-106">In this specific workflow, you're always developing and testing Docker containers in no other environments, but locally.</span></span>

![Diagrama mostrando o conceito de um ambiente de desenvolvimento de loop interno.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="ba1e4-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-108">**Figure 4-21**.</span></span> <span data-ttu-id="ba1e4-109">Contexto de desenvolvimento do loop interno</span><span class="sxs-lookup"><span data-stu-id="ba1e4-109">Inner-loop development context</span></span>

<span data-ttu-id="ba1e4-110">O contêiner ou instância de uma imagem de Docker terá estes componentes:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="ba1e4-111">Uma seleção de sistema operacional (por exemplo, uma distribuição do Linux ou Windows)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="ba1e4-112">Arquivos adicionados pelo desenvolvedor (por exemplo, binários do aplicativo)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="ba1e4-113">Configuração (por exemplo, configurações de ambiente e dependências)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="ba1e4-114">Instruções sobre quais processos devem ser executados pelo Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="ba1e4-115">Você pode configurar o fluxo de trabalho de desenvolvimento do loop interno que utiliza o Docker como processo (descrito na próxima seção).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="ba1e4-116">Observe que as etapas iniciais para configurar o ambiente não estão incluídas, porque você só precisa fazer isso uma vez.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="ba1e4-117">Criando um único aplicativo dentro de um contêiner do Docker usando o Visual Studio Code e a CLI do Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="ba1e4-118">Aplicativos são compostos por seus próprios serviços e por bibliotecas adicionais (dependências).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="ba1e4-119">A Figura 4-22 mostra as etapas básicas que normalmente você precisaria executar ao criar um aplicativo do Docker, seguidas por descrições detalhadas de cada etapa.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Diagrama mostrando as sete etapas necessárias para criar um aplicativo em contêineres.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="ba1e4-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-121">**Figure 4-22**.</span></span> <span data-ttu-id="ba1e4-122">Fluxo de trabalho de alto nível do ciclo de vida de aplicativos em contêineres do Docker usando a CLI do Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="ba1e4-123">Etapa 1: iniciar a codificação em Visual Studio Code e criar sua linha de base de aplicativo/serviço inicial</span><span class="sxs-lookup"><span data-stu-id="ba1e4-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="ba1e4-124">A maneira como você desenvolve seu aplicativo é semelhante à maneira como o faz sem o Docker.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="ba1e4-125">A diferença é que, durante o desenvolvimento, você está implantando e testando o aplicativo ou os serviços em execução dentro de contêineres do Docker colocados no ambiente local (como uma VM Linux ou Windows).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="ba1e4-126">**Configurando o ambiente local**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-126">**Setting up your local environment**</span></span>

<span data-ttu-id="ba1e4-127">Com as versões mais recentes do Docker desktop para Mac e Windows, é mais fácil do que nunca desenvolver aplicativos do Docker, e a configuração é simples.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-127">With the latest versions of Docker Desktop for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-128">Para obter instruções sobre como configurar o Docker desktop para Windows, acesse <https://docs.docker.com/docker-for-windows/> .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-128">For instructions on setting up Docker Desktop for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
> <span data-ttu-id="ba1e4-129">Para obter instruções sobre como configurar o Docker desktop para Mac, vá para <https://docs.docker.com/docker-for-mac/> .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-129">For instructions on setting up Docker Desktop for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="ba1e4-130">Além disso, você precisará de um editor de código para que possa desenvolver o aplicativo enquanto estiver usando a CLI do Docker.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="ba1e4-131">A Microsoft fornece Visual Studio Code, que é um editor de código leve com suporte no Windows, Linux e macOS, e fornece IntelliSense com [suporte para várias linguagens](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .net, go, Java, Ruby, Python e linguagens mais modernas), [depuração](https://code.visualstudio.com/Docs/editor/debugging), [integração com git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [suporte a extensões](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="ba1e4-132">Esse editor é uma ótima opção para desenvolvedores de macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="ba1e4-133">No Windows, você também pode usar o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-134">Para obter instruções sobre como instalar o Visual Studio Code para Windows, Linux ou macOS, vá para <https://code.visualstudio.com/docs/setup/setup-overview/> .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="ba1e4-135">Para obter instruções sobre como configurar o Docker para Mac, acesse <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="ba1e4-136">Você pode trabalhar com a CLI do Docker e escrever seu código usando qualquer editor de código, mas usar o Visual Studio Code com a extensão do Docker torna mais fácil criar arquivos `Dockerfile` e `docker-compose.yml` em seu workspace.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="ba1e4-137">Você também pode executar tarefas e scripts do IDE do Visual Studio Code para executar comandos do Docker usando a CLI do Docker abaixo.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="ba1e4-138">A extensão do Docker para o VS Code fornece os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="ba1e4-139">Geração automática de arquivos `Dockerfile` e `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="ba1e4-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="ba1e4-140">Destaque de sintaxe e dicas ao passar o mouse para arquivos `docker-compose.yml` e `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="ba1e4-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="ba1e4-141">IntelliSense (preenchimentos) para arquivos `Dockerfile` e `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="ba1e4-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="ba1e4-142">Linting (erros e avisos) para arquivos `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="ba1e4-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="ba1e4-143">Integração de paleta de comandos (F1) para os comandos do Docker mais comuns</span><span class="sxs-lookup"><span data-stu-id="ba1e4-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="ba1e4-144">Integração do Explorer para gerenciar Imagens e Contêineres</span><span class="sxs-lookup"><span data-stu-id="ba1e4-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="ba1e4-145">Implantar imagens do DockerHub e dos Registros de Contêiner do Azure no Serviço de Aplicativo do Azure</span><span class="sxs-lookup"><span data-stu-id="ba1e4-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="ba1e4-146">Para instalar a extensão do Docker, pressione Ctrl + Shift + P, digite `ext install` e, em seguida, execute o comando Instalar Extensão para abrir a lista de extensões do Marketplace.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="ba1e4-147">Em seguida, digite **docker** para filtrar os resultados e, então, selecione a extensão Docker Support, conforme ilustrado na Figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Modo de exibição da extensão do Docker para VS Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="ba1e4-149">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-149">**Figure 4-23**.</span></span> <span data-ttu-id="ba1e4-150">Instalando a extensão do Docker no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ba1e4-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-nodejs-and-ruby"></a><span data-ttu-id="ba1e4-151">Etapa 2: criar um DockerFile relacionado a uma imagem existente (ambientes de sistema operacional simples ou de desenvolvimento, como .NET, Node.js e Ruby)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET, Node.js, and Ruby)</span></span>

<span data-ttu-id="ba1e4-152">Você precisará de um `DockerFile` por imagem personalizada a ser criada e por contêiner a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="ba1e4-153">Se seu aplicativo for composto por um único serviço personalizado, você precisará de um único `DockerFile` .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-153">If your app is made up of single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="ba1e4-154">No entanto, se o aplicativo for composto por vários serviços (por exemplo, em uma arquitetura de microsserviços), você precisará de um `Dockerfile` por serviço.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="ba1e4-155">Normalmente, o `DockerFile` é colocado na pasta raiz do aplicativo ou serviço e contém os comandos necessários para que o Docker saiba como configurar e executar esse aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="ba1e4-156">Você pode criar seu `DockerFile` e adicioná-lo ao seu projeto junto com seu código (node.js, .net, etc.) ou, se você for novo no ambiente, dê uma olhada na dica a seguir.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-157">Você pode usar a extensão do Docker para orientá-lo ao usar os arquivos `Dockerfile` e `docker-compose.yml` relacionados a seus contêineres do Docker.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="ba1e4-158">Eventualmente, você provavelmente gravará esses tipos de arquivos sem essa ferramenta, mas usar a extensão do Docker é um bom ponto de partida que acelerará sua curva de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="ba1e4-159">Na Figura 4-24, você pode ver as etapas para adicionar os arquivos do Docker a um projeto usando a extensão do Docker para VS Code:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-159">In Figure 4-24, you can see the steps to add the docker files to a project by using the Docker Extension for VS Code:</span></span>

1. <span data-ttu-id="ba1e4-160">Abra a paleta de comandos, digite "**Docker**" e selecione "**Adicionar arquivos do Docker ao espaço de trabalho**".</span><span class="sxs-lookup"><span data-stu-id="ba1e4-160">Open the command palette, type "**docker**" and select "**Add Docker Files to Workspace**".</span></span>
2. <span data-ttu-id="ba1e4-161">Selecionar plataforma de aplicativo (ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-161">Select Application Platform (ASP.NET Core)</span></span>
3. <span data-ttu-id="ba1e4-162">Selecionar sistema operacional (Linux)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-162">Select Operating System (Linux)</span></span>
4. <span data-ttu-id="ba1e4-163">Incluir arquivos de Docker Compose opcionais</span><span class="sxs-lookup"><span data-stu-id="ba1e4-163">Include optional Docker Compose files</span></span>
5. <span data-ttu-id="ba1e4-164">Insira as portas a serem publicadas (80, 443)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-164">Enter ports to publish (80, 443)</span></span>
6. <span data-ttu-id="ba1e4-165">Selecione o projeto</span><span class="sxs-lookup"><span data-stu-id="ba1e4-165">Select the project</span></span>

![Etapas para adicionar arquivos do Docker com a extensão do Docker](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="ba1e4-167">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-167">**Figure 4-24**.</span></span> <span data-ttu-id="ba1e4-168">Arquivos do Docker adicionados usando o comando **Adicionar arquivos do Docker ao espaço de trabalho**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-168">Docker files added using the **Add Docker files to Workspace** command</span></span>

<span data-ttu-id="ba1e4-169">Quando você adiciona um DockerFile, você especifica qual imagem do Docker base você usará (como usar `FROM mcr.microsoft.com/dotnet/aspnet` ).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-169">When you add a DockerFile, you specify what base Docker image you'll be using (like using `FROM mcr.microsoft.com/dotnet/aspnet`).</span></span> <span data-ttu-id="ba1e4-170">Normalmente, você criará sua imagem personalizada sobre uma imagem de base que você obtém de qualquer repositório oficial no [registro do Hub do Docker](https://hub.docker.com/) (como uma [imagem para .net](https://hub.docker.com/_/microsoft-dotnet/) ou a [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-170">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET](https://hub.docker.com/_/microsoft-dotnet/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-171">Você precisará repetir esse procedimento para cada projeto em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-171">You'll have to repeat this procedure for every project in your application.</span></span> <span data-ttu-id="ba1e4-172">No entanto, a extensão solicitará que o arquivo do Docker-compote gerado seja substituído após a primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-172">However, the extension will ask to overwrite the generated docker-compose file after the first time.</span></span> <span data-ttu-id="ba1e4-173">Você deve responder a não substituí-lo, portanto, a extensão cria arquivos separados do Docker-Compose, que você pode mesclar manualmente, antes de executar o Docker-Compose.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-173">You should reply to not overwrite it, so the extension creates separate docker-compose files, that you can then merge by hand, prior to running docker-compose.</span></span>

<span data-ttu-id="ba1e4-174">**_Usar uma imagem oficial do Docker existente_**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-174">**_Use an existing official Docker image_**</span></span>

<span data-ttu-id="ba1e4-175">Usar um repositório oficial de uma pilha de linguagem com um número de versão garante que recursos da mesma linguagem estejam disponíveis em todos os computadores (incluindo desenvolvimento, teste e produção).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-175">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="ba1e4-176">Veja a seguir um exemplo de DockerFile para um contêiner .NET:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-176">The following is a sample DockerFile for a .NET container:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

<span data-ttu-id="ba1e4-177">Nesse caso, a imagem é baseada na versão 5,0 do oficial ASP.NET Core imagem do Docker (vários arcos para Linux e Windows), de acordo com a linha `FROM mcr.microsoft.com/dotnet/aspnet:5.0` .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-177">In this case, the image is based on version 5.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/aspnet:5.0`.</span></span> <span data-ttu-id="ba1e4-178">(Para obter mais informações sobre este tópico, consulte a página [ASP.NET Core imagem do Docker](https://hub.docker.com/_/microsoft-dotnet-aspnet/) e a página [imagem do Docker do .net](https://hub.docker.com/_/microsoft-dotnet/) ).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-178">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-aspnet/) page and the [.NET Docker Image](https://hub.docker.com/_/microsoft-dotnet/) page).</span></span>

<span data-ttu-id="ba1e4-179">No DockerFile, você também pode instruir o Docker para escutar a porta TCP que você usará no tempo de execução (como a porta 80 ou 443).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-179">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80 or 443).</span></span>

<span data-ttu-id="ba1e4-180">Você pode especificar mais definições de configurações no Dockerfile, dependendo da linguagem e da estrutura usadas.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="ba1e4-181">Por exemplo, a `ENTRYPOINT` linha com `["dotnet", "WebMvcApplication.dll"]` instrui o Docker a executar um aplicativo .net.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-181">For instance, the `ENTRYPOINT` line with `["dotnet", "WebMvcApplication.dll"]` tells Docker to run a .NET application.</span></span> <span data-ttu-id="ba1e4-182">Se você estiver usando o SDK e a CLI do .NET ( `dotnet CLI` ) para compilar e executar o aplicativo .net, essa configuração será diferente.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-182">If you're using the SDK and the .NET CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="ba1e4-183">O essencial aqui é que a linha ENTRYPOINT e outras configurações dependem da linguagem e da plataforma que você escolher para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-183">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-184">Para obter mais informações sobre a criação de imagens do Docker para aplicativos .NET, vá para <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images> .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-184">For more information about building Docker images for .NET applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="ba1e4-185">Para saber mais sobre como criar suas próprias imagens, acesse <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-185">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="ba1e4-186">**Usar repositórios de imagens com várias arquiteturas**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-186">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="ba1e4-187">Um único nome de imagem em um repositório pode conter variantes de plataforma, como uma imagem do Linux e uma imagem do Windows.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-187">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="ba1e4-188">Esse recurso permite que fornecedores como a Microsoft (criadores de imagem base) criem um único repositório para abranger várias plataformas (ou seja, Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-188">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="ba1e4-189">Por exemplo, o repositório [dotnet/ASPNET](https://hub.docker.com/_/microsoft-dotnet-aspnet/) disponível no registro do Hub do Docker fornece suporte para Linux e Windows nano Server usando o mesmo nome de imagem.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-189">For example, the [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="ba1e4-190">A extração da imagem [dotnet/ASPNET](https://hub.docker.com/_/microsoft-dotnet-aspnet/) de um host do Windows efetua pull da variante do Windows, enquanto o Pull do mesmo nome de imagem de um host Linux efetua pull da variante do Linux.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-190">Pulling the [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="ba1e4-191">**_Criar sua imagem base do zero_**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-191">**_Create your base image from scratch_**</span></span>

<span data-ttu-id="ba1e4-192">Você pode criar sua própria imagem base do Docker do zero, conforme explicado neste [artigo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) do Docker.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-192">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="ba1e4-193">Esse cenário provavelmente não é recomendado para iniciantes no Docker, mas, se você quiser definir os bits específicos de sua própria imagem base, poderá fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-193">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="ba1e4-194">Etapa 3: criar suas imagens personalizadas do Docker inserindo seu serviço nele</span><span class="sxs-lookup"><span data-stu-id="ba1e4-194">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="ba1e4-195">Para cada serviço personalizado que compõe seu aplicativo, você precisará criar uma imagem relacionada.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-195">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="ba1e4-196">Se seu aplicativo for composto por um único serviço ou aplicativo Web, você precisará apenas de uma única imagem.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-196">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="ba1e4-197">Ao levar em consideração o "fluxo de trabalho de DevOps de loop externo", as imagens serão criadas por um processo de build automatizado sempre que você efetuar push de seu código-fonte para um repositório Git (integração contínua), portanto, as imagens serão criadas no ambiente global de seu código-fonte.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-197">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="ba1e4-198">Mas antes de você considerar a saída dessa rota de loop externo, você precisa garantir que o aplicativo Docker esteja realmente funcionando corretamente para que eles não enviem um código que possa não funcionar corretamente para o sistema de controle do código-fonte (git, etc.).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-198">But before you consider going to that outer-loop route, you need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="ba1e4-199">Sendo assim, cada desenvolvedor precisa primeiro realizar todo o processo de loop interno para testar localmente e continuar desenvolvendo até que queiram efetuar push de um recurso ou alteração completa para o sistema de controle do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-199">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="ba1e4-200">Para criar uma imagem em seu ambiente local e usar o DockerFile, você pode usar o comando Docker Build, como mostrado na Figura 4-25, porque ele já marca a imagem para você e compila as imagens para todos os serviços no aplicativo com um comando simples.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-200">To create an image in your local environment and using the DockerFile, you can use the docker build command, as shown in Figure 4-25, because it already tags the image for you and builds the images for all services in the application with a simple command.</span></span>

![Captura de tela mostrando a saída do console do comando Docker-Compose Build.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="ba1e4-202">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-202">**Figure 4-25**.</span></span> <span data-ttu-id="ba1e4-203">Executando docker build</span><span class="sxs-lookup"><span data-stu-id="ba1e4-203">Running docker build</span></span>

<span data-ttu-id="ba1e4-204">Opcionalmente, em vez de executar `docker build` diretamente da pasta do projeto, você pode primeiro gerar uma pasta implantável com as bibliotecas .NET necessárias usando o comando run `dotnet publish` e, em seguida, executando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-204">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="ba1e4-205">Este exemplo cria uma imagem do Docker com o nome `webapi:latest` (`:latest` é uma marca, como uma versão específica).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-205">This example creates a Docker image with the name `webapi:latest` (`:latest` is a tag, like a specific version).</span></span> <span data-ttu-id="ba1e4-206">Você poderá realizar esta etapa para cada imagem personalizada que precisar criar para o seu aplicativo do Docker composto com vários contêineres.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-206">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span> <span data-ttu-id="ba1e4-207">No entanto, veremos na próxima seção que é mais fácil fazer isso usando `docker-compose` .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-207">However, we'll see in the next section that it's easier to do this using `docker-compose`.</span></span>

<span data-ttu-id="ba1e4-208">Você pode encontrar as imagens existentes no seu repositório local (seu computador de desenvolvimento) usando o `docker images` comando, como ilustrado na figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-208">You can find the existing images in your local repository (your development machine) by using the `docker images` command, as illustrated in Figure 4-26.</span></span>

![Saída do console do comando docker images, mostrando as imagens existentes.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="ba1e4-210">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-210">**Figure 4-26**.</span></span> <span data-ttu-id="ba1e4-211">Exibindo imagens existentes usando imagens do Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-211">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="ba1e4-212">Etapa 4: definir seus serviços em Docker-Compose. yml ao criar um aplicativo do Docker composto com vários serviços</span><span class="sxs-lookup"><span data-stu-id="ba1e4-212">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="ba1e4-213">Com o arquivo `docker-compose.yml`, você pode definir um conjunto de serviços relacionados para que sejam implantados como um aplicativo composto usando os comandos de implantação explicados na seção sobre a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-213">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="ba1e4-214">Crie esse arquivo na pasta principal ou raiz da solução; ele deve ter conteúdo semelhante ao mostrado neste arquivo `docker-compose.yml`:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-214">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

<span data-ttu-id="ba1e4-215">Nesse caso em particular, esse arquivo define três serviços: o serviço de API Web (seu serviço personalizado), um aplicativo Web e o serviço Redis (um serviço de cache popular).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-215">In this particular case, this file defines three services: the web API service (your custom service), a web application, and the Redis service (a popular cache service).</span></span> <span data-ttu-id="ba1e4-216">Cada serviço será implantado como um contêiner, portanto, você precisa usar uma imagem concreta do Docker para cada um.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-216">Each service will be deployed as a container, so you need to use a concrete Docker image for each.</span></span> <span data-ttu-id="ba1e4-217">Para este aplicativo específico:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-217">For this particular application:</span></span>

- <span data-ttu-id="ba1e4-218">O serviço de API Web é criado a partir do DockerFile no `src/WebApi/Dockerfile` diretório.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-218">The web API service is built from the DockerFile in the `src/WebApi/Dockerfile` directory.</span></span>

- <span data-ttu-id="ba1e4-219">A porta de host 51080 é encaminhada para a porta exposta 80 no `webapi` contêiner.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-219">The host port 51080 is forwarded to the exposed port 80 on the `webapi` container.</span></span>

- <span data-ttu-id="ba1e4-220">O serviço API da Web depende do serviço Redis</span><span class="sxs-lookup"><span data-stu-id="ba1e4-220">The web API service depends on the Redis service</span></span>

- <span data-ttu-id="ba1e4-221">O aplicativo Web acessa o serviço de API Web usando o endereço interno: `http://webapi` .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-221">The web application accesses the web API service using the internal address: `http://webapi`.</span></span>

- <span data-ttu-id="ba1e4-222">O serviço Redis usa a [imagem de Redis pública mais recente](https://hub.docker.com/_/redis/) extraída do registro do Hub do Docker.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-222">The Redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="ba1e4-223">[Redis](https://redis.io/) é um sistema de cache popular para aplicativos do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-223">[Redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="ba1e4-224">Etapa 5: criar e executar o aplicativo Docker</span><span class="sxs-lookup"><span data-stu-id="ba1e4-224">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="ba1e4-225">Se seu aplicativo tiver apenas um contêiner, você precisará apenas executá-lo implantando-o no host do Docker (VM ou servidor físico).</span><span class="sxs-lookup"><span data-stu-id="ba1e4-225">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="ba1e4-226">No entanto, se o aplicativo for composto por vários serviços, você também precisará _compô-lo_.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-226">However, if your app is made up of multiple services, you need to _compose it_, too.</span></span> <span data-ttu-id="ba1e4-227">Vejamos as diferentes opções.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-227">Let's see the different options.</span></span>

<span data-ttu-id="ba1e4-228">**_Opção A: executar um único contêiner ou serviço_**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-228">**_Option A: Run a single container or service_**</span></span>

<span data-ttu-id="ba1e4-229">Você pode executar a imagem do Docker usando o comando docker run, conforme mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="ba1e4-229">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 50080:80 webapp:latest
```

<span data-ttu-id="ba1e4-230">Para essa implantação específica, vamos redirecionar as solicitações enviadas para a porta 50080 no host para a porta interna 80.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-230">For this particular deployment, we'll be redirecting requests sent to port 50080 on the host to the internal port 80.</span></span>

<span data-ttu-id="ba1e4-231">**_Opção B: compor e executar um aplicativo de vários contêineres_**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-231">**_Option B: Compose and run a multiple-container application_**</span></span>

<span data-ttu-id="ba1e4-232">Na maioria dos cenários empresariais, um aplicativo do Docker será composto por vários serviços.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-232">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="ba1e4-233">Nesses casos, você pode executar o `docker-compose up` comando (figura 4-27), que usará o arquivo Docker-Compose. yml que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-233">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you created previously.</span></span> <span data-ttu-id="ba1e4-234">A execução desse comando compila todas as imagens personalizadas e implanta o aplicativo composto com todos os seus contêineres relacionados.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-234">Running this command builds all custom images and deploys the composed application with all of its related containers.</span></span>

![Saída de console do comando docker-compose up.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="ba1e4-236">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-236">**Figure 4-27**.</span></span> <span data-ttu-id="ba1e4-237">Resultados da execução do comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="ba1e4-237">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="ba1e4-238">Depois de executar `docker-compose up`, implante seu aplicativo e os contêineres relacionados no Host do Docker, conforme ilustrado na Figura 4-28, na representação da VM.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-238">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![VM executando aplicativos de vários contêineres.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="ba1e4-240">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-240">**Figure 4-28**.</span></span> <span data-ttu-id="ba1e4-241">VM com contêineres do Docker implantados</span><span class="sxs-lookup"><span data-stu-id="ba1e4-241">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="ba1e4-242">Etapa 6: testar o aplicativo Docker (localmente, em sua VM de CD local)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-242">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="ba1e4-243">Esta etapa varia de acordo com o que seu aplicativo está fazendo.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-243">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="ba1e4-244">Em uma API Web simples do .NET "Olá, Mundo" implantada como um único contêiner ou serviço, você precisaria apenas acessar o serviço fornecendo a porta TCP especificada no DockerFile.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-244">In a simple .NET Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="ba1e4-245">No host do Docker, abra um navegador e navegue até esse site. Você deverá ver seu aplicativo/serviço em execução, conforme demonstrado na Figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-245">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Modo de exibição de navegador da resposta de localhost/API/ valores.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="ba1e4-247">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-247">**Figure 4-29**.</span></span> <span data-ttu-id="ba1e4-248">Testando o aplicativo Docker localmente usando o navegador</span><span class="sxs-lookup"><span data-stu-id="ba1e4-248">Testing your Docker application locally by using the browser</span></span>

<span data-ttu-id="ba1e4-249">Observe que ele está usando a porta 50080, mas internamente ela está sendo redirecionada para a porta 80, porque é assim que ela foi implantada `docker compose` , conforme explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-249">Note that it's using port 50080, but internally it's being redirected to port 80, because that's how it was deployed with `docker compose`, as explained earlier.</span></span>

<span data-ttu-id="ba1e4-250">Você pode testar isso usando o navegador usando a rotação do terminal, conforme descrito na Figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-250">You can test this by using the browser using CURL from the terminal, as depicted in Figure 4-30.</span></span>

![O resultado da ondulação obtido de http://localhost:51080/WeatherForecast](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="ba1e4-252">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-252">**Figure 4-30**.</span></span> <span data-ttu-id="ba1e4-253">Testando um aplicativo do Docker localmente usando CURL</span><span class="sxs-lookup"><span data-stu-id="ba1e4-253">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="ba1e4-254">**Depurando um contêiner em execução no Docker**</span><span class="sxs-lookup"><span data-stu-id="ba1e4-254">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="ba1e4-255">Visual Studio Code dá suporte à depuração do Docker se você estiver usando Node.js e outras plataformas como contêineres .NET.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-255">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET containers.</span></span>

<span data-ttu-id="ba1e4-256">Você também pode depurar contêineres .NET ou .NET Framework no Docker ao usar o Visual Studio para Windows ou Mac, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-256">You also can debug .NET or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="ba1e4-257">Para saber mais sobre depuração Node.js contêineres do Docker, consulte <https://blog.docker.com/2016/07/live-debugging-docker/> e <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more> .</span><span class="sxs-lookup"><span data-stu-id="ba1e4-257">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="ba1e4-258">[Anterior](docker-apps-development-environment.md) 
>  [Avançar](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-258">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
