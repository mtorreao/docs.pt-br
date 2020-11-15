---
title: comando de pesquisa da ferramenta dotnet
description: O comando de pesquisa da ferramenta dotnet pesquisa as ferramentas do .NET que são publicadas no NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634136"
---
# <a name="dotnet-tool-search"></a><span data-ttu-id="a06c2-103">dotnet tool search</span><span class="sxs-lookup"><span data-stu-id="a06c2-103">dotnet tool search</span></span>

<span data-ttu-id="a06c2-104">**Este artigo aplica-se a:** ✔️ SDK do .NET 5,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="a06c2-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a06c2-105">Name</span><span class="sxs-lookup"><span data-stu-id="a06c2-105">Name</span></span>

<span data-ttu-id="a06c2-106">`dotnet tool search` -Pesquisa todas as [ferramentas .net](global-tools.md) que são publicadas no NuGet.</span><span class="sxs-lookup"><span data-stu-id="a06c2-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a06c2-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="a06c2-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="a06c2-108">Description</span><span class="sxs-lookup"><span data-stu-id="a06c2-108">Description</span></span>

<span data-ttu-id="a06c2-109">O `dotnet tool search` comando fornece uma maneira de Pesquisar o NuGet para ferramentas que podem ser usadas como .net global, ferramenta-caminho ou ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="a06c2-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="a06c2-110">O comando pesquisa os nomes de ferramentas e os metadados, como títulos, descrições e marcas.</span><span class="sxs-lookup"><span data-stu-id="a06c2-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="a06c2-111">O comando usa a [API de pesquisa do NuGet](/nuget/api/search-query-service-resource#search-for-packages).</span><span class="sxs-lookup"><span data-stu-id="a06c2-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="a06c2-112">Ele filtra `packageType=dotnettool` para selecionar apenas pacotes de ferramentas .net.</span><span class="sxs-lookup"><span data-stu-id="a06c2-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="a06c2-113">Opções</span><span class="sxs-lookup"><span data-stu-id="a06c2-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="a06c2-114">Mostra resultados detalhados da consulta.</span><span class="sxs-lookup"><span data-stu-id="a06c2-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="a06c2-115">Inclui pacotes de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="a06c2-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="a06c2-116">Especifica o número de resultados da consulta a serem ignorados.</span><span class="sxs-lookup"><span data-stu-id="a06c2-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="a06c2-117">Usado para paginação.</span><span class="sxs-lookup"><span data-stu-id="a06c2-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="a06c2-118">Especifica o número de resultados da consulta a serem mostrados.</span><span class="sxs-lookup"><span data-stu-id="a06c2-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="a06c2-119">Usado para paginação.</span><span class="sxs-lookup"><span data-stu-id="a06c2-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a06c2-120">Mostra a ajuda da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a06c2-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="a06c2-121">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a06c2-121">Examples</span></span>

- <span data-ttu-id="a06c2-122">Pesquise NuGet.org para ferramentas .NET que tenham "Format" em seu nome de pacote ou descrição:</span><span class="sxs-lookup"><span data-stu-id="a06c2-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="a06c2-123">A saída se parece com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="a06c2-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="a06c2-124">Pesquise NuGet.org para ferramentas .NET que tenham "formato" em seu nome de pacote ou metadados, mostre apenas o primeiro resultado e mostre uma exibição detalhada.</span><span class="sxs-lookup"><span data-stu-id="a06c2-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="a06c2-125">A saída se parece com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="a06c2-125">The output looks like the following example:</span></span>

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a><span data-ttu-id="a06c2-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a06c2-126">See also</span></span>

- [<span data-ttu-id="a06c2-127">Ferramentas .NET</span><span class="sxs-lookup"><span data-stu-id="a06c2-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="a06c2-128">Tutorial: instalar e usar uma ferramenta global do .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="a06c2-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="a06c2-129">Tutorial: instalar e usar uma ferramenta local do .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="a06c2-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
