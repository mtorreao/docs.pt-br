---
title: Novidades do .NET 5
description: Saiba mais sobre o .NET 5, uma plataforma de desenvolvimento de plataforma cruzada e de software livre que é a próxima evolução do .NET Core.
ms.date: 11/30/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: 7984f235044db5dfc7533343e7d43cd7745fba33
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899450"
---
# <a name="whats-new-in-net-5"></a><span data-ttu-id="75f14-103">Novidades do .NET 5</span><span class="sxs-lookup"><span data-stu-id="75f14-103">What's new in .NET 5</span></span>

<span data-ttu-id="75f14-104">O .NET 5,0 é a próxima versão principal do .NET Core a seguir 3,1.</span><span class="sxs-lookup"><span data-stu-id="75f14-104">.NET 5.0 is the next major release of .NET Core following 3.1.</span></span> <span data-ttu-id="75f14-105">Nomeamos essa nova versão do .NET 5,0 em vez do .NET Core 4,0 por dois motivos:</span><span class="sxs-lookup"><span data-stu-id="75f14-105">We named this new release .NET 5.0 instead of .NET Core 4.0 for two reasons:</span></span>

- <span data-ttu-id="75f14-106">Ignoramos os números de versão 4. x para evitar confusão com .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="75f14-106">We skipped version numbers 4.x to avoid confusion with .NET Framework 4.x.</span></span>
- <span data-ttu-id="75f14-107">Descartamos "Core" do nome para enfatizar que esta é a principal implementação do .NET em diante.</span><span class="sxs-lookup"><span data-stu-id="75f14-107">We dropped "Core" from the name to emphasize that this is the main implementation of .NET going forward.</span></span> <span data-ttu-id="75f14-108">O .NET 5,0 dá suporte a mais tipos de aplicativos e mais plataformas do que o .NET Core ou o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75f14-108">.NET 5.0 supports more types of apps and more platforms than .NET Core or .NET Framework.</span></span>

<span data-ttu-id="75f14-109">ASP.NET Core 5,0 é baseado no .NET 5,0, mas mantém o nome "Core" para evitar confusão com o ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="75f14-109">ASP.NET Core 5.0 is based on .NET 5.0 but retains the name "Core" to avoid confusing it with ASP.NET MVC 5.</span></span> <span data-ttu-id="75f14-110">Da mesma forma, Entity Framework Core 5,0 mantém o nome "Core" para evitar confusão com Entity Framework 5 e 6.</span><span class="sxs-lookup"><span data-stu-id="75f14-110">Likewise, Entity Framework Core 5.0 retains the name "Core" to avoid confusing it with Entity Framework 5 and 6.</span></span>

<span data-ttu-id="75f14-111">O .NET 5,0 inclui os seguintes aprimoramentos e novos recursos em comparação com o .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="75f14-111">.NET 5.0 includes the following improvements and new features compared to .NET Core 3.1:</span></span>

