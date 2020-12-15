---
title: Criar um modelo de item para a CLI New-.NET do dotnet
description: Saiba como criar um modelo de item para o comando dotnet new. Os modelos de item podem conter qualquer quantidade de arquivos.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: b148870480584cff37f3fd395e0594344001f247
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512418"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="c345f-104">Tutorial: criar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="c345f-105">Com o .NET, você pode criar e implantar modelos que geram projetos, arquivos, até mesmo recursos.</span><span class="sxs-lookup"><span data-stu-id="c345f-105">With .NET, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="c345f-106">Este tutorial é a parte um de uma série que ensina a criar, instalar e desinstalar modelos para uso com o `dotnet new` comando.</span><span class="sxs-lookup"><span data-stu-id="c345f-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="c345f-107">Nesta parte da série, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="c345f-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="c345f-108">Criar uma classe para um modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-108">Create a class for an item template</span></span>
> * <span data-ttu-id="c345f-109">Criar a pasta e o arquivo de configuração do modelo</span><span class="sxs-lookup"><span data-stu-id="c345f-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="c345f-110">Instalar um modelo a partir de um caminho de arquivos</span><span class="sxs-lookup"><span data-stu-id="c345f-110">Install a template from a file path</span></span>
> * <span data-ttu-id="c345f-111">Testar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-111">Test an item template</span></span>
> * <span data-ttu-id="c345f-112">Desinstalar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c345f-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c345f-113">Prerequisites</span></span>

