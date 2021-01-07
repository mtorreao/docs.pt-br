---
title: Docker-gRPC para desenvolvedores do WCF
description: Criando imagens do Docker para aplicativos ASP.NET Core gRPC
ms.date: 01/06/2021
ms.openlocfilehash: f59518a28b0a1dee75c792ba03bd4af826638502
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970083"
---
# <a name="create-docker-images"></a><span data-ttu-id="a5e97-103">Criar imagens do Docker</span><span class="sxs-lookup"><span data-stu-id="a5e97-103">Create Docker images</span></span>

<span data-ttu-id="a5e97-104">Esta seção aborda a criação de imagens do Docker para ASP.NET Core aplicativos gRPC, prontos para execução no Docker, kubernetes ou outros ambientes de contêiner.</span><span class="sxs-lookup"><span data-stu-id="a5e97-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="a5e97-105">O aplicativo de exemplo usado, com um ASP.NET Core aplicativo Web MVC e um serviço gRPC, está disponível no repositório [dotnet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) no github.</span><span class="sxs-lookup"><span data-stu-id="a5e97-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="a5e97-106">Imagens base da Microsoft para aplicativos ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a5e97-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="a5e97-107">A Microsoft fornece uma variedade de imagens básicas para a criação e a execução de aplicativos .NET.</span><span class="sxs-lookup"><span data-stu-id="a5e97-107">Microsoft provides a range of base images for building and running .NET applications.</span></span> <span data-ttu-id="a5e97-108">Para criar uma imagem ASP.NET Core 5,0, você usa duas imagens base:</span><span class="sxs-lookup"><span data-stu-id="a5e97-108">To create an ASP.NET Core 5.0 image, you use two base images:</span></span>

- <span data-ttu-id="a5e97-109">Uma imagem do SDK para compilar e publicar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a5e97-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="a5e97-110">Uma imagem de tempo de execução para implantação.</span><span class="sxs-lookup"><span data-stu-id="a5e97-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="a5e97-111">Imagem</span><span class="sxs-lookup"><span data-stu-id="a5e97-111">Image</span></span> | <span data-ttu-id="a5e97-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5e97-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="a5e97-113">mcr.microsoft.com/dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="a5e97-113">mcr.microsoft.com/dotnet/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-sdk/) | <span data-ttu-id="a5e97-114">Para a criação de aplicativos com o `docker build` .</span><span class="sxs-lookup"><span data-stu-id="a5e97-114">For building applications with `docker build`.</span></span> <span data-ttu-id="a5e97-115">Não deve ser usado na produção.</span><span class="sxs-lookup"><span data-stu-id="a5e97-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="a5e97-116">mcr.microsoft.com/dotnet/aspnet</span><span class="sxs-lookup"><span data-stu-id="a5e97-116">mcr.microsoft.com/dotnet/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | <span data-ttu-id="a5e97-117">Contém as dependências de tempo de execução e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5e97-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="a5e97-118">Para produção.</span><span class="sxs-lookup"><span data-stu-id="a5e97-118">For production.</span></span> |

<span data-ttu-id="a5e97-119">Para cada imagem, há quatro variantes com base em diferentes distribuições do Linux, diferenciadas por marcas.</span><span class="sxs-lookup"><span data-stu-id="a5e97-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="a5e97-120">Marca (s) de imagem</span><span class="sxs-lookup"><span data-stu-id="a5e97-120">Image tag(s)</span></span> | <span data-ttu-id="a5e97-121">Linux</span><span class="sxs-lookup"><span data-stu-id="a5e97-121">Linux</span></span> | <span data-ttu-id="a5e97-122">Observações</span><span class="sxs-lookup"><span data-stu-id="a5e97-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="a5e97-123">5,0-Buster-Slim, 5,0</span><span class="sxs-lookup"><span data-stu-id="a5e97-123">5.0-buster-slim, 5.0</span></span> | <span data-ttu-id="a5e97-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="a5e97-124">Debian 10</span></span> | <span data-ttu-id="a5e97-125">A imagem padrão se nenhuma variante do sistema operacional for especificada.</span><span class="sxs-lookup"><span data-stu-id="a5e97-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="a5e97-126">5,0 – Alpine Ski</span><span class="sxs-lookup"><span data-stu-id="a5e97-126">5.0-alpine</span></span> | <span data-ttu-id="a5e97-127">Alpine 3,12</span><span class="sxs-lookup"><span data-stu-id="a5e97-127">Alpine 3.12</span></span> | <span data-ttu-id="a5e97-128">As imagens da Alpine base são muito menores do que Debian ou Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a5e97-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="a5e97-129">5,0 – focal</span><span class="sxs-lookup"><span data-stu-id="a5e97-129">5.0-focal</span></span>| <span data-ttu-id="a5e97-130">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="a5e97-130">Ubuntu 20.04</span></span> | |

