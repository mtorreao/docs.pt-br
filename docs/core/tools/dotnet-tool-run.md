---
title: comando de execução da ferramenta dotnet
description: O comando dotnet ferramenta de execução invoca uma ferramenta local.
ms.date: 02/14/2020
ms.openlocfilehash: 116ecb61748a0ca70ed385b279b11b939748f4a8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634149"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="c642f-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="c642f-103">dotnet tool run</span></span>

<span data-ttu-id="c642f-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="c642f-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c642f-105">Name</span><span class="sxs-lookup"><span data-stu-id="c642f-105">Name</span></span>

<span data-ttu-id="c642f-106">`dotnet tool run` -Invoca uma ferramenta local.</span><span class="sxs-lookup"><span data-stu-id="c642f-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c642f-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="c642f-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a><span data-ttu-id="c642f-108">Description</span><span class="sxs-lookup"><span data-stu-id="c642f-108">Description</span></span>

<span data-ttu-id="c642f-109">O `dotnet tool run` comando pesquisa os arquivos de manifesto da ferramenta que estão no escopo do diretório atual.</span><span class="sxs-lookup"><span data-stu-id="c642f-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="c642f-110">Quando ele encontra uma referência à ferramenta especificada, ele executa a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="c642f-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="c642f-111">Para obter mais informações, consulte [invocar uma ferramenta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="c642f-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="c642f-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c642f-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="c642f-113">O nome do comando da ferramenta a ser executada.</span><span class="sxs-lookup"><span data-stu-id="c642f-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="c642f-114">Opções</span><span class="sxs-lookup"><span data-stu-id="c642f-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="c642f-115">Imprime uma ajuda breve para o comando.</span><span class="sxs-lookup"><span data-stu-id="c642f-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="c642f-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c642f-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="c642f-117">Executa a `dotnetsay` ferramenta local.</span><span class="sxs-lookup"><span data-stu-id="c642f-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="c642f-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c642f-118">See also</span></span>

- [<span data-ttu-id="c642f-119">Ferramentas .NET</span><span class="sxs-lookup"><span data-stu-id="c642f-119">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="c642f-120">Tutorial: instalar e usar uma ferramenta local do .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="c642f-120">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
