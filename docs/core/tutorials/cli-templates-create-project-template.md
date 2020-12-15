---
title: Criar um modelo de projetos para o dotnet new
description: Saiba como criar um modelo de projetos para o comando dotnet new.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: ed40cfd303c70c7b8f198a0f5b593bf1e1ebeaf8
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513127"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="2ea7f-103">Tutorial: criar um modelo de projeto</span><span class="sxs-lookup"><span data-stu-id="2ea7f-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="2ea7f-104">Com o .NET, você pode criar e implantar modelos que geram projetos, arquivos, até mesmo recursos.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-104">With .NET, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="2ea7f-105">Este tutorial é a parte dois de uma série que ensina como criar, instalar e desinstalar modelos para usar com o comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="2ea7f-106">Nesta parte da série, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="2ea7f-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="2ea7f-107">Criar os recursos de um modelo de projeto</span><span class="sxs-lookup"><span data-stu-id="2ea7f-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="2ea7f-108">Criar a pasta e o arquivo de configuração do modelo</span><span class="sxs-lookup"><span data-stu-id="2ea7f-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="2ea7f-109">Instalar um modelo a partir de um caminho de arquivos</span><span class="sxs-lookup"><span data-stu-id="2ea7f-109">Install a template from a file path</span></span>
> * <span data-ttu-id="2ea7f-110">Testar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="2ea7f-110">Test an item template</span></span>
> * <span data-ttu-id="2ea7f-111">Desinstalar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="2ea7f-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ea7f-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2ea7f-112">Prerequisites</span></span>

* <span data-ttu-id="2ea7f-113">Conclua a [parte 1](cli-templates-create-item-template.md) desta série de tutoriais.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="2ea7f-114">Abra um terminal e navegue até a pasta _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="2ea7f-115">Criar um modelo de projeto</span><span class="sxs-lookup"><span data-stu-id="2ea7f-115">Create a project template</span></span>

<span data-ttu-id="2ea7f-116">Os modelos de projeto produzem projetos prontos para execução que ajudam os usuários a começar com um conjunto de códigos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="2ea7f-117">O .NET inclui alguns modelos de projeto, como um aplicativo de console ou uma biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-117">.NET includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="2ea7f-118">Neste exemplo, você criará um novo projeto de console que habilita o C# 9,0 e produz um `async main` ponto de entrada.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-118">In this example, you'll create a new console project that enables C# 9.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="2ea7f-119">No terminal, navegue até a pasta _working\templates_ e crie uma nova subpasta chamada _consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="2ea7f-120">Insira a subpasta e execute `dotnet new console` para gerar o aplicativo de console padrão.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="2ea7f-121">Você editará os arquivos produzidos por este modelo para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="2ea7f-122">Modificar o Program.cs</span><span class="sxs-lookup"><span data-stu-id="2ea7f-122">Modify Program.cs</span></span>

<span data-ttu-id="2ea7f-123">Abra o arquivo _program.cs_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="2ea7f-124">O projeto do console não usa um ponto de entrada assíncrono, então vamos adicionar isso.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="2ea7f-125">Altere seu código para o seguinte e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-125">Change your code to the following and save the file.</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 9.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="2ea7f-126">Modificar consoleasync.csproj</span><span class="sxs-lookup"><span data-stu-id="2ea7f-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="2ea7f-127">Vamos atualizar a versão da linguagem C# que o projeto usa para a versão 9,0.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-127">Let's update the C# language version the project uses to version 9.0.</span></span> <span data-ttu-id="2ea7f-128">Edite o arquivo _consoleasync.csproj_ e adicione a configuração `<LangVersion>` a um nó `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>

    <LangVersion>9.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="2ea7f-129">Compilar o projeto</span><span class="sxs-lookup"><span data-stu-id="2ea7f-129">Build the project</span></span>

<span data-ttu-id="2ea7f-130">Antes de concluir um modelo de projeto, você deve testá-lo para garantir que ele seja compilado e executado corretamente.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span>

<span data-ttu-id="2ea7f-131">No seu terminal, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-131">In your terminal, run the following command.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="2ea7f-132">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-132">You get the following output.</span></span>

```console
Hello World with C# 9.0!
```