<span data-ttu-id="a5e97-131">A imagem do Alpine base é de cerca de 100 MB, em comparação com 200 MB para as imagens Debian e Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="a5e97-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="a5e97-132">Alguns pacotes de software ou bibliotecas podem não estar disponíveis no gerenciamento de pacotes da Alpine Ski.</span><span class="sxs-lookup"><span data-stu-id="a5e97-132">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="a5e97-133">Se você não tiver certeza de qual imagem usar, provavelmente deverá escolher o Debian padrão.</span><span class="sxs-lookup"><span data-stu-id="a5e97-133">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5e97-134">Certifique-se de usar a mesma variante do Linux para a compilação e o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a5e97-134">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="a5e97-135">Os aplicativos criados e publicados em uma variante podem não funcionar em outro.</span><span class="sxs-lookup"><span data-stu-id="a5e97-135">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="a5e97-136">Criar uma imagem do Docker</span><span class="sxs-lookup"><span data-stu-id="a5e97-136">Create a Docker image</span></span>

<span data-ttu-id="a5e97-137">Uma imagem do Docker é definida por um *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="a5e97-137">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="a5e97-138">Esse *Dockerfile* é um arquivo de texto que contém todos os comandos necessários para compilar o aplicativo e instalar quaisquer dependências necessárias para compilar ou executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a5e97-138">This *Dockerfile* is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="a5e97-139">O exemplo a seguir mostra a Dockerfile mais simples para um aplicativo ASP.NET Core 5,0:</span><span class="sxs-lookup"><span data-stu-id="a5e97-139">The following example shows the simplest Dockerfile for an ASP.NET Core 5.0 application:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="a5e97-140">O Dockerfile tem duas partes: a primeira usa a `sdk` imagem base para compilar e publicar o aplicativo; a segunda cria uma imagem de tempo de execução a partir da `aspnet` base.</span><span class="sxs-lookup"><span data-stu-id="a5e97-140">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="a5e97-141">Isso ocorre porque a `sdk` imagem está em cerca de 900 MB, em comparação com cerca de 200 MB para a imagem de tempo de execução, e a maior parte de seu conteúdo é desnecessária no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a5e97-141">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="a5e97-142">As etapas de compilação</span><span class="sxs-lookup"><span data-stu-id="a5e97-142">The build steps</span></span>

| <span data-ttu-id="a5e97-143">Etapa</span><span class="sxs-lookup"><span data-stu-id="a5e97-143">Step</span></span> | <span data-ttu-id="a5e97-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5e97-144">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="a5e97-145">Declara a imagem base e atribui o `builder` alias.</span><span class="sxs-lookup"><span data-stu-id="a5e97-145">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="a5e97-146">Cria o `/src` diretório e o define como o diretório de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="a5e97-146">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="a5e97-147">Copia tudo abaixo do diretório atual no host para o diretório atual na imagem.</span><span class="sxs-lookup"><span data-stu-id="a5e97-147">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="a5e97-148">Restaura todos os pacotes externos (ASP.NET Core estrutura 3,0 é pré-instalada com o SDK).</span><span class="sxs-lookup"><span data-stu-id="a5e97-148">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="a5e97-149">Compila e publica uma compilação de versão.</span><span class="sxs-lookup"><span data-stu-id="a5e97-149">Builds and publishes a Release build.</span></span> <span data-ttu-id="a5e97-150">Observe que o `--runtime` sinalizador não é necessário.</span><span class="sxs-lookup"><span data-stu-id="a5e97-150">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="a5e97-151">As etapas da imagem de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="a5e97-151">The runtime image steps</span></span>

