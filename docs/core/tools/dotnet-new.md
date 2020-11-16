---
title: Comando dotnet new
description: O comando dotnet New cria novos projetos .NET com base no modelo especificado.
no-loc:
- 'Blazor'
- 'WebAssembly'
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634449"
---
# <a name="dotnet-new"></a><span data-ttu-id="a33c2-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a33c2-103">dotnet new</span></span>

<span data-ttu-id="a33c2-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 2,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="a33c2-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a33c2-105">Name</span><span class="sxs-lookup"><span data-stu-id="a33c2-105">Name</span></span>

<span data-ttu-id="a33c2-106">`dotnet new` – Cria um novo projeto, arquivo de configuração ou solução com base no modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a33c2-107">Sinopse</span><span class="sxs-lookup"><span data-stu-id="a33c2-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="a33c2-108">Description</span><span class="sxs-lookup"><span data-stu-id="a33c2-108">Description</span></span>

<span data-ttu-id="a33c2-109">O `dotnet new` comando cria um projeto .net ou outros artefatos com base em um modelo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="a33c2-110">O comando chama o [mecanismo de modelo](https://github.com/dotnet/templating) para criar os artefatos em disco com base no modelo e nas opções especificadas.</span><span class="sxs-lookup"><span data-stu-id="a33c2-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="a33c2-111">Restauração implícita</span><span class="sxs-lookup"><span data-stu-id="a33c2-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="a33c2-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a33c2-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="a33c2-113">O modelo para o qual criar uma instância quando o comando é invocado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="a33c2-114">Cada modelo pode ter opções específicas que podem ser passadas.</span><span class="sxs-lookup"><span data-stu-id="a33c2-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="a33c2-115">Para obter mais informações, consulte [Opções de modelo](#template-options).</span><span class="sxs-lookup"><span data-stu-id="a33c2-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="a33c2-116">Você pode executar `dotnet new --list` ou `dotnet new -l` para ver uma lista de todos os modelos instalados.</span><span class="sxs-lookup"><span data-stu-id="a33c2-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="a33c2-117">Se o `TEMPLATE` valor não for uma correspondência exata no texto na coluna **modelos** ou **nome curto** da tabela retornada, uma correspondência de subcadeia de caracteres será executada nessas duas colunas.</span><span class="sxs-lookup"><span data-stu-id="a33c2-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="a33c2-118">A partir do SDK do .NET Core 3,0, a CLI procura modelos em NuGet.org quando você invoca o `dotnet new` comando nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="a33c2-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="a33c2-119">Se a CLI não encontrar uma correspondência de modelo ao invocar `dotnet new` , nem mesmo parcial.</span><span class="sxs-lookup"><span data-stu-id="a33c2-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="a33c2-120">Se houver uma versão mais recente do modelo disponível.</span><span class="sxs-lookup"><span data-stu-id="a33c2-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="a33c2-121">Nesse caso, o projeto ou artefato é criado, mas a CLI avisa sobre uma versão atualizada do modelo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="a33c2-122">A tabela a seguir mostra os modelos que vêm pré-instalados com o SDK do .NET.</span><span class="sxs-lookup"><span data-stu-id="a33c2-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="a33c2-123">O idioma padrão do modelo é mostrado entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="a33c2-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="a33c2-124">Clique no link nome curto para ver as opções de modelo específicas.</span><span class="sxs-lookup"><span data-stu-id="a33c2-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="a33c2-125">Modelos</span><span class="sxs-lookup"><span data-stu-id="a33c2-125">Templates</span></span>                                    | <span data-ttu-id="a33c2-126">Nome curto</span><span class="sxs-lookup"><span data-stu-id="a33c2-126">Short name</span></span>                      | <span data-ttu-id="a33c2-127">Idioma</span><span class="sxs-lookup"><span data-stu-id="a33c2-127">Language</span></span>     | <span data-ttu-id="a33c2-128">Marcações</span><span class="sxs-lookup"><span data-stu-id="a33c2-128">Tags</span></span>                                  | <span data-ttu-id="a33c2-129">Introduzida</span><span class="sxs-lookup"><span data-stu-id="a33c2-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="a33c2-130">Aplicativo do Console</span><span class="sxs-lookup"><span data-stu-id="a33c2-130">Console Application</span></span>                          | [<span data-ttu-id="a33c2-131">MMC</span><span class="sxs-lookup"><span data-stu-id="a33c2-131">console</span></span>](#console)             | <span data-ttu-id="a33c2-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-132">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-133">Comum/Console</span><span class="sxs-lookup"><span data-stu-id="a33c2-133">Common/Console</span></span>                        | <span data-ttu-id="a33c2-134">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-134">1.0</span></span>        |
| <span data-ttu-id="a33c2-135">Biblioteca de classes</span><span class="sxs-lookup"><span data-stu-id="a33c2-135">Class library</span></span>                                | [<span data-ttu-id="a33c2-136">classlib</span><span class="sxs-lookup"><span data-stu-id="a33c2-136">classlib</span></span>](#classlib)           | <span data-ttu-id="a33c2-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-137">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-138">Comum/Library</span><span class="sxs-lookup"><span data-stu-id="a33c2-138">Common/Library</span></span>                        | <span data-ttu-id="a33c2-139">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-139">1.0</span></span>        |
| <span data-ttu-id="a33c2-140">Aplicativo WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-140">WPF Application</span></span>                              | [<span data-ttu-id="a33c2-141">WFP</span><span class="sxs-lookup"><span data-stu-id="a33c2-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="a33c2-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-142">[C#], VB</span></span>     | <span data-ttu-id="a33c2-143">Comum/WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-143">Common/WPF</span></span>                            | <span data-ttu-id="a33c2-144">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-145">Biblioteca de classes do WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-145">WPF Class library</span></span>                            | [<span data-ttu-id="a33c2-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="a33c2-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="a33c2-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-147">[C#], VB</span></span>     | <span data-ttu-id="a33c2-148">Comum/WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-148">Common/WPF</span></span>                            | <span data-ttu-id="a33c2-149">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-150">Biblioteca de Controles Personalizados do WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="a33c2-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="a33c2-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="a33c2-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-152">[C#], VB</span></span>     | <span data-ttu-id="a33c2-153">Comum/WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-153">Common/WPF</span></span>                            | <span data-ttu-id="a33c2-154">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-155">Biblioteca de controle de usuário WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="a33c2-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="a33c2-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="a33c2-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-157">[C#], VB</span></span>     | <span data-ttu-id="a33c2-158">Comum/WPF</span><span class="sxs-lookup"><span data-stu-id="a33c2-158">Common/WPF</span></span>                            | <span data-ttu-id="a33c2-159">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-160">Aplicativo Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="a33c2-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="a33c2-161">WinForms</span><span class="sxs-lookup"><span data-stu-id="a33c2-161">winforms</span></span>](#winforms)           | <span data-ttu-id="a33c2-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-162">[C#], VB</span></span>     | <span data-ttu-id="a33c2-163">Comum/WinForms</span><span class="sxs-lookup"><span data-stu-id="a33c2-163">Common/WinForms</span></span>                       | <span data-ttu-id="a33c2-164">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-165">Biblioteca de classes do Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="a33c2-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="a33c2-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="a33c2-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="a33c2-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-167">[C#], VB</span></span>     | <span data-ttu-id="a33c2-168">Comum/WinForms</span><span class="sxs-lookup"><span data-stu-id="a33c2-168">Common/WinForms</span></span>                       | <span data-ttu-id="a33c2-169">3,0 (5,0 para VB)</span><span class="sxs-lookup"><span data-stu-id="a33c2-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="a33c2-170">Serviço de trabalho</span><span class="sxs-lookup"><span data-stu-id="a33c2-170">Worker Service</span></span>                               | [<span data-ttu-id="a33c2-171">funcionários</span><span class="sxs-lookup"><span data-stu-id="a33c2-171">worker</span></span>](#web-others)           | <span data-ttu-id="a33c2-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-172">[C#]</span></span>         | <span data-ttu-id="a33c2-173">Comum/de trabalho/Web</span><span class="sxs-lookup"><span data-stu-id="a33c2-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="a33c2-174">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-174">3.0</span></span>        |
| <span data-ttu-id="a33c2-175">Projeto de Teste de Unidade</span><span class="sxs-lookup"><span data-stu-id="a33c2-175">Unit Test Project</span></span>                            | [<span data-ttu-id="a33c2-176">MSTest</span><span class="sxs-lookup"><span data-stu-id="a33c2-176">mstest</span></span>](#test)                 | <span data-ttu-id="a33c2-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-177">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-178">Teste/MSTest</span><span class="sxs-lookup"><span data-stu-id="a33c2-178">Test/MSTest</span></span>                           | <span data-ttu-id="a33c2-179">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-179">1.0</span></span>        |
| <span data-ttu-id="a33c2-180">Projeto de Teste do NUnit 3</span><span class="sxs-lookup"><span data-stu-id="a33c2-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="a33c2-181">NUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="a33c2-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-182">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-183">Teste/NUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-183">Test/NUnit</span></span>                            | <span data-ttu-id="a33c2-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="a33c2-184">2.1.400</span></span>    |
| <span data-ttu-id="a33c2-185">Item de Teste do NUnit 3</span><span class="sxs-lookup"><span data-stu-id="a33c2-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="a33c2-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-186">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-187">Teste/NUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-187">Test/NUnit</span></span>                            | <span data-ttu-id="a33c2-188">2.2</span><span class="sxs-lookup"><span data-stu-id="a33c2-188">2.2</span></span>        |
| <span data-ttu-id="a33c2-189">Projeto de Teste xUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="a33c2-190">xUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-190">xunit</span></span>](#test)                  | <span data-ttu-id="a33c2-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a33c2-191">[C#], F#, VB</span></span> | <span data-ttu-id="a33c2-192">Teste/xUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-192">Test/xUnit</span></span>                            | <span data-ttu-id="a33c2-193">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-193">1.0</span></span>        |
| <span data-ttu-id="a33c2-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="a33c2-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="a33c2-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-195">[C#]</span></span>         | <span data-ttu-id="a33c2-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a33c2-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="a33c2-197">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-197">3.0</span></span>        |
| <span data-ttu-id="a33c2-198">Página do Razor</span><span class="sxs-lookup"><span data-stu-id="a33c2-198">Razor Page</span></span>                                   | [<span data-ttu-id="a33c2-199">page</span><span class="sxs-lookup"><span data-stu-id="a33c2-199">page</span></span>](#page)                   | <span data-ttu-id="a33c2-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-200">[C#]</span></span>         | <span data-ttu-id="a33c2-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a33c2-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="a33c2-202">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-202">2.0</span></span>        |
| <span data-ttu-id="a33c2-203">Importações de Exibição do MVC</span><span class="sxs-lookup"><span data-stu-id="a33c2-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="a33c2-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="a33c2-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="a33c2-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-205">[C#]</span></span>         | <span data-ttu-id="a33c2-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a33c2-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="a33c2-207">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-207">2.0</span></span>        |
| <span data-ttu-id="a33c2-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="a33c2-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="a33c2-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-209">[C#]</span></span>         | <span data-ttu-id="a33c2-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a33c2-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="a33c2-211">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-211">2.0</span></span>        |
| <span data-ttu-id="a33c2-212">Blazor Aplicativo de servidor</span><span class="sxs-lookup"><span data-stu-id="a33c2-212">Blazor Server App</span></span>                            | [<span data-ttu-id="a33c2-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="a33c2-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="a33c2-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-214">[C#]</span></span>         | <span data-ttu-id="a33c2-215">SiteBlazor</span><span class="sxs-lookup"><span data-stu-id="a33c2-215">Web/Blazor</span></span>                            | <span data-ttu-id="a33c2-216">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-216">3.0</span></span>        |
| <span data-ttu-id="a33c2-217">BlazorDo WebAssembly aplicativo</span><span class="sxs-lookup"><span data-stu-id="a33c2-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="a33c2-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="a33c2-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="a33c2-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-219">[C#]</span></span>         | <span data-ttu-id="a33c2-220">SiteBlazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="a33c2-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="a33c2-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="a33c2-221">3.1.300</span></span>    |
| <span data-ttu-id="a33c2-222">ASP.NET Core Vazio</span><span class="sxs-lookup"><span data-stu-id="a33c2-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="a33c2-223">site</span><span class="sxs-lookup"><span data-stu-id="a33c2-223">web</span></span>](#web)                     | <span data-ttu-id="a33c2-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a33c2-224">[C#], F#</span></span>     | <span data-ttu-id="a33c2-225">Web/Vazio</span><span class="sxs-lookup"><span data-stu-id="a33c2-225">Web/Empty</span></span>                             | <span data-ttu-id="a33c2-226">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-226">1.0</span></span>        |
| <span data-ttu-id="a33c2-227">Aplicativo Web ASP.NET Core (Modelo-Exibição-Controlador)</span><span class="sxs-lookup"><span data-stu-id="a33c2-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="a33c2-228">MVC</span><span class="sxs-lookup"><span data-stu-id="a33c2-228">mvc</span></span>](#web-options)             | <span data-ttu-id="a33c2-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a33c2-229">[C#], F#</span></span>     | <span data-ttu-id="a33c2-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a33c2-230">Web/MVC</span></span>                               | <span data-ttu-id="a33c2-231">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-231">1.0</span></span>        |
| <span data-ttu-id="a33c2-232">Aplicativo Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a33c2-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="a33c2-233">webapp, Razor</span><span class="sxs-lookup"><span data-stu-id="a33c2-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="a33c2-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-234">[C#]</span></span>         | <span data-ttu-id="a33c2-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a33c2-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="a33c2-236">2,2, 2,0</span><span class="sxs-lookup"><span data-stu-id="a33c2-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="a33c2-237">ASP.NET Core com Angular</span><span class="sxs-lookup"><span data-stu-id="a33c2-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="a33c2-238">angular</span><span class="sxs-lookup"><span data-stu-id="a33c2-238">angular</span></span>](#spa)                 | <span data-ttu-id="a33c2-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-239">[C#]</span></span>         | <span data-ttu-id="a33c2-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a33c2-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a33c2-241">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-241">2.0</span></span>        |
| <span data-ttu-id="a33c2-242">ASP.NET Core com React.js</span><span class="sxs-lookup"><span data-stu-id="a33c2-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="a33c2-243">reagir</span><span class="sxs-lookup"><span data-stu-id="a33c2-243">react</span></span>](#spa)                   | <span data-ttu-id="a33c2-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-244">[C#]</span></span>         | <span data-ttu-id="a33c2-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a33c2-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a33c2-246">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-246">2.0</span></span>        |
| <span data-ttu-id="a33c2-247">ASP.NET Core com React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="a33c2-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="a33c2-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="a33c2-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="a33c2-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-249">[C#]</span></span>         | <span data-ttu-id="a33c2-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a33c2-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a33c2-251">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-251">2.0</span></span>        |
| <span data-ttu-id="a33c2-252">Biblioteca de Classes do Razor</span><span class="sxs-lookup"><span data-stu-id="a33c2-252">Razor Class Library</span></span>                          | [<span data-ttu-id="a33c2-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="a33c2-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="a33c2-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-254">[C#]</span></span>         | <span data-ttu-id="a33c2-255">Web/Razor/Biblioteca/Biblioteca de Classes do Razor</span><span class="sxs-lookup"><span data-stu-id="a33c2-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="a33c2-256">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-256">2.1</span></span>        |
| <span data-ttu-id="a33c2-257">API Web do ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a33c2-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="a33c2-258">webAPI</span><span class="sxs-lookup"><span data-stu-id="a33c2-258">webapi</span></span>](#webapi)               | <span data-ttu-id="a33c2-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a33c2-259">[C#], F#</span></span>     | <span data-ttu-id="a33c2-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a33c2-260">Web/WebAPI</span></span>                            | <span data-ttu-id="a33c2-261">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-261">1.0</span></span>        |
| <span data-ttu-id="a33c2-262">ASP.NET Core serviço gRPC</span><span class="sxs-lookup"><span data-stu-id="a33c2-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="a33c2-263">grpc</span><span class="sxs-lookup"><span data-stu-id="a33c2-263">grpc</span></span>](#web-others)             | <span data-ttu-id="a33c2-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="a33c2-264">[C#]</span></span>         | <span data-ttu-id="a33c2-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="a33c2-265">Web/gRPC</span></span>                              | <span data-ttu-id="a33c2-266">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-266">3.0</span></span>        |
| <span data-ttu-id="a33c2-267">arquivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="a33c2-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="a33c2-268">Config</span><span class="sxs-lookup"><span data-stu-id="a33c2-268">Config</span></span>                                | <span data-ttu-id="a33c2-269">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-269">3.0</span></span>        |
| <span data-ttu-id="a33c2-270">Arquivo global.json</span><span class="sxs-lookup"><span data-stu-id="a33c2-270">global.json file</span></span>                             | [<span data-ttu-id="a33c2-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="a33c2-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="a33c2-272">Config</span><span class="sxs-lookup"><span data-stu-id="a33c2-272">Config</span></span>                                | <span data-ttu-id="a33c2-273">2.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-273">2.0</span></span>        |
| <span data-ttu-id="a33c2-274">Configuração do NuGet</span><span class="sxs-lookup"><span data-stu-id="a33c2-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="a33c2-275">Config</span><span class="sxs-lookup"><span data-stu-id="a33c2-275">Config</span></span>                                | <span data-ttu-id="a33c2-276">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-276">1.0</span></span>        |
| <span data-ttu-id="a33c2-277">Arquivo de manifesto da ferramenta local dotnet</span><span class="sxs-lookup"><span data-stu-id="a33c2-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="a33c2-278">Config</span><span class="sxs-lookup"><span data-stu-id="a33c2-278">Config</span></span>                                | <span data-ttu-id="a33c2-279">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-279">3.0</span></span>        |
| <span data-ttu-id="a33c2-280">Configuração da Web</span><span class="sxs-lookup"><span data-stu-id="a33c2-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="a33c2-281">Config</span><span class="sxs-lookup"><span data-stu-id="a33c2-281">Config</span></span>                                | <span data-ttu-id="a33c2-282">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-282">1.0</span></span>        |
| <span data-ttu-id="a33c2-283">Arquivo de Solução</span><span class="sxs-lookup"><span data-stu-id="a33c2-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="a33c2-284">Solução</span><span class="sxs-lookup"><span data-stu-id="a33c2-284">Solution</span></span>                              | <span data-ttu-id="a33c2-285">1.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-285">1.0</span></span>        |
| <span data-ttu-id="a33c2-286">Arquivo de buffer de protocolo</span><span class="sxs-lookup"><span data-stu-id="a33c2-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="a33c2-287">proto</span><span class="sxs-lookup"><span data-stu-id="a33c2-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="a33c2-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="a33c2-288">Web/gRPC</span></span>                              | <span data-ttu-id="a33c2-289">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="a33c2-290">Opções</span><span class="sxs-lookup"><span data-stu-id="a33c2-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="a33c2-291">Exibe um resumo do que ocorreria se o comando fornecido fosse executado se resultasse na criação de um modelo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="a33c2-292">Disponível desde o SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="a33c2-293">Força o conteúdo a ser gerado mesmo se ele alterasse os arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a33c2-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="a33c2-294">Isso é necessário quando o modelo escolhido substituiria os arquivos existentes no diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="a33c2-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a33c2-295">Imprime uma ajuda para o comando.</span><span class="sxs-lookup"><span data-stu-id="a33c2-295">Prints out help for the command.</span></span> <span data-ttu-id="a33c2-296">Ele pode ser invocado para o `dotnet new` próprio comando ou para qualquer modelo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="a33c2-297">Por exemplo, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="a33c2-298">Instala um pacote de modelos do `PATH` ou `NUGET_ID` fornecido.</span><span class="sxs-lookup"><span data-stu-id="a33c2-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a33c2-299">Se você deseja instalar uma versão de pré-lançamento de um pacote de modelo, é necessário especificar a versão no formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="a33c2-300">Por padrão, `dotnet new` \* o passa para a versão, que representa a versão de pacote estável mais recente.</span><span class="sxs-lookup"><span data-stu-id="a33c2-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="a33c2-301">Veja um exemplo na seção [exemplos](#examples) .</span><span class="sxs-lookup"><span data-stu-id="a33c2-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="a33c2-302">Se uma versão do modelo já tiver sido instalada quando você executar esse comando, o modelo será atualizado para a versão especificada ou para a versão estável mais recente se nenhuma versão tiver sido especificada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="a33c2-303">Para obter informações sobre a criação de modelos personalizados, consulte [Custom templates for dotnet new](custom-templates.md) (Modelos personalizados para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="a33c2-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="a33c2-304">Lista os modelos que contêm o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="a33c2-305">Se nenhum nome for especificado, listará todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="a33c2-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="a33c2-306">A linguagem do modelo a ser criada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-306">The language of the template to create.</span></span> <span data-ttu-id="a33c2-307">A linguagem aceita varia de acordo com o modelo (consulte os padrões na seção [Argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="a33c2-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a33c2-308">Não é válida para alguns modelos.</span><span class="sxs-lookup"><span data-stu-id="a33c2-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a33c2-309">Alguns shells interpretam `#` como um caractere especial.</span><span class="sxs-lookup"><span data-stu-id="a33c2-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a33c2-310">Nesses casos, coloque o valor do parâmetro de idioma entre aspas.</span><span class="sxs-lookup"><span data-stu-id="a33c2-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="a33c2-311">Por exemplo, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="a33c2-312">O nome para a saída criada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-312">The name for the created output.</span></span> <span data-ttu-id="a33c2-313">Se nenhum nome for especificado, o nome do diretório atual será usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="a33c2-314">Especifica uma origem do NuGet a ser usada durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="a33c2-315">Local para colocar a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-315">Location to place the generated output.</span></span> <span data-ttu-id="a33c2-316">O padrão é o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a33c2-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="a33c2-317">Filtra modelos com base em tipos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a33c2-317">Filters templates based on available types.</span></span> <span data-ttu-id="a33c2-318">Os valores predefinidos são `project` e `item` .</span><span class="sxs-lookup"><span data-stu-id="a33c2-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="a33c2-319">Desinstala um pacote de modelos no `PATH` ou `NUGET_ID` fornecido.</span><span class="sxs-lookup"><span data-stu-id="a33c2-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a33c2-320">Quando o `<PATH|NUGET_ID>` valor não for especificado, todos os pacotes de modelos instalados atualmente e seus modelos associados serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="a33c2-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="a33c2-321">Ao especificar `NUGET_ID` , não inclua o número de versão.</span><span class="sxs-lookup"><span data-stu-id="a33c2-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="a33c2-322">Se você não especificar um parâmetro para essa opção, o comando listará os modelos instalados e os detalhes sobre eles.</span><span class="sxs-lookup"><span data-stu-id="a33c2-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a33c2-323">Para desinstalar um modelo usando um `PATH`, você precisa qualificar totalmente o caminho.</span><span class="sxs-lookup"><span data-stu-id="a33c2-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="a33c2-324">Por exemplo, *C:/Users/ \<USER> /Documents/templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, mas *./GarciaSoftware.ConsoleTemplate.CSharp* da pasta que a contém não irá.</span><span class="sxs-lookup"><span data-stu-id="a33c2-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="a33c2-325">Não inclua uma barra de diretório final de encerramento no caminho do modelo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="a33c2-326">Verifica se há atualizações disponíveis para os pacotes de modelos que estão instalados no momento e os instala.</span><span class="sxs-lookup"><span data-stu-id="a33c2-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="a33c2-327">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="a33c2-328">Verifica se há atualizações disponíveis para os pacotes de modelos que estão instalados no momento.</span><span class="sxs-lookup"><span data-stu-id="a33c2-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="a33c2-329">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="a33c2-330">Opções de modelo</span><span class="sxs-lookup"><span data-stu-id="a33c2-330">Template options</span></span>

<span data-ttu-id="a33c2-331">Cada modelo de projeto pode ter opções adicionais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a33c2-331">Each project template may have additional options available.</span></span> <span data-ttu-id="a33c2-332">Os principais modelos têm as seguintes opções adicionais:</span><span class="sxs-lookup"><span data-stu-id="a33c2-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="a33c2-333">console</span><span class="sxs-lookup"><span data-stu-id="a33c2-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-334">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-335">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a33c2-336">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-337">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-337">SDK version</span></span> | <span data-ttu-id="a33c2-338">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-339">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-340">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-341">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a33c2-342">Define a `LangVersion` propriedade no arquivo de projeto criado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a33c2-343">Por exemplo, use `--langVersion 7.3` para usar C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a33c2-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a33c2-344">Sem suporte para F#.</span><span class="sxs-lookup"><span data-stu-id="a33c2-344">Not supported for F#.</span></span> <span data-ttu-id="a33c2-345">Disponível desde o SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-346">Para obter uma lista de versões padrão do C#, consulte [padrões](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a33c2-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-347">Se especificado, não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="a33c2-348">Disponível desde o SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="a33c2-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="a33c2-350">classlib</span><span class="sxs-lookup"><span data-stu-id="a33c2-350">classlib</span></span>

- <span data-ttu-id="a33c2-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-352">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-353">Valores: `net5.0` ou `netcoreapp<version>` para criar uma biblioteca de classes .net ou `netstandard<version>` para criar uma .net Standard biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="a33c2-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="a33c2-354">O valor padrão para o SDK do .NET 5,0 é `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="a33c2-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a33c2-355">Define a `LangVersion` propriedade no arquivo de projeto criado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a33c2-356">Por exemplo, use `--langVersion 7.3` para usar C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a33c2-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a33c2-357">Sem suporte para F#.</span><span class="sxs-lookup"><span data-stu-id="a33c2-357">Not supported for F#.</span></span> <span data-ttu-id="a33c2-358">Disponível desde o SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-359">Para obter uma lista de versões padrão do C#, consulte [padrões](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a33c2-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-360">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="a33c2-362">WPF, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="a33c2-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="a33c2-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-364">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-365">O valor padrão é `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-365">The default value is `net5.0`.</span></span> <span data-ttu-id="a33c2-366">Disponível desde o SDK do .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a33c2-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a33c2-367">Define a `LangVersion` propriedade no arquivo de projeto criado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a33c2-368">Por exemplo, use `--langVersion 7.3` para usar C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a33c2-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="a33c2-369">Para obter uma lista de versões padrão do C#, consulte [padrões](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a33c2-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-370">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="a33c2-372">WinForms, winformslib</span><span class="sxs-lookup"><span data-stu-id="a33c2-372">winforms, winformslib</span></span>

- <span data-ttu-id="a33c2-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="a33c2-374">Define a `LangVersion` propriedade no arquivo de projeto criado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a33c2-375">Por exemplo, use `--langVersion 7.3` para usar C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a33c2-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="a33c2-376">Para obter uma lista de versões padrão do C#, consulte [padrões](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a33c2-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-377">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="a33c2-379">trabalho, grpc</span><span class="sxs-lookup"><span data-stu-id="a33c2-379">worker, grpc</span></span>

- <span data-ttu-id="a33c2-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-381">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-382">O valor padrão é `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="a33c2-383">Disponível desde o SDK do .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a33c2-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-384">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-385">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="a33c2-387">MSTest, xUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-387">mstest, xunit</span></span>

- <span data-ttu-id="a33c2-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-389">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-390">Opção disponível desde o SDK do .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a33c2-391">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-392">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-392">SDK version</span></span> | <span data-ttu-id="a33c2-393">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-394">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-395">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-396">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="a33c2-397">Habilita o empacotamento para o projeto usando o [pacote dotnet](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a33c2-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-398">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="a33c2-400">NUnit</span><span class="sxs-lookup"><span data-stu-id="a33c2-400">nunit</span></span>

- <span data-ttu-id="a33c2-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-402">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="a33c2-403">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-404">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-404">SDK version</span></span> | <span data-ttu-id="a33c2-405">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-406">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-407">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-408">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a33c2-409">2.2</span><span class="sxs-lookup"><span data-stu-id="a33c2-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="a33c2-410">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="a33c2-411">Habilita o empacotamento para o projeto usando o [pacote dotnet](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a33c2-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-412">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="a33c2-414">página</span><span class="sxs-lookup"><span data-stu-id="a33c2-414">page</span></span>

- <span data-ttu-id="a33c2-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="a33c2-416">Namespace para o código gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-416">Namespace for the generated code.</span></span> <span data-ttu-id="a33c2-417">O valor padrão é `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="a33c2-418">Cria a página sem um PageModel.</span><span class="sxs-lookup"><span data-stu-id="a33c2-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="a33c2-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="a33c2-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="a33c2-420">viewimports, proto</span></span>

- <span data-ttu-id="a33c2-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="a33c2-422">Namespace para o código gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-422">Namespace for the generated code.</span></span> <span data-ttu-id="a33c2-423">O valor padrão é `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="a33c2-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="a33c2-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="a33c2-425">blazorserver</span></span>

- <span data-ttu-id="a33c2-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="a33c2-427">O tipo de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-427">The type of authentication to use.</span></span> <span data-ttu-id="a33c2-428">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33c2-428">The possible values are:</span></span>

  - <span data-ttu-id="a33c2-429">`None` – Nenhuma autenticação (Padrão).</span><span class="sxs-lookup"><span data-stu-id="a33c2-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a33c2-430">`Individual` – Autenticação individual.</span><span class="sxs-lookup"><span data-stu-id="a33c2-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="a33c2-431">`IndividualB2C` – Autenticação individual com o Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a33c2-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a33c2-432">`SingleOrg` – Autenticação organizacional para um único locatário.</span><span class="sxs-lookup"><span data-stu-id="a33c2-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a33c2-433">`MultiOrg` – Autenticação organizacional para vários locatários.</span><span class="sxs-lookup"><span data-stu-id="a33c2-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="a33c2-434">`Windows` – Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a33c2-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-435">A instância de Azure Active Directory B2C à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a33c2-436">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-437">O valor padrão é `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a33c2-438">A ID da política de entrada e inscrição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a33c2-439">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="a33c2-440">A ID da política de senha de redefinição para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="a33c2-441">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="a33c2-442">A ID de política de perfil de edição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="a33c2-443">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-444">A instância de Azure Active Directory à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a33c2-445">Use com a autenticação `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a33c2-446">O valor padrão é `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a33c2-447">A ID do cliente para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-447">The Client ID for this project.</span></span> <span data-ttu-id="a33c2-448">Use com a autenticação `IndividualB2C`, `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a33c2-449">O valor padrão é `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a33c2-450">O domínio para o locatário do diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-450">The domain for the directory tenant.</span></span> <span data-ttu-id="a33c2-451">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-452">O valor padrão é `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a33c2-453">A ID de Tenantid do diretório ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a33c2-454">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-455">O valor padrão é `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="a33c2-456">O caminho de solicitação dentro do caminho base do aplicativo do URI de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="a33c2-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a33c2-457">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-458">O valor padrão é `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a33c2-459">Permite que este aplicativo Leia o acesso ao diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a33c2-460">Aplicável apenas à autenticação `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-461">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-462">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-462">Turns off HTTPS.</span></span> <span data-ttu-id="a33c2-463">Essa opção só se aplica se `Individual` , `IndividualB2C` , `SingleOrg` ou `MultiOrg` não estiverem sendo usados para `--auth` .</span><span class="sxs-lookup"><span data-stu-id="a33c2-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a33c2-464">Especifica LocalDB deve ser usado em vez do SQLite.</span><span class="sxs-lookup"><span data-stu-id="a33c2-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a33c2-465">Aplicável apenas à autenticação `Individual` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-466">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="a33c2-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="a33c2-468">blazorwasm</span></span>

- <span data-ttu-id="a33c2-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="a33c2-470">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="a33c2-471">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-472">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-472">SDK version</span></span> | <span data-ttu-id="a33c2-473">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-474">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-475">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="a33c2-476">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="a33c2-477">Inclui um host ASP.NET Core para o Blazor WebAssembly aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="a33c2-478">O tipo de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-478">The type of authentication to use.</span></span> <span data-ttu-id="a33c2-479">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33c2-479">The possible values are:</span></span>

  - <span data-ttu-id="a33c2-480">`None` – Nenhuma autenticação (Padrão).</span><span class="sxs-lookup"><span data-stu-id="a33c2-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a33c2-481">`Individual` – Autenticação individual.</span><span class="sxs-lookup"><span data-stu-id="a33c2-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="a33c2-482">`IndividualB2C` – Autenticação individual com o Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a33c2-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a33c2-483">`SingleOrg` – Autenticação organizacional para um único locatário.</span><span class="sxs-lookup"><span data-stu-id="a33c2-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="a33c2-484">A autoridade do provedor de OIDC.</span><span class="sxs-lookup"><span data-stu-id="a33c2-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="a33c2-485">Use com a autenticação do `Individual`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="a33c2-486">O valor padrão é `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-487">A instância de Azure Active Directory B2C à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a33c2-488">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-489">O valor padrão é `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a33c2-490">A ID da política de entrada e inscrição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a33c2-491">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-492">A instância de Azure Active Directory à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a33c2-493">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-494">O valor padrão é `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a33c2-495">A ID do cliente para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-495">The Client ID for this project.</span></span> <span data-ttu-id="a33c2-496">Use o com o `IndividualB2C` , o `SingleOrg` ou a `Individual` autenticação em cenários autônomos.</span><span class="sxs-lookup"><span data-stu-id="a33c2-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="a33c2-497">O valor padrão é `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a33c2-498">O domínio para o locatário do diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-498">The domain for the directory tenant.</span></span> <span data-ttu-id="a33c2-499">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-500">O valor padrão é `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="a33c2-501">O URI da ID do aplicativo para a API do servidor que você deseja chamar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="a33c2-502">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-503">O valor padrão é `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="a33c2-504">A ID do cliente para a API que o servidor hospeda.</span><span class="sxs-lookup"><span data-stu-id="a33c2-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="a33c2-505">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-506">O valor padrão é `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="a33c2-507">O escopo da API que o cliente precisa solicitar para provisionar um token de acesso.</span><span class="sxs-lookup"><span data-stu-id="a33c2-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="a33c2-508">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-509">O valor padrão é `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a33c2-510">A ID de Tenantid do diretório ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a33c2-511">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-512">O valor padrão é `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a33c2-513">Permite que este aplicativo Leia o acesso ao diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a33c2-514">Aplica-se somente à `SingleOrg` autenticação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-515">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="a33c2-516">produz um aplicativo Web progressivo (PWA) que dá suporte à instalação e ao uso offline.</span><span class="sxs-lookup"><span data-stu-id="a33c2-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-517">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-517">Turns off HTTPS.</span></span> <span data-ttu-id="a33c2-518">Essa opção se aplica somente se `Individual` , `IndividualB2C` ou `SingleOrg` não estiverem sendo usados para `--auth` .</span><span class="sxs-lookup"><span data-stu-id="a33c2-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a33c2-519">Especifica LocalDB deve ser usado em vez do SQLite.</span><span class="sxs-lookup"><span data-stu-id="a33c2-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a33c2-520">Aplicável apenas à autenticação `Individual` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="a33c2-521">URL da API a ser chamada do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="a33c2-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="a33c2-522">Aplica-se somente ao `SingleOrg` ou à `IndividualB2C` autenticação sem um host ASP.NET Core especificado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="a33c2-523">O valor padrão é `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="a33c2-524">Especifica se o aplicativo Web chama Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="a33c2-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="a33c2-525">Aplica-se somente à `SingleOrg` autenticação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="a33c2-526">Escopos a serem solicitados a chamar a API do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="a33c2-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="a33c2-527">Aplica-se somente ao `SingleOrg` ou à `IndividualB2C` autenticação sem um host ASP.NET Core especificado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="a33c2-528">O padrão é `user.read`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-528">The default is `user.read`.</span></span>

<span data-ttu-id="a33c2-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="a33c2-530">web</span><span class="sxs-lookup"><span data-stu-id="a33c2-530">web</span></span>

- <span data-ttu-id="a33c2-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="a33c2-532">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-533">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-534">Opção não disponível no SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-535">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-536">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-536">SDK version</span></span> | <span data-ttu-id="a33c2-537">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-538">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-539">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-540">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a33c2-541">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="a33c2-542">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-543">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-543">Turns off HTTPS.</span></span>

<span data-ttu-id="a33c2-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="a33c2-545">MVC, webapp</span><span class="sxs-lookup"><span data-stu-id="a33c2-545">mvc, webapp</span></span>

- <span data-ttu-id="a33c2-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="a33c2-547">O tipo de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-547">The type of authentication to use.</span></span> <span data-ttu-id="a33c2-548">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33c2-548">The possible values are:</span></span>

  - <span data-ttu-id="a33c2-549">`None` – Nenhuma autenticação (Padrão).</span><span class="sxs-lookup"><span data-stu-id="a33c2-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a33c2-550">`Individual` – Autenticação individual.</span><span class="sxs-lookup"><span data-stu-id="a33c2-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="a33c2-551">`IndividualB2C` – Autenticação individual com o Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a33c2-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a33c2-552">`SingleOrg` – Autenticação organizacional para um único locatário.</span><span class="sxs-lookup"><span data-stu-id="a33c2-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a33c2-553">`MultiOrg` – Autenticação organizacional para vários locatários.</span><span class="sxs-lookup"><span data-stu-id="a33c2-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="a33c2-554">`Windows` – Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a33c2-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-555">A instância de Azure Active Directory B2C à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a33c2-556">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-557">O valor padrão é `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a33c2-558">A ID da política de entrada e inscrição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a33c2-559">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="a33c2-560">A ID da política de senha de redefinição para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="a33c2-561">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="a33c2-562">A ID de política de perfil de edição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="a33c2-563">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-564">A instância de Azure Active Directory à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a33c2-565">Use com a autenticação `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a33c2-566">O valor padrão é `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a33c2-567">A ID do cliente para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-567">The Client ID for this project.</span></span> <span data-ttu-id="a33c2-568">Use com a autenticação `IndividualB2C`, `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a33c2-569">O valor padrão é `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a33c2-570">O domínio para o locatário do diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-570">The domain for the directory tenant.</span></span> <span data-ttu-id="a33c2-571">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-572">O valor padrão é `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a33c2-573">A ID de Tenantid do diretório ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a33c2-574">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-575">O valor padrão é `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="a33c2-576">O caminho de solicitação dentro do caminho base do aplicativo do URI de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="a33c2-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a33c2-577">Use com a autenticação `SingleOrg` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-578">O valor padrão é `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a33c2-579">Permite que este aplicativo Leia o acesso ao diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a33c2-580">Aplicável apenas à autenticação `SingleOrg` ou `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-581">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-582">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-582">Turns off HTTPS.</span></span> <span data-ttu-id="a33c2-583">Essa opção é aplicável somente se `Individual`, `IndividualB2C`, `SingleOrg` ou `MultiOrg` não estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="a33c2-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a33c2-584">Especifica LocalDB deve ser usado em vez do SQLite.</span><span class="sxs-lookup"><span data-stu-id="a33c2-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a33c2-585">Aplicável apenas à autenticação `Individual` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-586">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-587">Opção disponível desde o SDK do .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a33c2-588">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-589">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-589">SDK version</span></span> | <span data-ttu-id="a33c2-590">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-591">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-592">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-593">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="a33c2-594">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="a33c2-595">Inclui BrowserLink no projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="a33c2-596">Opção não disponível no SDK do .NET Core 2,2 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="a33c2-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="a33c2-597">Determina se o projeto está configurado para usar a [compilação de tempo de execução do Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) em compilações de depuração.</span><span class="sxs-lookup"><span data-stu-id="a33c2-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="a33c2-598">Opção disponível desde o SDK do 3.1.201 do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a33c2-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="a33c2-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="a33c2-600">angular, reagir</span><span class="sxs-lookup"><span data-stu-id="a33c2-600">angular, react</span></span>

- <span data-ttu-id="a33c2-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="a33c2-602">O tipo de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-602">The type of authentication to use.</span></span> <span data-ttu-id="a33c2-603">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="a33c2-604">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33c2-604">The possible values are:</span></span>

  - <span data-ttu-id="a33c2-605">`None` – Nenhuma autenticação (Padrão).</span><span class="sxs-lookup"><span data-stu-id="a33c2-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a33c2-606">`Individual` – Autenticação individual.</span><span class="sxs-lookup"><span data-stu-id="a33c2-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-607">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a33c2-608">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-609">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-609">Turns off HTTPS.</span></span> <span data-ttu-id="a33c2-610">Essa opção se aplica somente se a autenticação for `None` .</span><span class="sxs-lookup"><span data-stu-id="a33c2-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a33c2-611">Especifica LocalDB deve ser usado em vez do SQLite.</span><span class="sxs-lookup"><span data-stu-id="a33c2-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a33c2-612">Aplicável apenas à autenticação `Individual` ou `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-613">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-614">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-615">Opção não disponível no SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-616">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-617">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-617">SDK version</span></span> | <span data-ttu-id="a33c2-618">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-619">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-620">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-621">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a33c2-622">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="a33c2-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="a33c2-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="a33c2-624">reactredux</span></span>

- <span data-ttu-id="a33c2-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="a33c2-626">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-627">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-628">Opção não disponível no SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-629">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-630">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-630">SDK version</span></span> | <span data-ttu-id="a33c2-631">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-632">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-633">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-634">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a33c2-635">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="a33c2-636">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-637">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-637">Turns off HTTPS.</span></span>

<span data-ttu-id="a33c2-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="a33c2-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="a33c2-639">razorclasslib</span></span>

- <span data-ttu-id="a33c2-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="a33c2-641">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="a33c2-642">Dá suporte à adição de páginas e exibições do Razor tradicionais, além dos componentes dessa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a33c2-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="a33c2-643">Disponível desde o SDK do .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a33c2-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="a33c2-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="a33c2-645">webapi</span><span class="sxs-lookup"><span data-stu-id="a33c2-645">webapi</span></span>

- <span data-ttu-id="a33c2-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="a33c2-647">O tipo de autenticação a ser usado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-647">The type of authentication to use.</span></span> <span data-ttu-id="a33c2-648">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a33c2-648">The possible values are:</span></span>

  - <span data-ttu-id="a33c2-649">`None` – Nenhuma autenticação (Padrão).</span><span class="sxs-lookup"><span data-stu-id="a33c2-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a33c2-650">`IndividualB2C` – Autenticação individual com o Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a33c2-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a33c2-651">`SingleOrg` – Autenticação organizacional para um único locatário.</span><span class="sxs-lookup"><span data-stu-id="a33c2-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a33c2-652">`Windows` – Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a33c2-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-653">A instância de Azure Active Directory B2C à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a33c2-654">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a33c2-655">O valor padrão é `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a33c2-656">A ID da política de entrada e inscrição deste projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a33c2-657">Use com a autenticação do `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a33c2-658">A instância de Azure Active Directory à qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a33c2-659">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-660">O valor padrão é `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a33c2-661">A ID do cliente para este projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-661">The Client ID for this project.</span></span> <span data-ttu-id="a33c2-662">Use com a autenticação `IndividualB2C` ou `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-663">O valor padrão é `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a33c2-664">O domínio para o locatário do diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-664">The domain for the directory tenant.</span></span> <span data-ttu-id="a33c2-665">Use com a autenticação `IndividualB2C` ou `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-666">O valor padrão é `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a33c2-667">A ID de Tenantid do diretório ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="a33c2-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a33c2-668">Use com a autenticação do `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a33c2-669">O valor padrão é `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a33c2-670">Permite que este aplicativo Leia o acesso ao diretório.</span><span class="sxs-lookup"><span data-stu-id="a33c2-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a33c2-671">Aplica-se somente à `SingleOrg` autenticação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a33c2-672">Exclui *launchSettings.js* do modelo gerado.</span><span class="sxs-lookup"><span data-stu-id="a33c2-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a33c2-673">Desativa o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a33c2-673">Turns off HTTPS.</span></span> <span data-ttu-id="a33c2-674">`app.UseHsts` e `app.UseHttpsRedirection` não são adicionados ao `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="a33c2-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a33c2-675">Essa opção só se aplica se `IndividualB2C` ou `SingleOrg` não estiver sendo usada para autenticação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a33c2-676">Especifica LocalDB deve ser usado em vez do SQLite.</span><span class="sxs-lookup"><span data-stu-id="a33c2-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a33c2-677">Aplica-se somente à `IndividualB2C` autenticação.</span><span class="sxs-lookup"><span data-stu-id="a33c2-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a33c2-678">Especifica a [estrutura](../../standard/frameworks.md) a ser direcionada.</span><span class="sxs-lookup"><span data-stu-id="a33c2-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a33c2-679">Opção não disponível no SDK do .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="a33c2-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a33c2-680">A tabela a seguir lista os valores padrão de acordo com o número de versão do SDK que você está usando:</span><span class="sxs-lookup"><span data-stu-id="a33c2-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a33c2-681">Versão do SDK</span><span class="sxs-lookup"><span data-stu-id="a33c2-681">SDK version</span></span> | <span data-ttu-id="a33c2-682">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="a33c2-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a33c2-683">5.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="a33c2-684">3.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a33c2-685">3.0</span><span class="sxs-lookup"><span data-stu-id="a33c2-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a33c2-686">2.1</span><span class="sxs-lookup"><span data-stu-id="a33c2-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="a33c2-687">Não executa uma restauração implícita durante a criação do projeto.</span><span class="sxs-lookup"><span data-stu-id="a33c2-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a33c2-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a33c2-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="a33c2-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="a33c2-689">globaljson</span></span>

- <span data-ttu-id="a33c2-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="a33c2-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="a33c2-691">Especifica a versão do SDK do .NET a ser usada na *global.jsno* arquivo.</span><span class="sxs-lookup"><span data-stu-id="a33c2-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="a33c2-692">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a33c2-692">Examples</span></span>

- <span data-ttu-id="a33c2-693">Crie um projeto de aplicativo de console em C# especificando o nome do modelo:</span><span class="sxs-lookup"><span data-stu-id="a33c2-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="a33c2-694">Crie um projeto de aplicativo de console F# no diretório atual:</span><span class="sxs-lookup"><span data-stu-id="a33c2-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="a33c2-695">Crie um projeto de biblioteca de classe .NET Standard no diretório especificado:</span><span class="sxs-lookup"><span data-stu-id="a33c2-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="a33c2-696">Crie um projeto de MVC em C# do ASP.NET Core no diretório atual sem autenticação:</span><span class="sxs-lookup"><span data-stu-id="a33c2-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="a33c2-697">Crie um projeto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="a33c2-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="a33c2-698">Listar todos os modelos disponíveis para modelos de aplicativo de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="a33c2-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="a33c2-699">Liste todos os modelos que correspondem à substring *we*.</span><span class="sxs-lookup"><span data-stu-id="a33c2-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="a33c2-700">Nenhuma correspondência exata é encontrada, portanto, a correspondência de substring é executada em relação tanto ao nome curto quanto às colunas de nome.</span><span class="sxs-lookup"><span data-stu-id="a33c2-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="a33c2-701">Tentativa de invocar o modelo correspondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="a33c2-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="a33c2-702">Se não for possível determinar uma única correspondência, liste os modelos que são correspondências parciais.</span><span class="sxs-lookup"><span data-stu-id="a33c2-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="a33c2-703">Instale a versão 2,0 dos modelos SPA para ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="a33c2-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="a33c2-704">Liste os modelos instalados e os detalhes sobre eles, incluindo como desinstalá-los:</span><span class="sxs-lookup"><span data-stu-id="a33c2-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="a33c2-705">Crie um *global.jsno* diretório atual definindo a versão do SDK para 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="a33c2-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="a33c2-706">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a33c2-706">See also</span></span>

- [<span data-ttu-id="a33c2-707">Modelos personalizados para dotnet new</span><span class="sxs-lookup"><span data-stu-id="a33c2-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- <span data-ttu-id="a33c2-708">[Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) (Criar um modelo personalizado para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="a33c2-708">[Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md)</span></span>
- [<span data-ttu-id="a33c2-709">Repositório do GitHub de dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="a33c2-709">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="a33c2-710">Modelos disponíveis para dotnet new</span><span class="sxs-lookup"><span data-stu-id="a33c2-710">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
