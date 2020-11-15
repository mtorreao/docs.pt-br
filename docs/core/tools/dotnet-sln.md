---
title: Comando dotnet sln
description: O comando dotnet-sln oferece uma opção conveniente para adicionar, remover e listar projetos em um arquivo de solução.
ms.date: 02/14/2020
ms.openlocfilehash: 898c53772a28b8cc3b65532dfc3d9bd6e73d467c
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634364"
---
# <a name="dotnet-sln"></a><span data-ttu-id="b8deb-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b8deb-103">dotnet sln</span></span>

<span data-ttu-id="b8deb-104">**Este artigo aplica-se a:** ✔️ SDK do .NET Core 2. x e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="b8deb-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b8deb-105">Name</span><span class="sxs-lookup"><span data-stu-id="b8deb-105">Name</span></span>

<span data-ttu-id="b8deb-106">`dotnet sln` -Lista ou modifica os projetos em um arquivo de solução .NET.</span><span class="sxs-lookup"><span data-stu-id="b8deb-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b8deb-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="b8deb-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="b8deb-108">Description</span><span class="sxs-lookup"><span data-stu-id="b8deb-108">Description</span></span>

<span data-ttu-id="b8deb-109">O `dotnet sln` comando fornece uma maneira conveniente de listar e modificar projetos em um arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="b8deb-110">Para usar o comando `dotnet sln`, o arquivo de solução já deve existir.</span><span class="sxs-lookup"><span data-stu-id="b8deb-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="b8deb-111">Se você precisar criar um, use o comando [dotnet New](dotnet-new.md) , como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8deb-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="b8deb-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8deb-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b8deb-113">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b8deb-113">The solution file to use.</span></span> <span data-ttu-id="b8deb-114">Se esse argumento for omitido, o comando pesquisará o diretório atual em busca de um.</span><span class="sxs-lookup"><span data-stu-id="b8deb-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="b8deb-115">Se ele não encontrar nenhum arquivo de solução ou vários arquivos de solução, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="b8deb-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="b8deb-116">Opções</span><span class="sxs-lookup"><span data-stu-id="b8deb-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b8deb-117">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="b8deb-118">Comandos</span><span class="sxs-lookup"><span data-stu-id="b8deb-118">Commands</span></span>

### `list`

<span data-ttu-id="b8deb-119">Lista todos os projetos em um arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b8deb-120">Sinopse</span><span class="sxs-lookup"><span data-stu-id="b8deb-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b8deb-121">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8deb-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b8deb-122">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b8deb-122">The solution file to use.</span></span> <span data-ttu-id="b8deb-123">Se esse argumento for omitido, o comando pesquisará o diretório atual em busca de um.</span><span class="sxs-lookup"><span data-stu-id="b8deb-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="b8deb-124">Se ele não encontrar nenhum arquivo de solução ou vários arquivos de solução, o comando falhará.</span><span class="sxs-lookup"><span data-stu-id="b8deb-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="b8deb-125">Opções</span><span class="sxs-lookup"><span data-stu-id="b8deb-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b8deb-126">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="b8deb-127">Adiciona um ou mais projetos ao arquivo de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b8deb-128">Sinopse</span><span class="sxs-lookup"><span data-stu-id="b8deb-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b8deb-129">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8deb-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b8deb-130">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b8deb-130">The solution file to use.</span></span> <span data-ttu-id="b8deb-131">Se não for especificado, o comando pesquisará o diretório atual em busca de um e falhará se houver vários arquivos de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="b8deb-132">O caminho para o projeto ou projetos a serem adicionados à solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="b8deb-133">As expansões de [padrão de mascaramento](https://en.wikipedia.org/wiki/Glob_(programming)) do shell do UNIX/Linux são processadas corretamente pelo `dotnet sln` comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="b8deb-134">Opções</span><span class="sxs-lookup"><span data-stu-id="b8deb-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b8deb-135">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="b8deb-136">Coloca os projetos na raiz da solução, em vez de criar uma pasta de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="b8deb-137">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b8deb-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="b8deb-138">O caminho da pasta da solução de destino para a qual adicionar os projetos.</span><span class="sxs-lookup"><span data-stu-id="b8deb-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="b8deb-139">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b8deb-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="b8deb-140">Remova um projeto ou vários projetos do arquivo da solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="b8deb-141">Sinopse</span><span class="sxs-lookup"><span data-stu-id="b8deb-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="b8deb-142">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8deb-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="b8deb-143">O arquivo de solução a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b8deb-143">The solution file to use.</span></span> <span data-ttu-id="b8deb-144">Se for Left não especificado, o comando pesquisará o diretório atual em busca de um e falhará se houver vários arquivos de solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="b8deb-145">O caminho para o projeto ou projetos a serem adicionados à solução.</span><span class="sxs-lookup"><span data-stu-id="b8deb-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="b8deb-146">As expansões de [padrão de mascaramento](https://en.wikipedia.org/wiki/Glob_(programming)) do shell do UNIX/Linux são processadas corretamente pelo `dotnet sln` comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="b8deb-147">Opções</span><span class="sxs-lookup"><span data-stu-id="b8deb-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b8deb-148">Imprime uma descrição de como usar o comando.</span><span class="sxs-lookup"><span data-stu-id="b8deb-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b8deb-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b8deb-149">Examples</span></span>

- <span data-ttu-id="b8deb-150">Listar os projetos em uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="b8deb-151">Adicione um projeto C# a uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="b8deb-152">Remova um projeto C# de uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="b8deb-153">Adicione vários projetos C# à raiz de uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="b8deb-154">Adicione vários projetos C# a uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="b8deb-155">Remova vários projetos C# de uma solução:</span><span class="sxs-lookup"><span data-stu-id="b8deb-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="b8deb-156">Adicionar vários projetos C# a uma solução usando um padrão de mascaramento (somente UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="b8deb-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="b8deb-157">Adicionar vários projetos C# a uma solução usando um padrão de mascaramento (somente Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="b8deb-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="b8deb-158">Remover vários projetos C# de uma solução usando um padrão de mascaramento (somente UNIX/Linux):</span><span class="sxs-lookup"><span data-stu-id="b8deb-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="b8deb-159">Remover vários projetos C# de uma solução usando um padrão de mascaramento (somente Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="b8deb-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```