| <span data-ttu-id="a5e97-152">Etapa</span><span class="sxs-lookup"><span data-stu-id="a5e97-152">Step</span></span> | <span data-ttu-id="a5e97-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5e97-153">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="a5e97-154">Declara uma nova imagem de base.</span><span class="sxs-lookup"><span data-stu-id="a5e97-154">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="a5e97-155">Cria o `/app` diretório e o define como o diretório de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="a5e97-155">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="a5e97-156">Copia o aplicativo publicado da imagem anterior, usando o `builder` alias da primeira `FROM` linha.</span><span class="sxs-lookup"><span data-stu-id="a5e97-156">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="a5e97-157">Define o comando a ser executado quando o contêiner é iniciado.</span><span class="sxs-lookup"><span data-stu-id="a5e97-157">Sets the command to run when the container starts.</span></span> <span data-ttu-id="a5e97-158">O `dotnet` comando na imagem de tempo de execução só pode executar arquivos dll.</span><span class="sxs-lookup"><span data-stu-id="a5e97-158">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="a5e97-159">HTTPS no Docker</span><span class="sxs-lookup"><span data-stu-id="a5e97-159">HTTPS in Docker</span></span>

<span data-ttu-id="a5e97-160">As imagens base da Microsoft para o Docker definem a `ASPNETCORE_URLS` variável de ambiente como `http://+:80` , o que significa que Kestrel é executado sem https nessa porta.</span><span class="sxs-lookup"><span data-stu-id="a5e97-160">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="a5e97-161">Se você estiver usando HTTPS com um certificado personalizado (conforme descrito em [aplicativos gRPC hospedados internamente](self-hosted.md)), deverá substituir essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a5e97-161">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this configuration.</span></span> <span data-ttu-id="a5e97-162">Defina a variável de ambiente na parte de criação da imagem de tempo de execução de seu Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a5e97-162">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="a5e97-163">O arquivo. dockerignore</span><span class="sxs-lookup"><span data-stu-id="a5e97-163">The .dockerignore file</span></span>

<span data-ttu-id="a5e97-164">Assim como `.gitignore` os arquivos que excluem determinados arquivos e diretórios do controle do código-fonte, o `.dockerignore` arquivo pode ser usado para excluir arquivos e diretórios de serem copiados para a imagem durante a compilação.</span><span class="sxs-lookup"><span data-stu-id="a5e97-164">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="a5e97-165">Esse arquivo não apenas poupa tempo de cópia, mas também pode evitar alguns erros que surgem de ter o `obj` diretório do seu PC copiado para a imagem.</span><span class="sxs-lookup"><span data-stu-id="a5e97-165">This file not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="a5e97-166">No mínimo, você deve adicionar entradas para `bin` e `obj` ao seu `.dockerignore` arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5e97-166">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="a5e97-167">Criar a imagem</span><span class="sxs-lookup"><span data-stu-id="a5e97-167">Build the image</span></span>

<span data-ttu-id="a5e97-168">Para uma `StockKube.sln` solução que contém dois aplicativos diferentes `StockData` e `StockWeb` , é mais simples colocar o Dockerfile para cada um deles no diretório base.</span><span class="sxs-lookup"><span data-stu-id="a5e97-168">For a `StockKube.sln` solution containing two different applications `StockData` and `StockWeb`, it's simplest to put the Dockerfile for each one of them in the base directory.</span></span> <span data-ttu-id="a5e97-169">Nesse caso, para criar a imagem, use o comando a seguir `docker build` do mesmo diretório em que o `.sln` arquivo reside.</span><span class="sxs-lookup"><span data-stu-id="a5e97-169">In that case, to build the image, use the following `docker build` command from the same directory where `.sln` file resides.</span></span>

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

