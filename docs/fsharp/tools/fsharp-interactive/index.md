---
title: Referência de F# Interativo (dotnet)
description: 'Saiba como F# Interativo (dotNet FSI) é usado para executar o código F # interativamente no console ou para executar scripts em F #.'
ms.date: 11/29/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 92177c41dc6b31d9186bae8176f85787e2fb89e0
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438043"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="618ba-103">Programação interativa com F\#</span><span class="sxs-lookup"><span data-stu-id="618ba-103">Interactive programming with F\#</span></span>

<span data-ttu-id="618ba-104">F# Interativo (dotNet FSI) é usado para executar o código F # interativamente no console ou para executar scripts em F #.</span><span class="sxs-lookup"><span data-stu-id="618ba-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="618ba-105">Em outras palavras, o F# interativo executa um REPL (Ler, Avaliar, Imprimir Loop) para a linguagem F#.</span><span class="sxs-lookup"><span data-stu-id="618ba-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="618ba-106">Para executar o F# Interativo no console do, execute `dotnet fsi` .</span><span class="sxs-lookup"><span data-stu-id="618ba-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="618ba-107">Você encontrará `dotnet fsi` em qualquer SDK do .net.</span><span class="sxs-lookup"><span data-stu-id="618ba-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="618ba-108">Para obter informações sobre opções de linha de comando disponíveis, consulte [Opções de F# interativo](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="618ba-108">For information about available command-line options, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

## <a name="executing-code-directly-in-f-interactive"></a><span data-ttu-id="618ba-109">Executando o código diretamente no F# Interativo</span><span class="sxs-lookup"><span data-stu-id="618ba-109">Executing code directly in F# Interactive</span></span>

<span data-ttu-id="618ba-110">Como F# Interativo é uma REPL (loop Read-eval-Print), você pode executar o código interativamente nele.</span><span class="sxs-lookup"><span data-stu-id="618ba-110">Because F# Interactive is a REPL (read-eval-print loop), you can execute code interactively in it.</span></span> <span data-ttu-id="618ba-111">Aqui está um exemplo de uma sessão interativa após `dotnet fsi` a execução na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="618ba-111">Here is an example of an interactive session after executing `dotnet fsi` from the command line:</span></span>

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

<span data-ttu-id="618ba-112">Você observará duas coisas principais:</span><span class="sxs-lookup"><span data-stu-id="618ba-112">You'll notice two main things:</span></span>

1. <span data-ttu-id="618ba-113">Todo o código deve ser encerrado com um ponto-e-vírgula duplo ( `;;` ) a ser avaliado</span><span class="sxs-lookup"><span data-stu-id="618ba-113">All code must be terminated with a double semicolon (`;;`) to be evaluated</span></span>
2. <span data-ttu-id="618ba-114">O código é avaliado e armazenado em um `it` valor.</span><span class="sxs-lookup"><span data-stu-id="618ba-114">Code is evaluated and stored in an `it` value.</span></span> <span data-ttu-id="618ba-115">Você pode fazer referência `it` interativamente.</span><span class="sxs-lookup"><span data-stu-id="618ba-115">You can reference `it` interactively.</span></span>

<span data-ttu-id="618ba-116">F# Interativo também dá suporte à entrada de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="618ba-116">F# Interactive also supports multi-line input.</span></span> <span data-ttu-id="618ba-117">Você só precisa encerrar o envio com um ponto-e-vírgula duplo ( `;;` ).</span><span class="sxs-lookup"><span data-stu-id="618ba-117">You just need to terminate your submission with a double semicolon (`;;`).</span></span> <span data-ttu-id="618ba-118">Considere o trecho a seguir que foi colado e avaliado por F# Interativo:</span><span class="sxs-lookup"><span data-stu-id="618ba-118">Consider the following snippet that has been pasted into and evaluated by F# Interactive:</span></span>

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

<span data-ttu-id="618ba-119">A formatação do código é preservada e há um ponto-e-vírgula duplo ( `;;` ) encerrando a entrada.</span><span class="sxs-lookup"><span data-stu-id="618ba-119">The code's formatting is preserved, and there is a double semicolon (`;;`) terminating the input.</span></span> <span data-ttu-id="618ba-120">F# Interativo, em seguida, avaliou o código e imprimiu os resultados!</span><span class="sxs-lookup"><span data-stu-id="618ba-120">F# Interactive then evaluated the code and printed the results!</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="618ba-121">Criando scripts com o F\#</span><span class="sxs-lookup"><span data-stu-id="618ba-121">Scripting with F\#</span></span>