<span data-ttu-id="2ea7f-133">Você pode excluir as pastas _obj_ e _bin_ criadas usando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-133">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="2ea7f-134">A exclusão desses arquivos garante que o modelo inclua apenas os arquivos relacionados ao seu modelo e não todos os arquivos resultantes de uma ação de compilação.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-134">Deleting these files ensures your template only includes the files related to your template and not any files that result from a build action.</span></span>

<span data-ttu-id="2ea7f-135">Agora que você tem o conteúdo do modelo criado, é necessário criar a configuração do modelo na pasta raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-135">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="2ea7f-136">Criar a configuração do modelo</span><span class="sxs-lookup"><span data-stu-id="2ea7f-136">Create the template config</span></span>

<span data-ttu-id="2ea7f-137">Os modelos são reconhecidos no .NET por uma pasta especial e um arquivo de configuração que existem na raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-137">Templates are recognized in .NET by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="2ea7f-138">Neste tutorial, a pasta de modelos está localizada em _working\templates\consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-138">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="2ea7f-139">Quando você cria um modelo, todos os arquivos e pastas na pasta de modelos são incluídos como parte do modelo, exceto a pasta de configuração especial.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-139">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="2ea7f-140">Esta pasta de configuração chama-se _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-140">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="2ea7f-141">Primeiro, crie uma nova subpasta chamada _.template.config_, insira-a.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-141">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="2ea7f-142">Em seguida, crie um novo arquivo chamado _template.json_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-142">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="2ea7f-143">A estrutura de pastas deve ser parecida com esta.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-143">Your folder structure should look like this.</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="2ea7f-144">Abra o _template.jsem_ com seu editor de texto favorito e cole o código JSON a seguir e salve-o.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-144">Open the _template.json_ with your favorite text editor and paste in the following json code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#9" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="2ea7f-145">Esse arquivo de configuração contém todas as configurações do modelo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-145">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="2ea7f-146">Você pode ver as configurações básicas, como `name` e `shortName`, mas também há um valor `tags/type` que é definido como `project`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-146">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="2ea7f-147">Isso designa seu modelo como um modelo de projeto.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-147">This designates your template as a project template.</span></span> <span data-ttu-id="2ea7f-148">Não há restrições quanto ao tipo do modelo criado.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-148">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="2ea7f-149">Os `item` `project` valores e são nomes comuns que o .net recomenda para que os usuários possam filtrar facilmente o tipo de modelo que estão procurando.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-149">The `item` and `project` values are common names that .NET recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="2ea7f-150">O item `classifications` representa a coluna **marcações** que você vê quando executa `dotnet new` e obtém uma lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-150">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="2ea7f-151">Os usuários também podem pesquisar com base nas marcações de classificação.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-151">Users can also search based on classification tags.</span></span> <span data-ttu-id="2ea7f-152">Não confunda a propriedade `tags` no arquivo json com a lista de marcações `classifications`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-152">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="2ea7f-153">São duas coisas diferentes, mas, infelizmente, nomeadas da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-153">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="2ea7f-154">O esquema completo do arquivo *template.json* é encontrado no [Repositório de Esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="2ea7f-154">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="2ea7f-155">Para saber mais sobre o arquivo *template.json*, veja o [wiki de modelagem dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="2ea7f-155">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="2ea7f-156">Agora que você já tem um arquivo _.template.config/template.json_ válido, seu modelo está pronto para ser instalado.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-156">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="2ea7f-157">Antes de instalar o modelo, exclua todas as pastas e arquivos extras que você não deseja incluir no modelo, como as pastas _bin_ ou _obj_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-157">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="2ea7f-158">No terminal, navegue até a pasta _consoleasync_ e execute `dotnet new -i .\` para instalar o modelo localizado na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-158">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="2ea7f-159">Se você estiver usando um sistema operacional Linux ou macOS, use uma barra invertida: `dotnet new -i ./` .</span><span class="sxs-lookup"><span data-stu-id="2ea7f-159">If you're using a Linux or macOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="2ea7f-160">Esse comando gera a lista de modelos instalados que deve incluir o seu.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-160">This command outputs the list of templates installed, which should include yours.</span></span>

```dotnetcli
dotnet new -i .\
```

