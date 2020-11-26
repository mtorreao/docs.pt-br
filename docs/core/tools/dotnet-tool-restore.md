---
title: comando de restauração da ferramenta dotnet
description: O comando dotnet ferramenta de restauração instala em seu computador as ferramentas locais do .NET que estão no escopo para o diretório atual.
ms.date: 02/14/2020
ms.openlocfilehash: 3425bc6b78fd53f578c209013f83b006305dbb81
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242923"
---
# <a name="dotnet-tool-restore"></a><span data-ttu-id="d2749-103">dotnet tool restore</span><span class="sxs-lookup"><span data-stu-id="d2749-103">dotnet tool restore</span></span>

<span data-ttu-id="d2749-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="d2749-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d2749-105">Nome</span><span class="sxs-lookup"><span data-stu-id="d2749-105">Name</span></span>

<span data-ttu-id="d2749-106">`dotnet tool restore` -Instala as ferramentas locais do .NET que estão no escopo do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d2749-106">`dotnet tool restore` - Installs the .NET local tools that are in scope for the current directory.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2749-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="d2749-107">Synopsis</span></span>

```dotnetcli
dotnet tool restore
    [--configfile <FILE>] [--add-source <SOURCE>]
    [tool-manifest <PATH_TO_MANIFEST_FILE>] [--disable-parallel]
    [--ignore-failed-sources] [--no-cache] [--interactive]
    [-v|--verbosity <LEVEL>]

dotnet tool restore -h|--help
```

## <a name="description"></a><span data-ttu-id="d2749-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d2749-108">Description</span></span>

<span data-ttu-id="d2749-109">O `dotnet tool restore` comando localiza o arquivo de manifesto da ferramenta que está no escopo do diretório atual e instala as ferramentas listadas nele.</span><span class="sxs-lookup"><span data-stu-id="d2749-109">The `dotnet tool restore` command finds the tool manifest file that is in scope for the current directory and installs the tools that are listed in it.</span></span> <span data-ttu-id="d2749-110">Para obter informações sobre arquivos de manifesto, consulte [instalar uma ferramenta local](global-tools.md#install-a-local-tool) e [invocar uma ferramenta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="d2749-110">For information about manifest files, see [Install a local tool](global-tools.md#install-a-local-tool) and [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="options"></a><span data-ttu-id="d2749-111">Opções</span><span class="sxs-lookup"><span data-stu-id="d2749-111">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="d2749-112">O arquivo de configuração do NuGet (*nuget.config*) a ser usado.</span><span class="sxs-lookup"><span data-stu-id="d2749-112">The NuGet configuration (*nuget.config*) file to use.</span></span>

- **`--add-source <SOURCE>`**

  <span data-ttu-id="d2749-113">Adiciona outra origem do pacote NuGet a ser usada durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="d2749-113">Adds an additional NuGet package source to use during installation.</span></span>

- **`--tool-manifest <PATH>`**

  <span data-ttu-id="d2749-114">Caminho para o arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="d2749-114">Path to the manifest file.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="d2749-115">Impedir a restauração de vários projetos em paralelo.</span><span class="sxs-lookup"><span data-stu-id="d2749-115">Prevent restoring multiple projects in parallel.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="d2749-116">Tratar falhas de origem do pacote como avisos.</span><span class="sxs-lookup"><span data-stu-id="d2749-116">Treat package source failures as warnings.</span></span>

- **`--no-cache`**

  <span data-ttu-id="d2749-117">Não armazene em cache pacotes e solicitações HTTP.</span><span class="sxs-lookup"><span data-stu-id="d2749-117">Do not cache packages and http requests.</span></span>

- **`--interactive`**

  <span data-ttu-id="d2749-118">Permite que o comando pare e aguarde a entrada ou uma ação do usuário (por exemplo, para concluir a autenticação).</span><span class="sxs-lookup"><span data-stu-id="d2749-118">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span>

- **`-h|--help`**

  <span data-ttu-id="d2749-119">Imprime uma ajuda breve para o comando.</span><span class="sxs-lookup"><span data-stu-id="d2749-119">Prints out a short help for the command.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="d2749-120">Define o nível de detalhes do comando.</span><span class="sxs-lookup"><span data-stu-id="d2749-120">Sets the verbosity level of the command.</span></span> <span data-ttu-id="d2749-121">Os valores permitidos são `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="d2749-121">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="example"></a><span data-ttu-id="d2749-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2749-122">Example</span></span>

- **`dotnet tool restore`**

  <span data-ttu-id="d2749-123">Restaura as ferramentas locais para o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="d2749-123">Restores local tools for the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2749-124">Veja também</span><span class="sxs-lookup"><span data-stu-id="d2749-124">See also</span></span>

- [<span data-ttu-id="d2749-125">Ferramentas .NET</span><span class="sxs-lookup"><span data-stu-id="d2749-125">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="d2749-126">Tutorial: instalar e usar uma ferramenta local do .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="d2749-126">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