- [<span data-ttu-id="75f14-112">Atualizações em C#</span><span class="sxs-lookup"><span data-stu-id="75f14-112">C# updates</span></span>](#c-updates)
- [<span data-ttu-id="75f14-113">Atualizações de F #</span><span class="sxs-lookup"><span data-stu-id="75f14-113">F# updates</span></span>](#f-updates)
- [<span data-ttu-id="75f14-114">Atualizações de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75f14-114">Visual Basic updates</span></span>](#visual-basic-updates)
- [<span data-ttu-id="75f14-115">System.Text.Jssobre novos recursos</span><span class="sxs-lookup"><span data-stu-id="75f14-115">System.Text.Json new features</span></span>](#systemtextjson-new-features)
- [<span data-ttu-id="75f14-116">Aplicativos de arquivo único</span><span class="sxs-lookup"><span data-stu-id="75f14-116">Single file apps</span></span>](deploying/single-file.md)
- [<span data-ttu-id="75f14-117">Corte de aplicativo</span><span class="sxs-lookup"><span data-stu-id="75f14-117">App trimming</span></span>](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- <span data-ttu-id="75f14-118">Intrínsecos do Windows ARM64 e ARM64</span><span class="sxs-lookup"><span data-stu-id="75f14-118">Windows ARM64 and ARM64 intrinsics</span></span>
- <span data-ttu-id="75f14-119">Suporte de ferramentas para depuração de despejo</span><span class="sxs-lookup"><span data-stu-id="75f14-119">Tooling support for dump debugging</span></span>
- <span data-ttu-id="75f14-120">As bibliotecas de tempo de execução são 80% anotadas para [tipos de referência anuláveis](../csharp/nullable-references.md)</span><span class="sxs-lookup"><span data-stu-id="75f14-120">The runtime libraries are 80% annotated for [nullable reference types](../csharp/nullable-references.md)</span></span>
- <span data-ttu-id="75f14-121">Aprimoramentos de desempenho:</span><span class="sxs-lookup"><span data-stu-id="75f14-121">Performance improvements:</span></span>
  - [<span data-ttu-id="75f14-122">Coleta de lixo (GC)</span><span class="sxs-lookup"><span data-stu-id="75f14-122">Garbage Collection (GC)</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [<span data-ttu-id="75f14-123">System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="75f14-123">System.Text.Json</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [<span data-ttu-id="75f14-124">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="75f14-124">System.Text.RegularExpressions</span></span>](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [<span data-ttu-id="75f14-125">Pooling ValueTask assíncrona</span><span class="sxs-lookup"><span data-stu-id="75f14-125">Async ValueTask pooling</span></span>](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [<span data-ttu-id="75f14-126">Otimizações de tamanho de contêiner</span><span class="sxs-lookup"><span data-stu-id="75f14-126">Container size optimizations</span></span>](https://github.com/dotnet/dotnet-docker/issues/1814#issuecomment-625294750)
  - [<span data-ttu-id="75f14-127">Muito mais áreas</span><span class="sxs-lookup"><span data-stu-id="75f14-127">Many more areas</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)

## <a name="net-50-doesnt-replace-net-framework"></a><span data-ttu-id="75f14-128">O .NET 5,0 não substitui .NET Framework</span><span class="sxs-lookup"><span data-stu-id="75f14-128">.NET 5.0 doesn't replace .NET Framework</span></span>

<span data-ttu-id="75f14-129">O .NET 5,0 é a principal implementação do .NET no futuro e .NET Framework 4. x ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="75f14-129">.NET 5.0 is the main implementation of .NET going forward and .NET Framework 4.x is still supported.</span></span>

<span data-ttu-id="75f14-130">Não há planos de portar as tecnologias a seguir de .NET Framework para o .NET 5,0, mas há alternativas no .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="75f14-130">There are no plans to port the following technologies from .NET Framework to .NET 5.0, but there are alternatives in .NET 5.0:</span></span>

| <span data-ttu-id="75f14-131">Tecnologia</span><span class="sxs-lookup"><span data-stu-id="75f14-131">Technology</span></span>            | <span data-ttu-id="75f14-132">Alternativa recomendada</span><span class="sxs-lookup"><span data-stu-id="75f14-132">Recommended alternative</span></span>                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="75f14-133">Web Forms</span><span class="sxs-lookup"><span data-stu-id="75f14-133">Web Forms</span></span>             | <span data-ttu-id="75f14-134">ASP.NET Core [mais](/aspnet/core/blazor) ou [Razor Pages](/aspnet/core/tutorials/razor-pages)</span><span class="sxs-lookup"><span data-stu-id="75f14-134">ASP.NET Core [Blazor](/aspnet/core/blazor) or [Razor Pages](/aspnet/core/tutorials/razor-pages)</span></span> |
| <span data-ttu-id="75f14-135">Windows Workflow (WF)</span><span class="sxs-lookup"><span data-stu-id="75f14-135">Windows Workflow (WF)</span></span> | <span data-ttu-id="75f14-136">[CoreWF de código-fonte aberto](https://github.com/UiPath-Open/corewf) ou [Elsa-Workflow](https://github.com/elsa-workflows/elsa-core)</span><span class="sxs-lookup"><span data-stu-id="75f14-136">[Open-source CoreWF](https://github.com/UiPath-Open/corewf) or [Elsa-Workflow](https://github.com/elsa-workflows/elsa-core)</span></span> |

### <a name="windows-communication-foundation"></a><span data-ttu-id="75f14-137">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="75f14-137">Windows Communication Foundation</span></span>

<span data-ttu-id="75f14-138">A implementação original do [Windows Communication Foundation (WCF)](../framework/wcf/index.md) era suportada apenas no Windows.</span><span class="sxs-lookup"><span data-stu-id="75f14-138">The original implementation of [Windows Communication Foundation (WCF)](../framework/wcf/index.md) was only supported on Windows.</span></span> <span data-ttu-id="75f14-139">No entanto, há uma porta do cliente disponível no .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="75f14-139">However, there is a client port available from the .NET Foundation.</span></span> <span data-ttu-id="75f14-140">Ele é totalmente de software livre [, de plataforma](https://github.com/dotnet/wcf)cruzada e tem suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75f14-140">It is entirely [open source](https://github.com/dotnet/wcf), cross platform, and supported by Microsoft.</span></span> <span data-ttu-id="75f14-141">Os pacotes principais do NuGet estão listados abaixo:</span><span class="sxs-lookup"><span data-stu-id="75f14-141">The core NuGet packages are listed below:</span></span>

- [<span data-ttu-id="75f14-142">System.ServiceModel.Duplex</span><span class="sxs-lookup"><span data-stu-id="75f14-142">System.ServiceModel.Duplex</span></span>](https://www.nuget.org/packages/System.ServiceModel.Duplex)
- [<span data-ttu-id="75f14-143">System. ServiceModel. Federation</span><span class="sxs-lookup"><span data-stu-id="75f14-143">System.ServiceModel.Federation</span></span>](https://www.nuget.org/packages/System.ServiceModel.Federation)
- [<span data-ttu-id="75f14-144">System.ServiceModel.Http</span><span class="sxs-lookup"><span data-stu-id="75f14-144">System.ServiceModel.Http</span></span>](https://www.nuget.org/packages/System.ServiceModel.Http)
- [<span data-ttu-id="75f14-145">System.ServiceModel.NetTcp</span><span class="sxs-lookup"><span data-stu-id="75f14-145">System.ServiceModel.NetTcp</span></span>](https://www.nuget.org/packages/System.ServiceModel.NetTcp)
- [<span data-ttu-id="75f14-146">System.ServiceModel.Primitives</span><span class="sxs-lookup"><span data-stu-id="75f14-146">System.ServiceModel.Primitives</span></span>](https://www.nuget.org/packages/System.ServiceModel.Primitives)
- [<span data-ttu-id="75f14-147">{1&amp;gt;System.ServiceModel.Security&amp;lt;1}</span><span class="sxs-lookup"><span data-stu-id="75f14-147">System.ServiceModel.Security</span></span>](https://www.nuget.org/packages/System.ServiceModel.Security)

<span data-ttu-id="75f14-148">A comunidade mantém os componentes de servidor que complementam as bibliotecas de cliente mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="75f14-148">The community maintains the server components that complement the aforementioned client libraries.</span></span> <span data-ttu-id="75f14-149">O repositório GitHub pode ser encontrado em [CoreWCF](https://github.com/CoreWCF/CoreWCF).</span><span class="sxs-lookup"><span data-stu-id="75f14-149">The GitHub repository can be found at [CoreWCF](https://github.com/CoreWCF/CoreWCF).</span></span> <span data-ttu-id="75f14-150">Os componentes do servidor _não_ são oficialmente suportados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75f14-150">The server components are _not_ officially supported by Microsoft.</span></span> <span data-ttu-id="75f14-151">Para obter uma alternativa ao WCF, considere [gRPC](/aspnet/core/grpc).</span><span class="sxs-lookup"><span data-stu-id="75f14-151">For an alternative to WCF, consider [gRPC](/aspnet/core/grpc).</span></span>

## <a name="net-50-doesnt-replace-net-standard"></a><span data-ttu-id="75f14-152">O .NET 5,0 não substitui .NET Standard</span><span class="sxs-lookup"><span data-stu-id="75f14-152">.NET 5.0 doesn't replace .NET Standard</span></span>

<span data-ttu-id="75f14-153">O novo desenvolvimento de aplicativos pode especificar o `net5.0` moniker do Framework de destino (TFM) para todos os tipos de projeto, incluindo bibliotecas de classes.</span><span class="sxs-lookup"><span data-stu-id="75f14-153">New application development can specify the `net5.0` target framework moniker (TFM) for all project types, including class libraries.</span></span> <span data-ttu-id="75f14-154">O compartilhamento de código entre as cargas de trabalho do .NET 5 é simplificado, pois tudo o que você precisa é o `net5.0` TFM.</span><span class="sxs-lookup"><span data-stu-id="75f14-154">Sharing code between .NET 5 workloads is simplified in that all you need is the `net5.0` TFM.</span></span>

<span data-ttu-id="75f14-155">Para aplicativos e bibliotecas do .NET 5,0, o `net5.0` moniker da estrutura de destino (TFM) combina e substitui o `netcoreapp` e o `netstandard` TFMs.</span><span class="sxs-lookup"><span data-stu-id="75f14-155">For .NET 5.0 apps and libraries, the `net5.0` Target Framework Moniker (TFM) combines and replaces the `netcoreapp` and `netstandard` TFMs.</span></span> <span data-ttu-id="75f14-156">No entanto, se você planeja compartilhar o código entre as cargas de trabalho .NET Framework, .NET Core e .NET 5, poderá fazer isso especificando `netstandard2.0` como seu TFM.</span><span class="sxs-lookup"><span data-stu-id="75f14-156">However, if you plan to share code between .NET Framework, .NET Core, and .NET 5 workloads, you can do so by specifying `netstandard2.0` as your TFM.</span></span> <span data-ttu-id="75f14-157">Para obter mais informações, confira [.NET Standard](../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="75f14-157">For more information, see [.NET Standard](../standard/net-standard.md).</span></span>

## <a name="c-updates"></a><span data-ttu-id="75f14-158">Atualizações em C#</span><span class="sxs-lookup"><span data-stu-id="75f14-158">C# updates</span></span>

<span data-ttu-id="75f14-159">Os desenvolvedores que escrevem aplicativos .NET 5 terão acesso à versão e aos recursos mais recentes do C#.</span><span class="sxs-lookup"><span data-stu-id="75f14-159">Developers writing .NET 5 apps will have access to the latest C# version and features.</span></span> <span data-ttu-id="75f14-160">O .NET 5 é emparelhado com o C# 9, que traz muitos recursos novos para a linguagem.</span><span class="sxs-lookup"><span data-stu-id="75f14-160">.NET 5 is paired with C# 9, which brings many new features to the language.</span></span> <span data-ttu-id="75f14-161">Aqui estão alguns destaques:</span><span class="sxs-lookup"><span data-stu-id="75f14-161">Here are a few highlights:</span></span>

- <span data-ttu-id="75f14-162">Registros: tipos de referência com semântica de igualdade baseada em valor e mutação não destrutiva com suporte por uma nova `with` expressão.</span><span class="sxs-lookup"><span data-stu-id="75f14-162">Records: reference types with value-based equality semantics and non-destructive mutation supported by a new `with` expression.</span></span>
- <span data-ttu-id="75f14-163">Correspondência de padrão relacional: estende os recursos de correspondência de padrões para operadores relacionais para avaliações e expressões comparativa, incluindo padrões lógicos – novas palavras-chave `and` , `or` e `not` .</span><span class="sxs-lookup"><span data-stu-id="75f14-163">Relational pattern matching: Extends pattern matching capabilities to relational operators for comparative evaluations and expressions, including logical patterns - new keywords `and`, `or`, and `not`.</span></span>
- <span data-ttu-id="75f14-164">Instruções de nível superior: como um meio para acelerar a adoção e o aprendizado do C#, o `Main` método pode ser omitido e o aplicativo tão simples quanto o seguinte é válido:</span><span class="sxs-lookup"><span data-stu-id="75f14-164">Top-level statements: As a means for accelerating adoption and learning of C#, the `Main` method can be omitted and application as simple as the following is valid:</span></span>

   ```csharp
   System.Console.Write("Hello world!");
   ```

- <span data-ttu-id="75f14-165">Ponteiros de função: constructos de linguagem que expõem os seguintes opcodes de linguagem intermediária (IL): `ldftn` e `calli` .</span><span class="sxs-lookup"><span data-stu-id="75f14-165">Function pointers: Language constructs that expose the following intermediate language (IL) opcodes: `ldftn` and `calli`.</span></span>

<span data-ttu-id="75f14-166">Para obter mais informações sobre os recursos disponíveis do C# 9, consulte [o que há de novo no c# 9](../csharp/whats-new/csharp-9.md).</span><span class="sxs-lookup"><span data-stu-id="75f14-166">For more information on the available C# 9 features, see [What's new in C# 9](../csharp/whats-new/csharp-9.md).</span></span>

### <a name="source-generators"></a><span data-ttu-id="75f14-167">Geradores de origem</span><span class="sxs-lookup"><span data-stu-id="75f14-167">Source generators</span></span>

<span data-ttu-id="75f14-168">Além de alguns dos novos recursos do C# destacados, os geradores de origem estão fazendo seu caminho em projetos de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="75f14-168">In addition to some of the highlighted new C# features, source generators are making their way into developer projects.</span></span> <span data-ttu-id="75f14-169">Os geradores de origem permitem o código que é executado durante a compilação para inspecionar seu programa e produzir arquivos adicionais que são compilados junto com o restante do seu código.</span><span class="sxs-lookup"><span data-stu-id="75f14-169">Source generators allow code that runs during compilation to inspect your program and produce additional files that are compiled together with the rest of your code.</span></span>

<span data-ttu-id="75f14-170">Para obter mais informações sobre geradores de origem, consulte [introdução aos geradores de código](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) -fonte c# e [exemplos do gerador de código-fonte c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span><span class="sxs-lookup"><span data-stu-id="75f14-170">For more information on source generators, see [Introducing C# source generators](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) and [C# source generator samples](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).</span></span>

## <a name="f-updates"></a><span data-ttu-id="75f14-171">Atualizações de F #</span><span class="sxs-lookup"><span data-stu-id="75f14-171">F# updates</span></span>

<span data-ttu-id="75f14-172">O f # é a linguagem de programação funcional do .NET e, com o .NET 5, os desenvolvedores têm acesso ao F # 5.</span><span class="sxs-lookup"><span data-stu-id="75f14-172">F# is the .NET functional programming language, and with .NET 5, developers have access to F# 5.</span></span> <span data-ttu-id="75f14-173">Aqui estão vários recursos novos do F # 5:</span><span class="sxs-lookup"><span data-stu-id="75f14-173">Here are several new features of F# 5:</span></span>

### <a name="interpolated-strings"></a><span data-ttu-id="75f14-174">Cadeias de caracteres interpoladas</span><span class="sxs-lookup"><span data-stu-id="75f14-174">Interpolated strings</span></span>

<span data-ttu-id="75f14-175">Semelhante à cadeia de caracteres interpolada em C# e até mesmo JavaScript, F # dá suporte à interpolação de cadeia de caracteres básica.</span><span class="sxs-lookup"><span data-stu-id="75f14-175">Similar to interpolated string in C#, and even JavaScript, F# supports basic string interpolation.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

<span data-ttu-id="75f14-176">Além da interpolação de cadeia de caracteres básica, há interpolação de tipo.</span><span class="sxs-lookup"><span data-stu-id="75f14-176">In addition to basic string interpolation, there is typed interpolation.</span></span> <span data-ttu-id="75f14-177">Com a interpolação digitada, um determinado tipo deve corresponder ao especificador de formato.</span><span class="sxs-lookup"><span data-stu-id="75f14-177">With typed interpolation, a given type must match the format specifier.</span></span>

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

<span data-ttu-id="75f14-178">Isso é semelhante à [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) função que formata uma cadeia de caracteres com base em entradas de tipo seguro.</span><span class="sxs-lookup"><span data-stu-id="75f14-178">This is similar to the [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) function that formats a string based on type-safe inputs.</span></span> <!-- For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md). -->

## <a name="visual-basic-updates"></a><span data-ttu-id="75f14-179">Atualizações de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75f14-179">Visual Basic updates</span></span>

<span data-ttu-id="75f14-180">Não há novos recursos de linguagem para Visual Basic no .NET 5.</span><span class="sxs-lookup"><span data-stu-id="75f14-180">There are no new language features for Visual Basic in .NET 5.</span></span> <span data-ttu-id="75f14-181">No entanto, com o .NET 5, Visual Basic suporte é estendido para:</span><span class="sxs-lookup"><span data-stu-id="75f14-181">However, with .NET 5, Visual Basic support is extended to:</span></span>

| <span data-ttu-id="75f14-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="75f14-182">Description</span></span>                            | <span data-ttu-id="75f14-183">Parâmetro `dotnet new`</span><span class="sxs-lookup"><span data-stu-id="75f14-183">`dotnet new` parameter</span></span> |
|----------------------------------------|------------------------|
| <span data-ttu-id="75f14-184">Aplicativo do Console</span><span class="sxs-lookup"><span data-stu-id="75f14-184">Console Application</span></span>                    | `console`              |
| <span data-ttu-id="75f14-185">Biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="75f14-185">Class library</span></span>                          | `classlib`             |
| <span data-ttu-id="75f14-186">Aplicativo WPF</span><span class="sxs-lookup"><span data-stu-id="75f14-186">WPF Application</span></span>                        | `wpf`                  |
| <span data-ttu-id="75f14-187">Biblioteca de classes do WPF</span><span class="sxs-lookup"><span data-stu-id="75f14-187">WPF Class library</span></span>                      | `wpflib`               |
| <span data-ttu-id="75f14-188">Biblioteca de Controles Personalizados do WPF</span><span class="sxs-lookup"><span data-stu-id="75f14-188">WPF Custom Control Library</span></span>             | `wpfcustomcontrollib`  |
| <span data-ttu-id="75f14-189">Biblioteca de controle de usuário WPF</span><span class="sxs-lookup"><span data-stu-id="75f14-189">WPF User Control Library</span></span>               | `wpfusercontrollib`    |
| <span data-ttu-id="75f14-190">Aplicativo Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="75f14-190">Windows Forms (WinForms) Application</span></span>   | `winforms`             |
| <span data-ttu-id="75f14-191">Biblioteca de classes do Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="75f14-191">Windows Forms (WinForms) Class library</span></span> | `winformslib`          |
| <span data-ttu-id="75f14-192">Projeto de Teste de Unidade</span><span class="sxs-lookup"><span data-stu-id="75f14-192">Unit Test Project</span></span>                      | `mstest`               |
| <span data-ttu-id="75f14-193">Projeto de Teste do NUnit 3</span><span class="sxs-lookup"><span data-stu-id="75f14-193">NUnit 3 Test Project</span></span>                   | `nunit`                |
| <span data-ttu-id="75f14-194">Item de Teste do NUnit 3</span><span class="sxs-lookup"><span data-stu-id="75f14-194">NUnit 3 Test Item</span></span>                      | `nunit-test`           |
| <span data-ttu-id="75f14-195">Projeto de Teste xUnit</span><span class="sxs-lookup"><span data-stu-id="75f14-195">xUnit Test Project</span></span>                     | `xunit`                |

<span data-ttu-id="75f14-196">Para obter mais informações sobre modelos de projeto da CLI do .NET, consulte [`dotnet new`](tools/dotnet-new.md) .</span><span class="sxs-lookup"><span data-stu-id="75f14-196">For more information on project templates from the .NET CLI, see [`dotnet new`](tools/dotnet-new.md).</span></span>

## <a name="systemtextjson-new-features"></a><span data-ttu-id="75f14-197">System.Text.Jssobre novos recursos</span><span class="sxs-lookup"><span data-stu-id="75f14-197">System.Text.Json new features</span></span>

<span data-ttu-id="75f14-198">Há novos recursos no e para o [System.Text.Jsem](../standard/serialization/system-text-json-overview.md):</span><span class="sxs-lookup"><span data-stu-id="75f14-198">There are new features in and for [System.Text.Json](../standard/serialization/system-text-json-overview.md):</span></span>

- [<span data-ttu-id="75f14-199">Preservar referências e manipular referências circulares</span><span class="sxs-lookup"><span data-stu-id="75f14-199">Preserve references and handle circular references</span></span>](../standard/serialization/system-text-json-preserve-references.md)
- [<span data-ttu-id="75f14-200">Métodos de extensão HttpClient e HttpContent</span><span class="sxs-lookup"><span data-stu-id="75f14-200">HttpClient and HttpContent extension methods</span></span>](../standard/serialization/system-text-json-how-to.md#httpclient-and-httpcontent-extension-methods)
- [<span data-ttu-id="75f14-201">Permitir ou gravar números entre aspas</span><span class="sxs-lookup"><span data-stu-id="75f14-201">Allow or write numbers in quotes</span></span>](../standard/serialization/system-text-json-invalid-json.md#allow-or-write-numbers-in-quotes)
- [<span data-ttu-id="75f14-202">Suporte a tipos imutáveis e registros C# 9</span><span class="sxs-lookup"><span data-stu-id="75f14-202">Support immutable types and C# 9 Records</span></span>](../standard/serialization/system-text-json-immutability.md)
- [<span data-ttu-id="75f14-203">Suporte a acessadores de propriedade não públicos</span><span class="sxs-lookup"><span data-stu-id="75f14-203">Support non-public property accessors</span></span>](../standard/serialization/system-text-json-immutability.md)
- [<span data-ttu-id="75f14-204">Campos de suporte</span><span class="sxs-lookup"><span data-stu-id="75f14-204">Support fields</span></span>](../standard/serialization/system-text-json-how-to.md#include-fields)
- [<span data-ttu-id="75f14-205">Ignorar as propriedades condicionalmente</span><span class="sxs-lookup"><span data-stu-id="75f14-205">Conditionally ignore properties</span></span>](../standard/serialization/system-text-json-ignore-properties.md)
- [<span data-ttu-id="75f14-206">Suporte a dicionários de chave não cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="75f14-206">Support non-string-key dictionaries</span></span>](../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md#dictionary-with-non-string-key)
- [<span data-ttu-id="75f14-207">Permitir que conversores personalizados manipulem NULL</span><span class="sxs-lookup"><span data-stu-id="75f14-207">Allow custom converters to handle null</span></span>](../standard/serialization/system-text-json-converters-how-to.md#handle-null-values)
- [<span data-ttu-id="75f14-208">Copiar JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="75f14-208">Copy JsonSerializerOptions</span></span>](../standard/serialization/system-text-json-configure-options.md#copy-jsonserializeroptions)
- [<span data-ttu-id="75f14-209">Criar JsonSerializerOptions com padrões da Web</span><span class="sxs-lookup"><span data-stu-id="75f14-209">Create JsonSerializerOptions with web defaults</span></span>](../standard/serialization/system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)

## <a name="see-also"></a><span data-ttu-id="75f14-210">Veja também</span><span class="sxs-lookup"><span data-stu-id="75f14-210">See also</span></span>

- [<span data-ttu-id="75f14-211">A jornada para um .NET</span><span class="sxs-lookup"><span data-stu-id="75f14-211">The Journey to one .NET</span></span>](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [<span data-ttu-id="75f14-212">Melhorias de desempenho no .NET 5</span><span class="sxs-lookup"><span data-stu-id="75f14-212">Performance improvements in .NET 5</span></span>](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- [<span data-ttu-id="75f14-213">Baixar o SDK do .NET</span><span class="sxs-lookup"><span data-stu-id="75f14-213">Download the .NET SDK</span></span>](https://dotnet.microsoft.com/download)
