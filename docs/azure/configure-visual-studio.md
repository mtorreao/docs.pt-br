---
title: Configurar o Visual Studio para desenvolvimento do Azure com o .NET
description: Este artigo ajuda você a configurar o Visual Studio para desenvolvimento do Azure, incluindo a obtenção das cargas de trabalho corretas instaladas e a conexão do Visual Studio à sua conta do Azure
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701076"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a><span data-ttu-id="a7485-103">Configurar o Visual Studio para desenvolvimento do Azure com o .NET</span><span class="sxs-lookup"><span data-stu-id="a7485-103">Configure Visual Studio for Azure development with .NET</span></span>

<span data-ttu-id="a7485-104">O Visual Studio inclui ferramentas para ajudar no desenvolvimento e na implantação de aplicativos no Azure.</span><span class="sxs-lookup"><span data-stu-id="a7485-104">Visual Studio includes tooling to help with the development and deployment of applications on Azure.</span></span>  <span data-ttu-id="a7485-105">Este guia o ajudará a garantir que você tenha o Visual Studio configurado corretamente para o desenvolvimento do Azure.</span><span class="sxs-lookup"><span data-stu-id="a7485-105">This guide will help you make sure that you have Visual Studio properly configured for Azure development.</span></span>

### <a name="download-visual-studio-2019"></a><span data-ttu-id="a7485-106">Baixar o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a7485-106">Download Visual Studio 2019</span></span>

<span data-ttu-id="a7485-107">Se você já tiver o Visual Studio 2019 instalado, poderá ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="a7485-107">If you already have Visual Studio 2019 installed, you can skip this step.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a7485-108">Baixar o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a7485-108">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a><span data-ttu-id="a7485-109">Instalar cargas de trabalho do Azure</span><span class="sxs-lookup"><span data-stu-id="a7485-109">Install Azure workloads</span></span>

<span data-ttu-id="a7485-110">Inicie o **instalador do Visual Studio** e valide se você tem as cargas de trabalho **desenvolvimento do Azure** e **ASP.net e desenvolvimento da Web** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="a7485-110">Launch the **Visual Studio Installer** and validate that you have the workloads **Azure development** and **ASP.NET and web development** are installed.</span></span>  <span data-ttu-id="a7485-111">Se nenhuma dessas cargas de trabalho não estiver instalada, selecione essas cargas de trabalho para instalá-las.</span><span class="sxs-lookup"><span data-stu-id="a7485-111">If either of these workloads is not installed, select these workloads to install them.</span></span>

![Captura de tela da Instalador do Visual Studio mostrando as cargas de trabalho de desenvolvimento do Azure e ASP.NET e desenvolvimento da Web selecionadas](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a><span data-ttu-id="a7485-113">Autenticar o Visual Studio com o Azure</span><span class="sxs-lookup"><span data-stu-id="a7485-113">Authenticate Visual Studio with Azure</span></span>

<span data-ttu-id="a7485-114">Ao depurar aplicativos por meio do Visual Studio, o Visual Studio pode usar sua conta do Azure para autenticar e acessar recursos do Azure com o.</span><span class="sxs-lookup"><span data-stu-id="a7485-114">When debugging apps through Visual Studio, Visual Studio can use your Azure account to authenticate and access Azure Resources with.</span></span>  <span data-ttu-id="a7485-115">Essa conta também é usada quando você publica aplicativos diretamente do Visual Studio para o Azure.</span><span class="sxs-lookup"><span data-stu-id="a7485-115">This account is also used when you publish apps directly from Visual Studio to Azure.</span></span>

<span data-ttu-id="a7485-116">Para autenticar sua conta do Azure do Visual Studio, selecione o menu opções de **ferramentas**  >   para iniciar a caixa de diálogo **Opções** .</span><span class="sxs-lookup"><span data-stu-id="a7485-116">To authenticate your Azure account from Visual Studio, select the **Tools** > **Options** menu to launch the **Options** dialog.</span></span> <span data-ttu-id="a7485-117">Navegue até as `Azure Service Authentication` Opções e entre usando sua conta do Azure.</span><span class="sxs-lookup"><span data-stu-id="a7485-117">Navigate to the `Azure Service Authentication` options and sign in using your Azure account.</span></span>

![Captura de tela da caixa de diálogo opções do Visual Studio mostrando o logon do Azure](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a><span data-ttu-id="a7485-119">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a7485-119">Next steps</span></span>

<span data-ttu-id="a7485-120">Se você também usar [Visual Studio Code](https://code.visualstudio.com/) para desenvolvimento no .net ou em qualquer outra linguagem, também deverá [Configurar o Visual Studio Code para o desenvolvimento do Azure](./configure-vs-code.md).</span><span class="sxs-lookup"><span data-stu-id="a7485-120">If you also use [Visual Studio Code](https://code.visualstudio.com/) for development in .NET or any other language, you should also [configure Visual Studio Code for Azure development](./configure-vs-code.md).</span></span> <span data-ttu-id="a7485-121">Caso contrário, vá para a [instalação do CLI do Azure](./install-azure-cli.md).</span><span class="sxs-lookup"><span data-stu-id="a7485-121">Otherwise, proceed to [Installing the Azure CLI](./install-azure-cli.md).</span></span>