<span data-ttu-id="a5e97-170">O `--tag` sinalizador com nome confuso (que pode ser reduzido `-t` ) especifica o nome completo da imagem, incluindo a marca real, se especificado.</span><span class="sxs-lookup"><span data-stu-id="a5e97-170">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="a5e97-171">O `.` no final especifica o contexto no qual a compilação será executada; o diretório de trabalho atual para os `COPY` comandos no Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a5e97-171">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="a5e97-172">Se você tiver vários aplicativos em uma única solução, poderá manter o Dockerfile de cada aplicativo em sua própria pasta, ao lado do `.csproj` arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5e97-172">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="a5e97-173">Você ainda deve executar o `docker build` comando do diretório base para garantir que a solução e todos os projetos sejam copiados para a imagem.</span><span class="sxs-lookup"><span data-stu-id="a5e97-173">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="a5e97-174">Você pode especificar um Dockerfile abaixo do diretório atual usando o `--file` sinalizador (ou `-f` ).</span><span class="sxs-lookup"><span data-stu-id="a5e97-174">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="a5e97-175">Executar a imagem em um contêiner em seu computador</span><span class="sxs-lookup"><span data-stu-id="a5e97-175">Run the image in a container on your machine</span></span>

<span data-ttu-id="a5e97-176">Para executar a imagem em sua instância local do Docker, use o `docker run` comando.</span><span class="sxs-lookup"><span data-stu-id="a5e97-176">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

<span data-ttu-id="a5e97-177">O `-ti` sinalizador conecta o terminal atual ao terminal do contêiner e é executado no modo interativo.</span><span class="sxs-lookup"><span data-stu-id="a5e97-177">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="a5e97-178">A `-p 5000:80` porta de publicação (links) 80 no contêiner para a porta 5000 na interface de rede do localhost.</span><span class="sxs-lookup"><span data-stu-id="a5e97-178">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="a5e97-179">Efetue o push da imagem para um Registro</span><span class="sxs-lookup"><span data-stu-id="a5e97-179">Push the image to a registry</span></span>

<span data-ttu-id="a5e97-180">Depois de verificar se a imagem funciona, envie-a por push para um registro do Docker para disponibilizá-la em outros sistemas.</span><span class="sxs-lookup"><span data-stu-id="a5e97-180">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="a5e97-181">As redes internas precisarão provisionar um registro do Docker.</span><span class="sxs-lookup"><span data-stu-id="a5e97-181">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="a5e97-182">Essa atividade pode ser tão simples quanto executar a [própria `registry` imagem do Docker](https://docs.docker.com/registry/deploying/) (o registro do Docker é executado em um contêiner do Docker), mas há várias soluções mais abrangentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a5e97-182">This activity can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="a5e97-183">Para o compartilhamento externo e o uso de nuvem, há vários registros gerenciados disponíveis, como o [registro de contêiner do Azure](/azure/container-registry/) ou o [Hub do Docker](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="a5e97-183">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="a5e97-184">Para enviar por push para o Hub do Docker, Prefixe o nome da imagem com o nome do usuário ou da organização.</span><span class="sxs-lookup"><span data-stu-id="a5e97-184">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

<span data-ttu-id="a5e97-185">Para enviar por push para um registro privado, Prefixe o nome da imagem com o nome do host do registro e o nome da organização.</span><span class="sxs-lookup"><span data-stu-id="a5e97-185">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

<span data-ttu-id="a5e97-186">Depois que a imagem estiver em um registro, você poderá implantá-la em hosts do Docker individuais ou em um mecanismo de orquestração de contêiner, como kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a5e97-186">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a5e97-187">[Anterior](self-hosted.md) 
> [Avançar](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="a5e97-187">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