<span data-ttu-id="618ba-122">Avaliar o código interativamente no F# Interativo pode ser uma excelente ferramenta de aprendizado, mas você descobrirá rapidamente que não é tão produtivo quanto escrever código em um editor normal.</span><span class="sxs-lookup"><span data-stu-id="618ba-122">Evaluating code interactively in F# Interactive can be a great learning tool, but you'll quickly find that it's not as productive as writing code in a normal editor.</span></span> <span data-ttu-id="618ba-123">Para dar suporte à edição de código normal, você pode escrever scripts em F #.</span><span class="sxs-lookup"><span data-stu-id="618ba-123">To support normal code editing, you can write F# scripts.</span></span>

<span data-ttu-id="618ba-124">Os scripts usam a extensão de arquivo **. fsx**.</span><span class="sxs-lookup"><span data-stu-id="618ba-124">Scripts use the file extension **.fsx**.</span></span> <span data-ttu-id="618ba-125">Em vez de compilar o código-fonte e, posteriormente, executar o assembly compilado, você pode apenas executar **dotnet FSI** e especificar o nome de arquivo do script do código-fonte f # e o f # Interactive lê o código e o executa em tempo real.</span><span class="sxs-lookup"><span data-stu-id="618ba-125">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span> <span data-ttu-id="618ba-126">Por exemplo, considere o script a seguir chamado `Script.fsx` :</span><span class="sxs-lookup"><span data-stu-id="618ba-126">For example, consider the following script called `Script.fsx`:</span></span>

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

printfn "%A" (getOddSquares [1..10])
```

<span data-ttu-id="618ba-127">Quando esse arquivo é criado em seu computador, você pode executá-lo com `dotnet fsi` e ver a saída diretamente na janela do seu terminal:</span><span class="sxs-lookup"><span data-stu-id="618ba-127">When this file is created in your machine, you can run it with `dotnet fsi` and see the output directly in your terminal window:</span></span>

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

<span data-ttu-id="618ba-128">O script F # tem suporte nativo no [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md)e [Visual Studio para Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span><span class="sxs-lookup"><span data-stu-id="618ba-128">F# scripting is natively supported in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md), and [Visual Studio for Mac](../../get-started/get-started-with-visual-studio-for-mac.md).</span></span>

## <a name="referencing-packages-in-f-interactive"></a><span data-ttu-id="618ba-129">Referenciando pacotes no F# Interativo</span><span class="sxs-lookup"><span data-stu-id="618ba-129">Referencing packages in F# Interactive</span></span>

<span data-ttu-id="618ba-130">O F# Interativo dá suporte à referência de pacotes NuGet com a `#r "nuget:"` sintaxe e uma versão opcional:</span><span class="sxs-lookup"><span data-stu-id="618ba-130">F# Interactive supports referencing NuGet packages with the `#r "nuget:"` syntax and an optional version:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

