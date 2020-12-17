---
title: Comando dotnet sln
description: O comando dotnet-sln oferece uma opção conveniente para adicionar, remover e listar projetos em um arquivo de solução.
ms.date: 12/07/2020
ms.openlocfilehash: af502efe842e9c9610137738d86c05e00a3b37df
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633644"
---
# <a name="dotnet-sln"></a><span data-ttu-id="99dbb-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="99dbb-103">dotnet sln</span></span>

<span data-ttu-id="99dbb-104">**Este artigo aplica-se a:** ✔️ SDK do .NET Core 2. x e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="99dbb-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="99dbb-105">Nome</span><span class="sxs-lookup"><span data-stu-id="99dbb-105">Name</span></span>

<span data-ttu-id="99dbb-106">`dotnet sln` -Lista ou modifica os projetos em um arquivo de solução .NET.</span><span class="sxs-lookup"><span data-stu-id="99dbb-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="99dbb-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="99dbb-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="99dbb-108">Description</span><span class="sxs-lookup"><span data-stu-id="99dbb-108">Description</span></span>

<span data-ttu-id="99dbb-109">O `dotnet sln` comando fornece uma maneira conveniente de listar e modificar projetos em um arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="99dbb-110">Para usar o comando `dotnet sln`, o arquivo de solução já deve existir.</span><span class="sxs-lookup"><span data-stu-id="99dbb-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="99dbb-111">Se você precisar criar um, use o comando [dotnet New](dotnet-new.md) , como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="99dbb-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="99dbb-112">Arguments</span><span class="sxs-lookup"><span data-stu-id="99dbb-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99dbb-113">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="99dbb-113">The solution file to use.</span></span> <span data-ttu-id="99dbb-114">Se esse argumento for omitido, o comando pesquisará o diretório atual em busca de um.</span><span class="sxs-lookup"><span data-stu-id="99dbb-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="99dbb-115">Se ele não encontrar nenhum arquivo de solução ou vários arquivos de solução, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="99dbb-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="99dbb-116">Opções</span><span class="sxs-lookup"><span data-stu-id="99dbb-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99dbb-117">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="99dbb-118">Comandos</span><span class="sxs-lookup"><span data-stu-id="99dbb-118">Commands</span></span>

### `list`

