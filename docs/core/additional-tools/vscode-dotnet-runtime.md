---
title: Ferramenta de instalação do .NET para autores de extensão VS Code
description: Uma visão geral da ferramenta de instalação do .NET para autores de extensão, uma extensão Visual Studio Code para instalar o tempo de execução do .NET.
author: sfoslund
ms.date: 11/18/2020
ms.openlocfilehash: 37be1b9dcdb9fba99554800fea23f28443efb5fa
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599907"
---
# <a name="net-install-tool-for-extension-authors"></a><span data-ttu-id="a90c8-103">Ferramenta de instalação do .NET para autores de extensão</span><span class="sxs-lookup"><span data-stu-id="a90c8-103">.NET install tool for extension authors</span></span>

<span data-ttu-id="a90c8-104">A [ferramenta de instalação do .net para autores de extensão](https://github.com/dotnet/vscode-dotnet-runtime) é uma extensão Visual Studio Code que permite a aquisição do tempo de execução do .net especificamente para autores de extensão vs Code.</span><span class="sxs-lookup"><span data-stu-id="a90c8-104">The [.NET install tool for extension authors](https://github.com/dotnet/vscode-dotnet-runtime) is a Visual Studio Code extension that allows acquisition of the .NET runtime specifically for VS Code extension authors.</span></span> <span data-ttu-id="a90c8-105">Essa ferramenta deve ser utilizada em extensões que são escritas em .NET e exigem que o .NET inicialize as partes da extensão (por exemplo, um servidor de idioma).</span><span class="sxs-lookup"><span data-stu-id="a90c8-105">This tool is intended to be leveraged in extensions that are written in .NET and require .NET to boot pieces of the extension (for example, a language server).</span></span> <span data-ttu-id="a90c8-106">A extensão não deve ser usada diretamente pelos usuários para instalar o .NET para desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a90c8-106">The extension is not intended to be used directly by users to install .NET for development.</span></span>

## <a name="getting-started-extension-authors"></a><span data-ttu-id="a90c8-107">Introdução: autores de extensão</span><span class="sxs-lookup"><span data-stu-id="a90c8-107">Getting started: extension authors</span></span>

<span data-ttu-id="a90c8-108">Para garantir que a ferramenta de instalação do .NET para autores de extensão seja a melhor opção para seu cenário, comece revisando as [metas dessa extensão](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) em nossa página do github.</span><span class="sxs-lookup"><span data-stu-id="a90c8-108">To ensure that the .NET install tool for extension authors is the right fit for your scenario, start by reviewing the [goals of this extension](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) on our GitHub page.</span></span>

> [!NOTE]
> <span data-ttu-id="a90c8-109">Essa ferramenta pode ser usada para instalar somente o tempo de execução do .NET, mas atualmente ele não tem a capacidade de instalar o SDK do .NET.</span><span class="sxs-lookup"><span data-stu-id="a90c8-109">This tool can be used to install the .NET runtime only, it currently does not have the capability to install the .NET SDK.</span></span>

<span data-ttu-id="a90c8-110">Depois de verificar se a ferramenta de instalação do .NET para autores de extensão atende às suas necessidades, você pode assumir uma dependência dele em seu [manifesto de extensão](https://code.visualstudio.com/api/references/extension-manifest) e começar a usar os comandos que expõemos com a [API vs Code](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command).</span><span class="sxs-lookup"><span data-stu-id="a90c8-110">Once you have verified that the .NET install tool for extension authors fits your needs, you can take a dependency on it in your [extension manifest](https://code.visualstudio.com/api/references/extension-manifest) and begin using the commands we expose with the [VS Code API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command).</span></span> <span data-ttu-id="a90c8-111">Você pode encontrar a lista de comandos que essa extensão expõe em nosso [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md).</span><span class="sxs-lookup"><span data-stu-id="a90c8-111">You can find the list of commands this extension exposes on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md).</span></span>

<span data-ttu-id="a90c8-112">Confira esta [extensão de exemplo](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) para ver essas etapas em ação.</span><span class="sxs-lookup"><span data-stu-id="a90c8-112">Check out this [sample extension](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) to see these steps in action.</span></span>

<span data-ttu-id="a90c8-113">Para obter mais exemplos, Confira essas extensões de software livre que atualmente aproveitam essa ferramenta:</span><span class="sxs-lookup"><span data-stu-id="a90c8-113">For more examples, check out these open source extensions that currently leverage this tool:</span></span>

- [<span data-ttu-id="a90c8-114">Ferramentas do Azure Resource Manager (ARM) para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a90c8-114">Azure Resource Manager (ARM) Tools for Visual Studio Code</span></span>](https://github.com/microsoft/vscode-azurearmtools)

- [<span data-ttu-id="a90c8-115">Notebooks interativos do .NET</span><span class="sxs-lookup"><span data-stu-id="a90c8-115">.NET Interactive Notebooks</span></span>](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a><span data-ttu-id="a90c8-116">Introdução: usuários finais</span><span class="sxs-lookup"><span data-stu-id="a90c8-116">Getting started: end users</span></span>

<span data-ttu-id="a90c8-117">Em geral, o usuário final não deve precisar interagir com a ferramenta de instalação do .NET para autores de extensão.</span><span class="sxs-lookup"><span data-stu-id="a90c8-117">In general, the end user should not need to interact with the .NET install tool for extension authors at all.</span></span> <span data-ttu-id="a90c8-118">Se você estiver tendo problemas com a extensão, Confira nossa [página de solução de problemas](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md) ou arquivou um problema em nosso [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).</span><span class="sxs-lookup"><span data-stu-id="a90c8-118">If you are having problems with the extension, check out our [troubleshooting page](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting.md) or file an issue on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).</span></span>