<span data-ttu-id="2ea7f-161">Você Obtém uma saída semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-161">You get output similar to the following.</span></span>

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Console Application                               console                  [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync             [C#]              Common/Console/C#9
Class library                                     classlib                 [C#], F#, VB      Common/Library
WPF Application                                   wpf                      [C#], VB          Common/WPF
```

### <a name="test-the-project-template"></a><span data-ttu-id="2ea7f-162">Testar o modelo do projeto</span><span class="sxs-lookup"><span data-stu-id="2ea7f-162">Test the project template</span></span>

<span data-ttu-id="2ea7f-163">Agora que você tem um modelo de projeto instalado, teste-o.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-163">Now that you have a project template installed, test it.</span></span>

1. <span data-ttu-id="2ea7f-164">Navegue até a pasta de _teste_</span><span class="sxs-lookup"><span data-stu-id="2ea7f-164">Navigate to the _test_ folder</span></span>

1. <span data-ttu-id="2ea7f-165">Crie um novo aplicativo de console com o comando a seguir, que gera um projeto em funcionamento que você pode testar facilmente com o `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-165">Create a new console application with the following command which generates a working project you can easily test with the `dotnet run` command.</span></span>

    ```dotnetcli
    dotnet new consoleasync
    ```

    <span data-ttu-id="2ea7f-166">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-166">You get the following output.</span></span>

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. <span data-ttu-id="2ea7f-167">Execute o projeto usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-167">Run the project using the following command.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="2ea7f-168">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-168">You get the following output.</span></span>

    ```console
    Hello World with C# 9.0!
    ```

<span data-ttu-id="2ea7f-169">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="2ea7f-169">Congratulations!</span></span> <span data-ttu-id="2ea7f-170">Você criou e implantou um modelo de projeto com o .NET.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-170">You created and deployed a project template with .NET.</span></span> <span data-ttu-id="2ea7f-171">Para se preparar para a próxima parte desta série de tutoriais, você deverá desinstalar o modelo criado.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="2ea7f-172">Lembre-se de também excluir todos os arquivos da pasta _test_.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="2ea7f-173">Isso levará você de volta a um estado limpo, pronto para a próxima seção principal deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="2ea7f-174">Desinstalar o modelo</span><span class="sxs-lookup"><span data-stu-id="2ea7f-174">Uninstall the template</span></span>

<span data-ttu-id="2ea7f-175">Como você instalou o modelo usando um caminho de arquivo, você deve desinstalá-lo com o caminho de arquivo **absoluto**.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-175">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="2ea7f-176">Você pode ver uma lista de modelos instalados executando o comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="2ea7f-177">Seu modelo deve ser listado por último.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-177">Your template should be listed last.</span></span> <span data-ttu-id="2ea7f-178">Use o `Uninstall Command` listado para desinstalar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-178">Use the `Uninstall Command` listed to uninstall your template.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="2ea7f-179">Você Obtém uma saída semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-179">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ProjectTemplates.2.2
    Details:
      NuGetPackageId: Microsoft.DotNet.Common.ProjectTemplates.2.2
      Version: 1.0.2-beta4
      Author: Microsoft
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
    Uninstall Command:
      dotnet new -u Microsoft.DotNet.Common.ProjectTemplates.2.2

... cut to save space ...

  C:\Test\templatetutorial\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
    Uninstall Command:
      dotnet new -u C:\working\templates\consoleasync
```

<span data-ttu-id="2ea7f-180">Para desinstalar o modelo que você criou, execute o `Uninstall Command` que é mostrado na saída.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-180">To uninstall the template that you created, run the `Uninstall Command` that is shown in the output.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="2ea7f-181">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2ea7f-181">Next steps</span></span>

<span data-ttu-id="2ea7f-182">Neste tutorial, você criou um modelo de projeto.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-182">In this tutorial, you created a project template.</span></span> <span data-ttu-id="2ea7f-183">Para aprender como empacotar os modelos de item e projeto em um arquivo simples, continue a ver esta série de tutoriais.</span><span class="sxs-lookup"><span data-stu-id="2ea7f-183">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2ea7f-184">Criar um pacote de modelos</span><span class="sxs-lookup"><span data-stu-id="2ea7f-184">Create a template pack</span></span>](cli-templates-create-template-pack.md)
