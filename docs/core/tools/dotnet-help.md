---
title: Comando dotnet help
description: O comando dotnet help mostra uma documentação mais detalhada online para o comando especificado.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634462"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="270fc-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="270fc-103">dotnet help reference</span></span>

<span data-ttu-id="270fc-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="270fc-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="270fc-105">Name</span><span class="sxs-lookup"><span data-stu-id="270fc-105">Name</span></span>

<span data-ttu-id="270fc-106">`dotnet help` – mostra uma documentação mais detalhada online para o comando especificado.</span><span class="sxs-lookup"><span data-stu-id="270fc-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="270fc-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="270fc-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="270fc-108">Description</span><span class="sxs-lookup"><span data-stu-id="270fc-108">Description</span></span>

<span data-ttu-id="270fc-109">O comando `dotnet help` abre a página de referência para oferecer informações mais detalhadas sobre o comando especificado em docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="270fc-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="270fc-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="270fc-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="270fc-111">Nome do comando da CLI do .NET.</span><span class="sxs-lookup"><span data-stu-id="270fc-111">Name of the .NET CLI command.</span></span> <span data-ttu-id="270fc-112">Para obter uma lista dos comandos válidos da CLI, consulte [CLI commands](index.md#cli-commands) (Comandos da CLI).</span><span class="sxs-lookup"><span data-stu-id="270fc-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="270fc-113">Opções</span><span class="sxs-lookup"><span data-stu-id="270fc-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="270fc-114">Imprime uma ajuda breve para o comando.</span><span class="sxs-lookup"><span data-stu-id="270fc-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="270fc-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="270fc-115">Examples</span></span>

- <span data-ttu-id="270fc-116">Abre a página de documentação do comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="270fc-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