<span data-ttu-id="99dbb-119">Lista todos os projetos em um arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99dbb-120">Sinopse</span><span class="sxs-lookup"><span data-stu-id="99dbb-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99dbb-121">Arguments</span><span class="sxs-lookup"><span data-stu-id="99dbb-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99dbb-122">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="99dbb-122">The solution file to use.</span></span> <span data-ttu-id="99dbb-123">Se esse argumento for omitido, o comando pesquisará o diretório atual em busca de um.</span><span class="sxs-lookup"><span data-stu-id="99dbb-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="99dbb-124">Se ele não encontrar nenhum arquivo de solução ou vários arquivos de solução, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="99dbb-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="99dbb-125">Opções</span><span class="sxs-lookup"><span data-stu-id="99dbb-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99dbb-126">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="99dbb-127">Adiciona um ou mais projetos ao arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99dbb-128">Sinopse</span><span class="sxs-lookup"><span data-stu-id="99dbb-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99dbb-129">Arguments</span><span class="sxs-lookup"><span data-stu-id="99dbb-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99dbb-130">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="99dbb-130">The solution file to use.</span></span> <span data-ttu-id="99dbb-131">Se não for especificado, o comando pesquisará o diretório atual em busca de um e falhará se houver vários arquivos de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="99dbb-132">O caminho para o projeto ou projetos a serem adicionados à solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="99dbb-133">As expansões de [padrão de mascaramento](https://en.wikipedia.org/wiki/Glob_(programming)) do shell do UNIX/Linux são processadas corretamente pelo `dotnet sln` comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="99dbb-134">Opções</span><span class="sxs-lookup"><span data-stu-id="99dbb-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99dbb-135">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="99dbb-136">Coloca os projetos na raiz da solução, em vez de criar uma pasta de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="99dbb-137">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="99dbb-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="99dbb-138">O caminho da [pasta da solução](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder) de destino para a qual adicionar os projetos.</span><span class="sxs-lookup"><span data-stu-id="99dbb-138">The destination [solution folder](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder) path to add the projects to.</span></span> <span data-ttu-id="99dbb-139">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="99dbb-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="99dbb-140">Remova um projeto ou vários projetos do arquivo da solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="99dbb-141">Sinopse</span><span class="sxs-lookup"><span data-stu-id="99dbb-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="99dbb-142">Arguments</span><span class="sxs-lookup"><span data-stu-id="99dbb-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="99dbb-143">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="99dbb-143">The solution file to use.</span></span> <span data-ttu-id="99dbb-144">Se for Left não especificado, o comando pesquisará o diretório atual em busca de um e falhará se houver vários arquivos de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="99dbb-145">O caminho para o projeto ou projetos a serem adicionados à solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="99dbb-146">As expansões de [padrão de mascaramento](https://en.wikipedia.org/wiki/Glob_(programming)) do shell do UNIX/Linux são processadas corretamente pelo `dotnet sln` comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="99dbb-147">Opções</span><span class="sxs-lookup"><span data-stu-id="99dbb-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="99dbb-148">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="99dbb-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="99dbb-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="99dbb-149">Examples</span></span>

- <span data-ttu-id="99dbb-150">Listar os projetos em uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="99dbb-151">Adicione um projeto C# a uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="99dbb-152">Remova um projeto C# de uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="99dbb-153">Adicione vários projetos C# à raiz de uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="99dbb-154">Adicione vários projetos C# a uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="99dbb-155">Remova vários projetos C# de uma solução:</span><span class="sxs-lookup"><span data-stu-id="99dbb-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="99dbb-156">Adicionar vários projetos C# a uma solução usando um padrão de mascaramento (somente UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="99dbb-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="99dbb-157">Adicionar vários projetos C# a uma solução usando um padrão de mascaramento (somente Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="99dbb-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="99dbb-158">Remover vários projetos C# de uma solução usando um padrão de mascaramento (somente UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="99dbb-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="99dbb-159">Remover vários projetos C# de uma solução usando um padrão de mascaramento (somente Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="99dbb-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```

- <span data-ttu-id="99dbb-160">Crie uma solução, um aplicativo de console e duas bibliotecas de classe.</span><span class="sxs-lookup"><span data-stu-id="99dbb-160">Create a solution, a console app, and two class libraries.</span></span> <span data-ttu-id="99dbb-161">Adicione os projetos à solução e use a `--solution-folder` opção de `dotnet sln` para organizar as bibliotecas de classes em uma pasta de solução.</span><span class="sxs-lookup"><span data-stu-id="99dbb-161">Add the projects to the solution, and use the `--solution-folder` option of `dotnet sln` to organize the class libraries into a solution folder.</span></span>

  ```dotnetcli
  dotnet new sln -n mysolution
  dotnet new console -o myapp
  dotnet new classlib -o mylib1
  dotnet new classlib -o mylib2
  dotnet sln mysolution.sln add myapp\myapp.csproj
  dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
  dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs
  ```

  <span data-ttu-id="99dbb-162">A captura de tela a seguir mostra o resultado no Visual Studio 2019 **Gerenciador de soluções**:</span><span class="sxs-lookup"><span data-stu-id="99dbb-162">The following screenshot shows the result in Visual Studio 2019 **Solution Explorer**:</span></span>

  :::image type="content" source="media/dotnet-sln/dotnet-sln-solution-folder.png" alt-text="Gerenciador de Soluções mostrando projetos de biblioteca de classes agrupados em uma pasta de solução.":::
