---
title: Configurar Visual Studio Code para o desenvolvimento do Azure com o .NET
description: Este artigo ajuda você a configurar Visual Studio Code para o desenvolvimento do Azure, incluindo a obtenção dos plug-ins corretos instalados e configurados no VS Code
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701073"
---
# <a name="configure-visual-studio-code-for-azure-development"></a><span data-ttu-id="8f194-103">Configurar Visual Studio Code para o desenvolvimento do Azure</span><span class="sxs-lookup"><span data-stu-id="8f194-103">Configure Visual Studio Code for Azure development</span></span>

<span data-ttu-id="8f194-104">Se você estiver usando Visual Studio Code, seja para o desenvolvimento do .NET, para criar aplicativos de página única usando estruturas como angular, reagir ou Vue ou para escrever aplicativos em outra linguagem, como o Python, você desejará configurar Visual Studio Code para o desenvolvimento do Azure.</span><span class="sxs-lookup"><span data-stu-id="8f194-104">If you are using Visual Studio Code, whether for .NET development, for building single page applications using frameworks like Angular, React or Vue, or for writing applications in another language like Python, you will want to configure Visual Studio Code for Azure development.</span></span>

### <a name="download-visual-studio-code"></a><span data-ttu-id="8f194-105">Baixar o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8f194-105">Download Visual Studio Code</span></span>

<span data-ttu-id="8f194-106">Se você já tiver Visual Studio Code instalado, poderá ignorar esta etapa</span><span class="sxs-lookup"><span data-stu-id="8f194-106">If you already have Visual Studio Code installed, you can skip this step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8f194-107">Baixar o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8f194-107">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a><span data-ttu-id="8f194-108">Instalar o pacote de extensão das ferramentas do Azure</span><span class="sxs-lookup"><span data-stu-id="8f194-108">Install the Azure Tools Extension Pack</span></span>

<span data-ttu-id="8f194-109">O [pacote de extensão das ferramentas do Azure](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contém extensões para trabalhar com Azure app serviço, Azure functions, armazenamento do azure, Cosmos DB e máquinas virtuais do Azure, tudo em um pacote conveniente.</span><span class="sxs-lookup"><span data-stu-id="8f194-109">The [Azure Tools Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contains extensions for working with Azure App Service, Azure Functions, Azure Storage, Cosmos DB, and Azure Virtual Machines all in one convenient package.</span></span>

<span data-ttu-id="8f194-110">Para instalar a extensão de Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="8f194-110">To install the extension from Visual Studio Code:</span></span>

1. <span data-ttu-id="8f194-111">Pressione <kbd>Ctrl + Shift + X</kbd> para abrir a janela **extensões** .</span><span class="sxs-lookup"><span data-stu-id="8f194-111">Press <kbd>Ctrl+Shift+X</kbd> to open the **Extensions** window.</span></span>
1. <span data-ttu-id="8f194-112">Pesquise a extensão de *Ferramentas do Azure* .</span><span class="sxs-lookup"><span data-stu-id="8f194-112">Search for the *Azure Tools* extension.</span></span>
1. <span data-ttu-id="8f194-113">Selecione o botão **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8f194-113">Select the **Install** button.</span></span>

![Captura de tela da Visual Studio Code mostrando o painel de extensões pesquisando o pacote de extensão das ferramentas do Azure](./media/visual-studio-code-azure-tools.png)

<span data-ttu-id="8f194-115">Para saber mais sobre como instalar extensões no Visual Studio Code, consulte o documento de [extensão do Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) no site do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8f194-115">To learn more about installing extensions in Visual Studio Code, refer to the [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) document on the Visual Studio Code website.</span></span>

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a><span data-ttu-id="8f194-116">Entre em sua conta do Azure com as ferramentas do Azure</span><span class="sxs-lookup"><span data-stu-id="8f194-116">Sign in to your Azure account with Azure Tools</span></span>

<span data-ttu-id="8f194-117">No painel esquerdo, você verá um ícone do Azure.</span><span class="sxs-lookup"><span data-stu-id="8f194-117">On the left hand panel, you'll see an Azure icon.</span></span> <span data-ttu-id="8f194-118">Selecione esse ícone e um painel de controle para os serviços do Azure será exibido.</span><span class="sxs-lookup"><span data-stu-id="8f194-118">Select this icon, and a control panel for Azure services will appear.</span></span> <span data-ttu-id="8f194-119">Escolha **entrar no Azure...** em qualquer serviço para concluir o processo de autenticação das ferramentas do Azure no Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8f194-119">Choose **Sign in to Azure...** under any service to complete the authentication process for the Azure tools in Visual Studio Code.</span></span>

![Captura de tela do Visual Studio Code mostrando como fazer logon nas ferramentas do Azure para o Azure](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a><span data-ttu-id="8f194-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8f194-121">Next steps</span></span>

<span data-ttu-id="8f194-122">Em seguida, você desejará instalar o CLI do Azure em sua estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8f194-122">Next, you will want to install the Azure CLI on your workstation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8f194-123">Instalar a CLI do Azure</span><span class="sxs-lookup"><span data-stu-id="8f194-123">Install the Azure CLI</span></span>](./install-azure-cli.md)