* <span data-ttu-id="c345f-114">[SDK do .net 5,0](https://dotnet.microsoft.com/download) ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="c345f-114">[.NET 5.0 SDK](https://dotnet.microsoft.com/download) or a later version.</span></span>
* <span data-ttu-id="c345f-115">Leia o artigo de referência [Modelos personalizados para dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c345f-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="c345f-116">O artigo de referência explica os conceitos básicos sobre modelos e como eles são agrupados.</span><span class="sxs-lookup"><span data-stu-id="c345f-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="c345f-117">Algumas dessas informações serão reiteradas aqui.</span><span class="sxs-lookup"><span data-stu-id="c345f-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="c345f-118">Abra um terminal e navegue até a pasta _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="c345f-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="c345f-119">Criar as pastas obrigatórias</span><span class="sxs-lookup"><span data-stu-id="c345f-119">Create the required folders</span></span>

<span data-ttu-id="c345f-120">Esta série usa uma "pasta de trabalho" na qual sua fonte de modelo está contida e uma "pasta de teste" usada para testar seus modelos.</span><span class="sxs-lookup"><span data-stu-id="c345f-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="c345f-121">A pasta de trabalho e a pasta de teste devem estar na mesma pasta pai.</span><span class="sxs-lookup"><span data-stu-id="c345f-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="c345f-122">Primeiro, crie a pasta pai. Use o nome que desejar para a pasta.</span><span class="sxs-lookup"><span data-stu-id="c345f-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="c345f-123">Em seguida, crie uma subpasta chamada _working_.</span><span class="sxs-lookup"><span data-stu-id="c345f-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="c345f-124">Na pasta _working_, crie uma subpasta chamada _templates_.</span><span class="sxs-lookup"><span data-stu-id="c345f-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="c345f-125">Em seguida, crie uma pasta na pasta pai chamada _test_.</span><span class="sxs-lookup"><span data-stu-id="c345f-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="c345f-126">A estrutura de pastas deve ser parecida com a seguinte.</span><span class="sxs-lookup"><span data-stu-id="c345f-126">The folder structure should look like the following.</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="c345f-127">Criar um modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-127">Create an item template</span></span>

<span data-ttu-id="c345f-128">Um modelo de item é um tipo específico de modelo que contém um ou mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="c345f-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="c345f-129">Esses tipos de modelos são úteis quando você deseja gerar algo como um arquivo de configuração, código ou solução.</span><span class="sxs-lookup"><span data-stu-id="c345f-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="c345f-130">Neste exemplo, você criará uma classe que adiciona um método de extensão ao tipo de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c345f-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="c345f-131">No terminal, navegue até a pasta _working\templates_ e crie uma nova subpasta chamada _extensions_.</span><span class="sxs-lookup"><span data-stu-id="c345f-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="c345f-132">Insira a pasta.</span><span class="sxs-lookup"><span data-stu-id="c345f-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="c345f-133">Crie um novo arquivo chamado _CommonExtensions.cs_ e abra-o com seu editor de texto favorito.</span><span class="sxs-lookup"><span data-stu-id="c345f-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="c345f-134">Essa classe fornecerá um método de extensão chamado `Reverse` que reverterá o conteúdo de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c345f-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="c345f-135">Cole no seguinte código e salve o arquivo:</span><span class="sxs-lookup"><span data-stu-id="c345f-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="c345f-136">Agora que você tem o conteúdo do modelo criado, é necessário criar a configuração do modelo na pasta raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="c345f-137">Criar a configuração do modelo</span><span class="sxs-lookup"><span data-stu-id="c345f-137">Create the template config</span></span>

<span data-ttu-id="c345f-138">Os modelos são reconhecidos por uma pasta especial e um arquivo de configuração que existem na raiz do modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-138">Templates are recognized by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="c345f-139">Neste tutorial, a pasta de modelos está localizada em _working\templates\extensions_.</span><span class="sxs-lookup"><span data-stu-id="c345f-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="c345f-140">Quando você cria um modelo, todos os arquivos e pastas na pasta de modelos são incluídos como parte do modelo, exceto a pasta de configuração especial.</span><span class="sxs-lookup"><span data-stu-id="c345f-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="c345f-141">Esta pasta de configuração chama-se _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="c345f-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="c345f-142">Primeiro, crie uma nova subpasta chamada _.template.config_, insira-a.</span><span class="sxs-lookup"><span data-stu-id="c345f-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="c345f-143">Em seguida, crie um novo arquivo chamado _template.json_.</span><span class="sxs-lookup"><span data-stu-id="c345f-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="c345f-144">A estrutura de pastas devem ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="c345f-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="c345f-145">Abra o _template.jsem_ com seu editor de texto favorito e cole o código JSON a seguir e salve-o.</span><span class="sxs-lookup"><span data-stu-id="c345f-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="c345f-146">Esse arquivo de configuração contém todas as configurações do modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="c345f-147">Você pode ver as configurações básicas, como `name` e `shortName`, mas também há um valor `tags/type` que está definido como `item`.</span><span class="sxs-lookup"><span data-stu-id="c345f-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="c345f-148">Isso categoriza seu modelo como um modelo de item.</span><span class="sxs-lookup"><span data-stu-id="c345f-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="c345f-149">Não há restrições quanto ao tipo do modelo criado.</span><span class="sxs-lookup"><span data-stu-id="c345f-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="c345f-150">Os `item` `project` valores e são nomes comuns que o .net recomenda para que os usuários possam filtrar facilmente o tipo de modelo que estão procurando.</span><span class="sxs-lookup"><span data-stu-id="c345f-150">The `item` and `project` values are common names that .NET recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="c345f-151">O item `classifications` representa a coluna **marcações** que você vê quando executa `dotnet new` e obtém uma lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="c345f-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="c345f-152">Os usuários também podem pesquisar com base nas marcações de classificação.</span><span class="sxs-lookup"><span data-stu-id="c345f-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="c345f-153">Não confunda a propriedade `tags` no arquivo \*.json com a lista de marcações `classifications`.</span><span class="sxs-lookup"><span data-stu-id="c345f-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="c345f-154">São duas coisas diferentes, mas, infelizmente, nomeadas da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="c345f-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="c345f-155">O esquema completo do arquivo *template.json* é encontrado no [Repositório de Esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="c345f-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="c345f-156">Para saber mais sobre o arquivo *template.json*, veja o [wiki de modelagem dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="c345f-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="c345f-157">Agora que você já tem um arquivo _.template.config/template.json_ válido, seu modelo está pronto para ser instalado.</span><span class="sxs-lookup"><span data-stu-id="c345f-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="c345f-158">No terminal, navegue até a pasta _extensions_ e execute o seguinte comando para instalar o modelo localizado na pasta atual:</span><span class="sxs-lookup"><span data-stu-id="c345f-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="c345f-159">**No Windows**: `dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="c345f-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="c345f-160">**No Linux ou MacOS**: `dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="c345f-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="c345f-161">Esse comando gera a lista de modelos instalados que deve incluir o seu.</span><span class="sxs-lookup"><span data-stu-id="c345f-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Example templates: string extensions              stringext                [C#]              Common/Code
Console Application                               console                  [C#], F#, VB      Common/Console
Class library                                     classlib                 [C#], F#, VB      Common/Library
WPF Application                                   wpf                      [C#], VB          Common/WPF
```

## <a name="test-the-item-template"></a><span data-ttu-id="c345f-162">Testar o modelo de item</span><span class="sxs-lookup"><span data-stu-id="c345f-162">Test the item template</span></span>

<span data-ttu-id="c345f-163">Agora que você tem um modelo de item instalado, teste-o.</span><span class="sxs-lookup"><span data-stu-id="c345f-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="c345f-164">Navegue até a pasta _test/_ e crie um novo aplicativo de console com `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="c345f-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="c345f-165">Isso gera um projeto funcional que você pode testar facilmente com o comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c345f-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="c345f-166">Você Obtém uma saída semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="c345f-166">You get output similar to the following.</span></span>

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

<span data-ttu-id="c345f-167">Execute o projeto com.</span><span class="sxs-lookup"><span data-stu-id="c345f-167">Run the project with.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c345f-168">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="c345f-168">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="c345f-169">Em seguida, execute `dotnet new stringext` para gerar o _CommonExtensions.cs_ a partir do modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-169">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```dotnetcli
dotnet new stringext
```

<span data-ttu-id="c345f-170">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="c345f-170">You get the following output.</span></span>

```console
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="c345f-171">Altere o código em _Program.cs_ para inverter a cadeia de caracteres `"Hello World"` com o método de extensão fornecido pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-171">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="c345f-172">Execute o programa novamente e você verá que o resultado foi invertido.</span><span class="sxs-lookup"><span data-stu-id="c345f-172">Run the program again and you'll see that the result is reversed.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c345f-173">Você Obtém a saída a seguir.</span><span class="sxs-lookup"><span data-stu-id="c345f-173">You get the following output.</span></span>

```console
!dlroW olleH
```

<span data-ttu-id="c345f-174">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="c345f-174">Congratulations!</span></span> <span data-ttu-id="c345f-175">Você criou e implantou um modelo de item com o .NET.</span><span class="sxs-lookup"><span data-stu-id="c345f-175">You created and deployed an item template with .NET.</span></span> <span data-ttu-id="c345f-176">Para se preparar para a próxima parte desta série de tutoriais, você deverá desinstalar o modelo criado.</span><span class="sxs-lookup"><span data-stu-id="c345f-176">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="c345f-177">Lembre-se de também excluir todos os arquivos da pasta _test_.</span><span class="sxs-lookup"><span data-stu-id="c345f-177">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="c345f-178">Isso levará você de volta a um estado limpo, pronto para a próxima seção principal deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="c345f-178">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="c345f-179">Desinstalar o modelo</span><span class="sxs-lookup"><span data-stu-id="c345f-179">Uninstall the template</span></span>

<span data-ttu-id="c345f-180">Como você instalou o modelo com o caminho de arquivo, você deve desinstalá-lo com o caminho de arquivo **absoluto**.</span><span class="sxs-lookup"><span data-stu-id="c345f-180">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="c345f-181">Você pode ver uma lista de modelos instalados executando o comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="c345f-181">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="c345f-182">Seu modelo deve ser listado por último.</span><span class="sxs-lookup"><span data-stu-id="c345f-182">Your template should be listed last.</span></span> <span data-ttu-id="c345f-183">Use o `Uninstall Command` listado para desinstalar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="c345f-183">Use the `Uninstall Command` listed to uninstall your template.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="c345f-184">Você Obtém uma saída semelhante à seguinte.</span><span class="sxs-lookup"><span data-stu-id="c345f-184">You get output similar to the following.</span></span>

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

C:\Test\templatetutorial\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
    Uninstall Command:
      dotnet new -u C:\working\templates\extensions
```

<span data-ttu-id="c345f-185">Para desinstalar o modelo que você criou, execute o `Uninstall Command` que é mostrado na saída.</span><span class="sxs-lookup"><span data-stu-id="c345f-185">To uninstall the template that you created, run the `Uninstall Command` that is shown in the output.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="c345f-186">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c345f-186">Next steps</span></span>

<span data-ttu-id="c345f-187">Neste tutorial, você criou um modelo de item.</span><span class="sxs-lookup"><span data-stu-id="c345f-187">In this tutorial, you created an item template.</span></span> <span data-ttu-id="c345f-188">Para saber como criar um modelo de projeto, continue a ver essa série de tutoriais.</span><span class="sxs-lookup"><span data-stu-id="c345f-188">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c345f-189">Criar um modelo de projeto</span><span class="sxs-lookup"><span data-stu-id="c345f-189">Create a project template</span></span>](cli-templates-create-project-template.md)
