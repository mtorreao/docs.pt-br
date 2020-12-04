---
title: Implantar aplicativos .NET no Raspberry Pi
description: Saiba como implantar aplicativos .NET no Raspberry Pi.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96585639"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a><span data-ttu-id="f7955-103">Implantar aplicativos .NET no Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="f7955-103">Deploy .NET apps to Raspberry Pi</span></span>

<span data-ttu-id="f7955-104">A implantação de aplicativos .NET no Raspberry Pi é idêntica à de qualquer outra plataforma.</span><span class="sxs-lookup"><span data-stu-id="f7955-104">Deployment of .NET apps to Raspberry Pi is identical to that of any other platform.</span></span> <span data-ttu-id="f7955-105">Seu aplicativo pode ser executado como modo de implantação *independente* ou *dependente de estrutura* .</span><span class="sxs-lookup"><span data-stu-id="f7955-105">Your app can run as *self-contained* or *framework-dependent* deployment modes.</span></span> <span data-ttu-id="f7955-106">Há vantagens para cada estratégia.</span><span class="sxs-lookup"><span data-stu-id="f7955-106">There are advantages to each strategy.</span></span> <span data-ttu-id="f7955-107">Para obter mais informações, consulte [visão geral da publicação de aplicativos .net](../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7955-107">For more information, see [.NET application publishing overview](../core/deploying/index.md).</span></span>

## <a name="deploying-a-framework-dependent-app"></a><span data-ttu-id="f7955-108">Implantando um aplicativo dependente de estrutura</span><span class="sxs-lookup"><span data-stu-id="f7955-108">Deploying a framework-dependent app</span></span>

<span data-ttu-id="f7955-109">Para implantar seu aplicativo como um aplicativo dependente de estrutura, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f7955-109">To deploy your app as a framework-dependent app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="f7955-110">Instale o .NET no Raspberry Pi usando os [scripts dotnet-install](../core/tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f7955-110">Install .NET on the Raspberry Pi using the [dotnet-install scripts](../core/tools/dotnet-install-script.md).</span></span> <span data-ttu-id="f7955-111">Conclua as etapas a seguir em um prompt do bash no Raspberry Pi (local ou SSH):</span><span class="sxs-lookup"><span data-stu-id="f7955-111">Complete the following steps from a Bash prompt on the Raspberry Pi (local or SSH):</span></span>
    1. <span data-ttu-id="f7955-112">Execute o seguinte comando para instalar o .NET:</span><span class="sxs-lookup"><span data-stu-id="f7955-112">Run the following command to install .NET:</span></span>

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > <span data-ttu-id="f7955-113">Isso instala a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f7955-113">This installs the latest version.</span></span> <span data-ttu-id="f7955-114">Se você precisar de uma versão específica, adicione `--version <VERSION>` ao final, em que `<VERSION>` é a versão de compilação específica.</span><span class="sxs-lookup"><span data-stu-id="f7955-114">If you need a specific version, add `--version <VERSION>` to the end, where `<VERSION>` is the specific build version.</span></span>

    1. <span data-ttu-id="f7955-115">Para simplificar a resolução de caminho, adicione uma `DOTNET_ROOT` variável de ambiente e adicione o diretório *. dotnet* ao `$PATH` com os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f7955-115">To simplify path resolution, add a `DOTNET_ROOT` environment variable and add the *.dotnet* directory to `$PATH` with the following commands:</span></span>

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. <span data-ttu-id="f7955-116">Verifique a instalação do .NET com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f7955-116">Verify the .NET installation with the following command:</span></span>

        ```dotnetcli
        dotnet --version
        ```

        <span data-ttu-id="f7955-117">Verifique se a versão exibida corresponde à versão instalada.</span><span class="sxs-lookup"><span data-stu-id="f7955-117">Verify the displayed version matches the version you installed.</span></span>

1. <span data-ttu-id="f7955-118">Publique o aplicativo no computador de desenvolvimento da seguinte maneira, dependendo do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="f7955-118">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="f7955-119">Se estiver usando o **Visual Studio**, [implante o aplicativo em uma pasta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="f7955-119">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="f7955-120">Antes de publicar, selecione **Editar** no resumo do perfil de publicação e selecione a guia **configurações** . Verifique se o **modo de implantação** está definido como dependente da *estrutura* e se o tempo de **execução de destino** está definido como *portátil*.</span><span class="sxs-lookup"><span data-stu-id="f7955-120">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Framework-dependent* and **Target runtime** is set to *Portable*.</span></span>
    - <span data-ttu-id="f7955-121">Se estiver usando a **CLI do .net**, use o comando [dotnet Publish](../core/tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="f7955-121">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="f7955-122">Nenhum argumento adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="f7955-122">No additional arguments are required.</span></span>

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="f7955-123">Em um prompt do bash no Raspberry Pi (local ou SSH), execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f7955-123">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="f7955-124">Para fazer isso, defina a pasta de implantação como o diretório atual e execute o seguinte comando (em que *HelloWorld.dll* é o ponto de entrada do aplicativo):</span><span class="sxs-lookup"><span data-stu-id="f7955-124">To do this, set the deployment folder as the current directory and execute the following command (where *HelloWorld.dll* is the entry point of the app):</span></span>

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a><span data-ttu-id="f7955-125">Implantando um aplicativo independente</span><span class="sxs-lookup"><span data-stu-id="f7955-125">Deploying a self-contained app</span></span>

<span data-ttu-id="f7955-126">Para implantar seu aplicativo como um aplicativo independente, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f7955-126">To deploy your app as a self-contained app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="f7955-127">Publique o aplicativo no computador de desenvolvimento da seguinte maneira, dependendo do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="f7955-127">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="f7955-128">Se estiver usando o **Visual Studio**, [implante o aplicativo em uma pasta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="f7955-128">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="f7955-129">Antes de publicar, selecione **Editar** no resumo do perfil de publicação e selecione a guia **configurações** . Verifique se **o modo de implantação** está definido como independente e se o tempo *de* execução de **destino** está definido como *Linux-ARM*.</span><span class="sxs-lookup"><span data-stu-id="f7955-129">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Self-contained* and **Target runtime** is set to *linux-arm*.</span></span>
    - <span data-ttu-id="f7955-130">Se estiver usando a **CLI do .net**, use o comando [dotnet Publish](../core/tools/dotnet-publish.md) com o `-r linux-arm` argumento:</span><span class="sxs-lookup"><span data-stu-id="f7955-130">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command with the `-r linux-arm` argument:</span></span>

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="f7955-131">Em um prompt do bash no Raspberry Pi (local ou SSH), execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f7955-131">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="f7955-132">Para fazer isso, defina o diretório atual para o local de implantação e conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f7955-132">To do this, set the current directory to the deployment location and complete the following steps:</span></span>
    1. <span data-ttu-id="f7955-133">Forneça a permissão *executar* como executável (onde `HelloWorld` é o nome do arquivo executável).</span><span class="sxs-lookup"><span data-stu-id="f7955-133">Give the executable *execute* permission (where `HelloWorld` is the executable file name).</span></span>

        ```bash
        chmod +x HelloWorld
        ```

    1. <span data-ttu-id="f7955-134">Execute o executável.</span><span class="sxs-lookup"><span data-stu-id="f7955-134">Run the executable.</span></span>

        ```bash
        ./HelloWorld
        ```
