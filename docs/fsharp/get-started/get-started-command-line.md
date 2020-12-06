---
title: 'Introdução ao F # com ferramentas de linha de comando'
description: 'Saiba como criar uma solução de vários projetos simples em F # usando o CLI do .NET Core em qualquer sistema operacional (Windows, macOS ou Linux).'
ms.date: 08/15/2020
ms.openlocfilehash: f890e31fe8c665874dc3034aebfae32e38b9031a
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739909"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="bc449-103">Introdução ao F # com o CLI do .NET Core</span><span class="sxs-lookup"><span data-stu-id="bc449-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="bc449-104">Este artigo aborda como você pode começar a usar o F # em qualquer sistema operacional (Windows, macOS ou Linux) com o CLI do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bc449-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="bc449-105">Ele passa pela criação de uma solução de vários projetos com uma biblioteca de classes chamada por um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="bc449-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc449-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bc449-106">Prerequisites</span></span>

<span data-ttu-id="bc449-107">Para começar, você deve instalar a [SDK do .NET Core](https://dotnet.microsoft.com/download)mais recente.</span><span class="sxs-lookup"><span data-stu-id="bc449-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="bc449-108">Este artigo pressupõe que você saiba como usar uma linha de comando e ter um editor de texto preferido.</span><span class="sxs-lookup"><span data-stu-id="bc449-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="bc449-109">Se você ainda não o utiliza, [Visual Studio Code](get-started-vscode.md) é uma ótima opção como um editor de texto para F #.</span><span class="sxs-lookup"><span data-stu-id="bc449-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="bc449-110">Criar uma solução simples de vários projetos</span><span class="sxs-lookup"><span data-stu-id="bc449-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="bc449-111">Abra um prompt de comando/terminal e use o comando [dotnet New](../../core/tools/dotnet-new.md) para criar um novo arquivo de solução chamado `FSNetCore` :</span><span class="sxs-lookup"><span data-stu-id="bc449-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="bc449-112">A seguinte estrutura de diretório é produzida após a execução do comando anterior:</span><span class="sxs-lookup"><span data-stu-id="bc449-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="bc449-113">Escrever uma biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="bc449-113">Write a class library</span></span>

<span data-ttu-id="bc449-114">Altere os diretórios para *FSNetCore*.</span><span class="sxs-lookup"><span data-stu-id="bc449-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="bc449-115">Use o `dotnet new` comando, crie um projeto de biblioteca de classes na pasta **src** denominada library.</span><span class="sxs-lookup"><span data-stu-id="bc449-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="bc449-116">A seguinte estrutura de diretório é produzida após a execução do comando anterior:</span><span class="sxs-lookup"><span data-stu-id="bc449-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="bc449-117">Substitua o conteúdo de `Library.fs` pelo código a seguir:</span><span class="sxs-lookup"><span data-stu-id="bc449-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    $"I used to be {value} but now I'm {json} thanks to JSON.NET!"
```

<span data-ttu-id="bc449-118">Adicione o Newtonsoft.Jsno pacote NuGet ao projeto de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bc449-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="bc449-119">Adicione o `Library` projeto à `FSNetCore` solução usando o comando [dotnet DPD Add](../../core/tools/dotnet-sln.md) :</span><span class="sxs-lookup"><span data-stu-id="bc449-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="bc449-120">Execute `dotnet build` para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="bc449-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="bc449-121">As dependências não resolvidas serão restauradas durante a compilação.</span><span class="sxs-lookup"><span data-stu-id="bc449-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="bc449-122">Escrever um aplicativo de console que consome a biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="bc449-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="bc449-123">Use o `dotnet new` comando, crie um aplicativo de console na pasta **src** chamada app.</span><span class="sxs-lookup"><span data-stu-id="bc449-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="bc449-124">A seguinte estrutura de diretório é produzida após a execução do comando anterior:</span><span class="sxs-lookup"><span data-stu-id="bc449-124">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="bc449-125">Substitua o conteúdo do arquivo `Program.fs` pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="bc449-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    for arg in argv do
        let value = getJsonNetJson arg
        printfn $"{value}"

    0 // return an integer exit code
```

<span data-ttu-id="bc449-126">Adicione uma referência ao `Library` projeto usando [dotnet Add Reference](../../core/tools/dotnet-add-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bc449-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="bc449-127">Adicione o `App` projeto à `FSNetCore` solução usando o `dotnet sln add` comando:</span><span class="sxs-lookup"><span data-stu-id="bc449-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="bc449-128">Restaure as dependências do NuGet `dotnet restore` e execute `dotnet build` para compilar o projeto.</span><span class="sxs-lookup"><span data-stu-id="bc449-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="bc449-129">Altere o diretório para o `src/App` projeto de console e execute o projeto passando `Hello World` como argumentos:</span><span class="sxs-lookup"><span data-stu-id="bc449-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```dotnetcli
cd src/App
dotnet run Hello World
```

<span data-ttu-id="bc449-130">Você deve ver o seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="bc449-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="bc449-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bc449-131">Next steps</span></span>

<span data-ttu-id="bc449-132">Em seguida, confira o [Tour do F #](../tour.md) para saber mais sobre os diferentes recursos do F #.</span><span class="sxs-lookup"><span data-stu-id="bc449-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