<span data-ttu-id="618ba-131">Se uma versão não for especificada, o pacote de não visualização mais alto disponível será obtido.</span><span class="sxs-lookup"><span data-stu-id="618ba-131">If a version is not specified, the highest available non-preview package is taken.</span></span> <span data-ttu-id="618ba-132">Para fazer referência a uma versão específica, introduza a versão por vírgula.</span><span class="sxs-lookup"><span data-stu-id="618ba-132">To reference a specific version, introduce the version via a comma.</span></span> <span data-ttu-id="618ba-133">Isso pode ser útil ao fazer referência a uma versão de visualização de um pacote.</span><span class="sxs-lookup"><span data-stu-id="618ba-133">This can be handy when referencing a preview version of a package.</span></span> <span data-ttu-id="618ba-134">Por exemplo, considere este script usando uma versão de visualização do [DiffSharp](https://diffsharp.github.io/):</span><span class="sxs-lookup"><span data-stu-id="618ba-134">For example, consider this script using a preview version of [DiffSharp](https://diffsharp.github.io/):</span></span>

```fsharp
#r "nuget: DiffSharp-lite, 1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

### <a name="specifying-a-package-source"></a><span data-ttu-id="618ba-135">Especificando uma origem de pacote</span><span class="sxs-lookup"><span data-stu-id="618ba-135">Specifying a package source</span></span>

<span data-ttu-id="618ba-136">Você também pode especificar uma origem de pacote com o `#i` comando.</span><span class="sxs-lookup"><span data-stu-id="618ba-136">You can also specify a package source with the `#i` command.</span></span> <span data-ttu-id="618ba-137">O exemplo a seguir especifica uma fonte remota e local:</span><span class="sxs-lookup"><span data-stu-id="618ba-137">The following example specifies a remote and a local source:</span></span>

```fsharp
#i "nuget:https://my-remote-package-source/index.json
#i @"path-to-my-local-source"
```

<span data-ttu-id="618ba-138">Isso fará com que o mecanismo de resolução nos bastidores também leve em consideração as fontes remotas e/ou locais adicionadas a um script.</span><span class="sxs-lookup"><span data-stu-id="618ba-138">This will tell the resolution engine under the covers to also take into account the remote and/or local sources added to a script.</span></span>

<span data-ttu-id="618ba-139">Você pode especificar quantas referências de pacote desejar em um script.</span><span class="sxs-lookup"><span data-stu-id="618ba-139">You can specify as many package references as you like in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="618ba-140">Atualmente, há uma limitação para scripts que usam referências de estrutura (por exemplo, `Microsoft.NET.Sdk.Web` ou  `Microsoft.NET.Sdk.WindowsDesktop` ).</span><span class="sxs-lookup"><span data-stu-id="618ba-140">There's currently a limitation for scripts that use framework references (e.g.`Microsoft.NET.Sdk.Web` or  `Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="618ba-141">Pacotes como Saturn, Giraffe, WinForms não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="618ba-141">Packages like Saturn, Giraffe, WinForms are not available.</span></span> <span data-ttu-id="618ba-142">Isso está sendo acompanhado em questão [#9417](https://github.com/dotnet/fsharp/issues/9417).</span><span class="sxs-lookup"><span data-stu-id="618ba-142">This is being tracked in issue [#9417](https://github.com/dotnet/fsharp/issues/9417).</span></span>

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a><span data-ttu-id="618ba-143">Referenciando assemblies em disco com F # interativo</span><span class="sxs-lookup"><span data-stu-id="618ba-143">Referencing assemblies on disk with F# interactive</span></span>

<span data-ttu-id="618ba-144">Como alternativa, se você tiver um assembly em disco e desejar fazer referência a ele em um script, você poderá usar a `#r` sintaxe para especificar um assembly.</span><span class="sxs-lookup"><span data-stu-id="618ba-144">Alternatively, if you have an assembly on disk and wish to reference that in a script, you can use the `#r` syntax to specify an assembly.</span></span> <span data-ttu-id="618ba-145">Considere o seguinte código em um projeto compilado em `MyAssembly.dll` :</span><span class="sxs-lookup"><span data-stu-id="618ba-145">Consider the following code in a project compiled into `MyAssembly.dll`:</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

<span data-ttu-id="618ba-146">Um compilado, você pode fazer referência a ele em um arquivo chamado da `Script.fsx` seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="618ba-146">One compiled, you can reference it in a file called `Script.fsx` like so:</span></span>

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="618ba-147">A saída é da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="618ba-147">The output is as follows:</span></span>

```console
dotnet fsi Script.fsx
90
```

<span data-ttu-id="618ba-148">Você pode especificar quantas referências de assembly desejar em um script.</span><span class="sxs-lookup"><span data-stu-id="618ba-148">You can specify as many assembly references as you like in a script.</span></span>

## <a name="loading-other-scripts"></a><span data-ttu-id="618ba-149">Carregando outros scripts</span><span class="sxs-lookup"><span data-stu-id="618ba-149">Loading other scripts</span></span>

<span data-ttu-id="618ba-150">Ao criar scripts, muitas vezes pode ser útil usar scripts diferentes para tarefas diferentes.</span><span class="sxs-lookup"><span data-stu-id="618ba-150">When scripting, it can often be helpful to use different scripts for different tasks.</span></span> <span data-ttu-id="618ba-151">Às vezes, talvez você queira reutilizar o código do script em outro.</span><span class="sxs-lookup"><span data-stu-id="618ba-151">Sometimes you may want to reuse code from on script in another.</span></span> <span data-ttu-id="618ba-152">Em vez de copiar e colar seu conteúdo em seu arquivo, você pode carregar simples e avaliá-lo com `#load` .</span><span class="sxs-lookup"><span data-stu-id="618ba-152">Rather than copy-pasting its contents into your file, you can simple load and evaluate it with `#load`.</span></span>

<span data-ttu-id="618ba-153">Considere o seguinte `Script1.fsx` :</span><span class="sxs-lookup"><span data-stu-id="618ba-153">Consider the following `Script1.fsx`:</span></span>

```fsharp
let square x = x * x
```

<span data-ttu-id="618ba-154">E o arquivo de consumo, `Script2.fsx` :</span><span class="sxs-lookup"><span data-stu-id="618ba-154">And the consuming file, `Script2.fsx`:</span></span>

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

<span data-ttu-id="618ba-155">Observe que a `open Script1` declaração é necessária.</span><span class="sxs-lookup"><span data-stu-id="618ba-155">Note that the `open Script1` declaration is required.</span></span> <span data-ttu-id="618ba-156">Isso ocorre porque as construções em um script F # são compiladas em um módulo de nível superior que é o nome do arquivo de script em que se encontra.</span><span class="sxs-lookup"><span data-stu-id="618ba-156">This is because constructs in an F# script are compiled into a top-level module that is the name of the script file it is in.</span></span>

<span data-ttu-id="618ba-157">Você pode avaliar da `Script2.fsx` seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="618ba-157">You can evaluate `Script2.fsx` like so:</span></span>

```console
dotnet fsi Script2.fsx
144
```

<span data-ttu-id="618ba-158">Você pode especificar quantas `#load` diretivas desejar em um script.</span><span class="sxs-lookup"><span data-stu-id="618ba-158">You can specify as many `#load` directives as you like in a script.</span></span>

## <a name="using-the-fsi-object-in-f-code"></a><span data-ttu-id="618ba-159">Usando o `fsi` objeto no código F #</span><span class="sxs-lookup"><span data-stu-id="618ba-159">Using the `fsi` object in F# code</span></span>

<span data-ttu-id="618ba-160">Os scripts F # têm acesso a um `fsi` objeto personalizado que representa a sessão de F# interativo.</span><span class="sxs-lookup"><span data-stu-id="618ba-160">F# scripts have access to a custom `fsi` object that represents the F# Interactive session.</span></span> <span data-ttu-id="618ba-161">Ele permite que você personalize coisas como formatação de saída.</span><span class="sxs-lookup"><span data-stu-id="618ba-161">It allows you to customize things like output formatting.</span></span> <span data-ttu-id="618ba-162">Também é como você pode acessar argumentos de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="618ba-162">It is also how you can access command-line arguments.</span></span>

<span data-ttu-id="618ba-163">O exemplo a seguir mostra como obter e usar argumentos de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="618ba-163">The following example shows how to get and use command-line arguments:</span></span>

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

<span data-ttu-id="618ba-164">Quando avaliado, ele imprime todos os argumentos.</span><span class="sxs-lookup"><span data-stu-id="618ba-164">When evaluated, it prints all arguments.</span></span> <span data-ttu-id="618ba-165">O primeiro argumento é sempre o nome do script que é avaliado:</span><span class="sxs-lookup"><span data-stu-id="618ba-165">The first argument is always the name of the script that is evaluated:</span></span>

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

<span data-ttu-id="618ba-166">Você também pode usar `System.Environment.GetCommandLineArgs()` o para acessar os mesmos argumentos.</span><span class="sxs-lookup"><span data-stu-id="618ba-166">You can also use `System.Environment.GetCommandLineArgs()` to access the same arguments.</span></span>

## <a name="f-interactive-directive-reference"></a><span data-ttu-id="618ba-167">Referência de diretiva de F# Interativo</span><span class="sxs-lookup"><span data-stu-id="618ba-167">F# Interactive directive reference</span></span>

<span data-ttu-id="618ba-168">As `#r` `#load` diretivas e vistas anteriormente só estão disponíveis no F# interativo.</span><span class="sxs-lookup"><span data-stu-id="618ba-168">The `#r` and `#load` directives seen previously are only available in F# Interactive.</span></span> <span data-ttu-id="618ba-169">Há várias diretivas disponíveis somente no F# Interativo:</span><span class="sxs-lookup"><span data-stu-id="618ba-169">There are several directives only available in F# Interactive:</span></span>

|<span data-ttu-id="618ba-170">Diretiva</span><span class="sxs-lookup"><span data-stu-id="618ba-170">Directive</span></span>|<span data-ttu-id="618ba-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="618ba-171">Description</span></span>|
|---------|-----------|
|`#r "nuget:..."`|<span data-ttu-id="618ba-172">Referencia um pacote do NuGet</span><span class="sxs-lookup"><span data-stu-id="618ba-172">References a package from NuGet</span></span>|
|`#r "assembly-name.dll"`|<span data-ttu-id="618ba-173">Faz referência a um assembly no disco</span><span class="sxs-lookup"><span data-stu-id="618ba-173">References an assembly on disk</span></span>|
|`#load "file-name.fsx"`|<span data-ttu-id="618ba-174">Lê um arquivo de origem, compila e o executa.</span><span class="sxs-lookup"><span data-stu-id="618ba-174">Reads a source file, compiles it, and runs it.</span></span>|
|`#help`|<span data-ttu-id="618ba-175">Exibe informações sobre as diretivas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="618ba-175">Displays information about available directives.</span></span>|
|`#I`|<span data-ttu-id="618ba-176">Especifica um caminho de pesquisa de assembly entre aspas.</span><span class="sxs-lookup"><span data-stu-id="618ba-176">Specifies an assembly search path in quotation marks.</span></span>|
|`#quit`|<span data-ttu-id="618ba-177">Finaliza uma sessão do F# interativo.</span><span class="sxs-lookup"><span data-stu-id="618ba-177">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="618ba-178">`#time "on"` ou `#time "off"`</span><span class="sxs-lookup"><span data-stu-id="618ba-178">`#time "on"` or `#time "off"`</span></span>|<span data-ttu-id="618ba-179">Por si só, `#time` alterna se as informações de desempenho devem ser exibidas.</span><span class="sxs-lookup"><span data-stu-id="618ba-179">By itself, `#time` toggles whether to display performance information.</span></span> <span data-ttu-id="618ba-180">Quando é `"on"` , F# interativo mede as informações em tempo real, tempo de CPU e coleta de lixo para cada seção de código que é interpretada e executada.</span><span class="sxs-lookup"><span data-stu-id="618ba-180">When it is `"on"`, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="618ba-181">Quando você especificar arquivos ou caminhos em F# interativo, uma sequência literal é esperada.</span><span class="sxs-lookup"><span data-stu-id="618ba-181">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="618ba-182">Portanto, arquivos e caminhos devem estar entre aspas e os caracteres de escape comuns se aplicam.</span><span class="sxs-lookup"><span data-stu-id="618ba-182">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="618ba-183">Você pode usar o `@` caractere para fazer com que F# interativo interprete uma cadeia de caracteres que contém um caminho como uma cadeia de caracteres textual.</span><span class="sxs-lookup"><span data-stu-id="618ba-183">You can use the `@` character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="618ba-184">Isso faz com que o F# interativo ignore quaisquer caracteres de escape.</span><span class="sxs-lookup"><span data-stu-id="618ba-184">This causes F# Interactive to ignore any escape characters.</span></span>

## <a name="interactive-and-compiled-preprocessor-directives"></a><span data-ttu-id="618ba-185">Diretivas de pré-processador interativo e compilado</span><span class="sxs-lookup"><span data-stu-id="618ba-185">Interactive and compiled preprocessor directives</span></span>

<span data-ttu-id="618ba-186">Quando você compila o código no F# Interativo, quer você esteja executando interativamente ou executando um script, o símbolo **interativo** é definido.</span><span class="sxs-lookup"><span data-stu-id="618ba-186">When you compile code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="618ba-187">Quando você compila o código no compilador, o símbolo **compilado** é definido.</span><span class="sxs-lookup"><span data-stu-id="618ba-187">When you compile code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="618ba-188">Portanto, se o código precisar ser diferente em modos compilados e interativos, você poderá usar essas diretivas de pré-processador para compilação condicional para determinar qual delas usar.</span><span class="sxs-lookup"><span data-stu-id="618ba-188">Thus, if code needs to be different in compiled and interactive modes, you can use these preprocessor directives for conditional compilation to determine which to use.</span></span> <span data-ttu-id="618ba-189">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="618ba-189">For example:</span></span>

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a><span data-ttu-id="618ba-190">Usando F# Interativo no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="618ba-190">Using F# Interactive in Visual Studio</span></span>

<span data-ttu-id="618ba-191">Para executar o F# Interativo por meio do Visual Studio, você pode clicar no botão de barra de ferramentas apropriado rotulado como **F# Interativo** ou usar as teclas **Ctrl+Alt+F**.</span><span class="sxs-lookup"><span data-stu-id="618ba-191">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="618ba-192">Isso abrirá a janela interativa, uma janela da ferramenta que executa uma sessão de F# interativo.</span><span class="sxs-lookup"><span data-stu-id="618ba-192">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="618ba-193">Você também pode selecionar um código que deseja executar na janela interativa e pressionar a combinação de teclas **ALT + Enter**.</span><span class="sxs-lookup"><span data-stu-id="618ba-193">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="618ba-194">O F# interativo é iniciado em uma janela da ferramenta rotulada como **F# Interativo**.</span><span class="sxs-lookup"><span data-stu-id="618ba-194">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="618ba-195">Quando você usar essa combinação de teclas, certifique-se de que a janela do editor tenha o foco.</span><span class="sxs-lookup"><span data-stu-id="618ba-195">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="618ba-196">Se você estiver usando o console ou o Visual Studio, será exibido um prompt de comando e o interpretador aguardará a entrada.</span><span class="sxs-lookup"><span data-stu-id="618ba-196">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="618ba-197">Você pode inserir o código como faria em um arquivo de código.</span><span class="sxs-lookup"><span data-stu-id="618ba-197">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="618ba-198">Para compilar e executar o código, insira dois sinais de ponto e vírgula (**;;**) para terminar uma linha ou várias linhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="618ba-198">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="618ba-199">O F# interativo tenta compilar o código e, se tiver êxito, executará o código e imprimirá a assinatura dos tipos e valores que ele compilou.</span><span class="sxs-lookup"><span data-stu-id="618ba-199">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="618ba-200">Se ocorrerem erros, o interpretador imprime as mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="618ba-200">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="618ba-201">O código digitado na mesma sessão tem acesso a quaisquer construções inseridas anteriormente, para poder criar os programas.</span><span class="sxs-lookup"><span data-stu-id="618ba-201">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="618ba-202">Um buffer extensivo na janela da ferramenta permite que você copie o código para um arquivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="618ba-202">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="618ba-203">Quando executado no Visual Studio, o F# interativo é executado independentemente do seu projeto, então, por exemplo, não é possível usar construções definidas em seu projeto em F# interativo, a menos que você copie o código para a função na janela interativa.</span><span class="sxs-lookup"><span data-stu-id="618ba-203">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="618ba-204">Você pode controlar a F# Interativo argumentos de linha de comando (opções) ajustando as configurações.</span><span class="sxs-lookup"><span data-stu-id="618ba-204">You can control the F# Interactive command-line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="618ba-205">No menu **Ferramentas**, selecione **Opções...** e expanda **Ferramentas do F#**.</span><span class="sxs-lookup"><span data-stu-id="618ba-205">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="618ba-206">As duas configurações que podem ser alteradas são as opções do F# interativo e a configuração do **F# Interativo de 64 bits**, que é relevante apenas se você estiver executando o F# interativo em uma máquina de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="618ba-206">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="618ba-207">Essa configuração determina se você deseja executar a versão dedicada de 64 bits do **fsi.exe** ou **fsianycpu.exe**, que usa a arquitetura do computador para determinar se deve ser executado como um processo de 32 ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="618ba-207">This setting determines whether you want to run the dedicated 64-bit version of **fsi.exe** or **fsianycpu.exe**, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="related-articles"></a><span data-ttu-id="618ba-208">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="618ba-208">Related articles</span></span>

|<span data-ttu-id="618ba-209">Título</span><span class="sxs-lookup"><span data-stu-id="618ba-209">Title</span></span>|<span data-ttu-id="618ba-210">Descrição</span><span class="sxs-lookup"><span data-stu-id="618ba-210">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="618ba-211">Opções do F# Interativo</span><span class="sxs-lookup"><span data-stu-id="618ba-211">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="618ba-212">Descreve a sintaxe de linha de comando e as opções para o F# Interativo, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="618ba-212">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
