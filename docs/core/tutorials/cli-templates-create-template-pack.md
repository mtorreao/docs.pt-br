---
title: Criar um pacote de modelos para dotnet new
description: Saiba como criar um arquivo csproj que criará um pacote de modelos para o comando dotnet new.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 0d8ef9c158920ec49948215afb505a3753503286
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512444"
---
# <a name="tutorial-create-a-template-pack"></a><span data-ttu-id="e6ea8-103">Tutorial: criar um pacote de modelos</span><span class="sxs-lookup"><span data-stu-id="e6ea8-103">Tutorial: Create a template pack</span></span>

<span data-ttu-id="e6ea8-104">Com o .NET, você pode criar e implantar modelos que geram projetos, arquivos, até mesmo recursos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-104">With .NET, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="e6ea8-105">Este tutorial é a parte três de uma série que ensina a criar, instalar e desinstalar modelos para uso com o `dotnet new` comando.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-105">This tutorial is part three of a series that teaches you how to create, install, and uninstall templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="e6ea8-106">Nesta parte da série, você aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="e6ea8-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="e6ea8-107">Criar um \* projeto. csproj para criar um pacote de modelos</span><span class="sxs-lookup"><span data-stu-id="e6ea8-107">Create a \*.csproj project to build a template pack</span></span>
> * <span data-ttu-id="e6ea8-108">Configurar o arquivo de projeto para empacotamento</span><span class="sxs-lookup"><span data-stu-id="e6ea8-108">Configure the project file for packing</span></span>
> * <span data-ttu-id="e6ea8-109">Instalar o modelo de um arquivo do pacote NuGet</span><span class="sxs-lookup"><span data-stu-id="e6ea8-109">Install a template from a NuGet package file</span></span>
> * <span data-ttu-id="e6ea8-110">Desinstalar um modelo pela ID do pacote</span><span class="sxs-lookup"><span data-stu-id="e6ea8-110">Uninstall a template by package ID</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6ea8-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e6ea8-111">Prerequisites</span></span>

* <span data-ttu-id="e6ea8-112">Conclua a [parte 1](cli-templates-create-item-template.md) e a [parte 2](cli-templates-create-project-template.md) desta série de tutoriais.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-112">Complete [part 1](cli-templates-create-item-template.md) and [part 2](cli-templates-create-project-template.md) of this tutorial series.</span></span>

  <span data-ttu-id="e6ea8-113">Este tutorial usa os dois modelos criados nas duas primeiras partes deste tutorial.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-113">This tutorial uses the two templates created in the first two parts of this tutorial.</span></span> <span data-ttu-id="e6ea8-114">Você pode usar um modelo diferente, desde que copie o modelo, como uma pasta, na pasta _working\templates \\_ .</span><span class="sxs-lookup"><span data-stu-id="e6ea8-114">You can use a different template as long as you copy the template, as a folder, into the _working\templates\\_ folder.</span></span>

* <span data-ttu-id="e6ea8-115">Abra um terminal e navegue até a pasta de _trabalho \\_ .</span><span class="sxs-lookup"><span data-stu-id="e6ea8-115">Open a terminal and navigate to the _working\\_ folder.</span></span>

## <a name="create-a-template-pack-project"></a><span data-ttu-id="e6ea8-116">Criar um projeto de pacote de modelos</span><span class="sxs-lookup"><span data-stu-id="e6ea8-116">Create a template pack project</span></span>

<span data-ttu-id="e6ea8-117">Um pacote de modelos é um ou mais modelos empacotados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-117">A template pack is one or more templates packaged into a file.</span></span> <span data-ttu-id="e6ea8-118">Quando você instala ou desinstala um pacote, todos os modelos contidos no pacote são adicionados ou removidos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-118">When you install or uninstall a pack, all templates contained in the pack are added or removed, respectively.</span></span> <span data-ttu-id="e6ea8-119">As partes anteriores desta série de tutoriais só funcionavam com modelos individuais.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-119">The previous parts of this tutorial series only worked with individual templates.</span></span> <span data-ttu-id="e6ea8-120">Para compartilhar um modelo não empacotado, você precisa copiar a pasta de modelos e instalá-la por meio dessa pasta.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-120">To share a non-packed template, you have to copy the template folder and install via that folder.</span></span> <span data-ttu-id="e6ea8-121">Como um pacote de modelos pode ter mais de um modelo e é um arquivo único, o compartilhamento é mais fácil.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-121">Because a template pack can have more than one template in it, and is a single file, sharing is easier.</span></span>

<span data-ttu-id="e6ea8-122">Os pacotes de modelos são representados por um arquivo (_.nupkg_) do pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-122">Template packs are represented by a NuGet package (_.nupkg_) file.</span></span> <span data-ttu-id="e6ea8-123">E, como qualquer pacote NuGet, você pode carregar o pacote de modelos em um feed do NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-123">And, like any NuGet package, you can upload the template pack to a NuGet feed.</span></span> <span data-ttu-id="e6ea8-124">O comando `dotnet new -i` dá suporte à instalação do pacote de modelos de um feed do pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-124">The `dotnet new -i` command supports installing template pack from a NuGet package feed.</span></span> <span data-ttu-id="e6ea8-125">Além disso, você pode instalar um pacote de modelos de um arquivo _.nupkg_ diretamente.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-125">Additionally, you can install a template pack from a _.nupkg_ file directly.</span></span>

<span data-ttu-id="e6ea8-126">Normalmente você usa um arquivo de projeto C# para compilar o código e produzir um binário.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-126">Normally you use a C# project file to compile code and produce a binary.</span></span> <span data-ttu-id="e6ea8-127">No entanto, o projeto também pode ser usado para gerar um pacote de modelos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-127">However, the project can also be used to generate a template pack.</span></span> <span data-ttu-id="e6ea8-128">Com a alteração das configurações do _.csproj_, você pode evitar que ele compile códigos e, em vez disso, inclua todos os recursos dos modelos como recursos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-128">By changing the settings of the _.csproj_, you can prevent it from compiling any code and instead include all the assets of your templates as resources.</span></span> <span data-ttu-id="e6ea8-129">Quando esse projeto é compilado, ele produz um pacote NuGet do pacote de modelos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-129">When this project is built, it produces a template pack NuGet package.</span></span>

<span data-ttu-id="e6ea8-130">O pacote que você criará incluirá o [modelo de item](cli-templates-create-item-template.md) e o [modelo de pacote](cli-templates-create-project-template.md) criados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-130">The pack you'll create will include the [item template](cli-templates-create-item-template.md) and [package template](cli-templates-create-project-template.md) previously created.</span></span> <span data-ttu-id="e6ea8-131">Como agrupamos os dois modelos na pasta _working\templates\\_, podemos usar a pasta _working_ para o arquivo _.csproj_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-131">Because we grouped the two templates into the _working\templates\\_ folder, we can use the _working_ folder for the _.csproj_ file.</span></span>

<span data-ttu-id="e6ea8-132">No terminal, navegue até a pasta _working_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-132">In your terminal, navigate to the _working_ folder.</span></span> <span data-ttu-id="e6ea8-133">Crie um novo projeto, defina o nome como `templatepack` e a pasta de saída para a pasta atual.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-133">Create a new project and set the name to `templatepack` and the output folder to the current folder.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

<span data-ttu-id="e6ea8-134">O `-n` parâmetro define o nome de arquivo _. csproj_ como _templatepack. csproj_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-134">The `-n` parameter sets the _.csproj_ filename to _templatepack.csproj_.</span></span> <span data-ttu-id="e6ea8-135">O `-o` parâmetro cria os arquivos no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-135">The `-o` parameter creates the files in the current directory.</span></span> <span data-ttu-id="e6ea8-136">Você verá um resultado semelhante à seguinte saída.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-136">You should see a result similar to the following output.</span></span>

```dotnetcli
dotnet new console -n templatepack -o .
```

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

<span data-ttu-id="e6ea8-137">Em seguida, abra o arquivo _templatepack.csproj_ em seu editor favorito e substitua o conteúdo pelo seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="e6ea8-137">Next, open the _templatepack.csproj_ file in your favorite editor and replace the content with the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>

    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
    <NoWarn>$(NoWarn);NU5128</NoWarn>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="e6ea8-138">As configurações `<PropertyGroup>` no XML acima estão divididas em três grupos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-138">The `<PropertyGroup>` settings in the XML above is broken into three groups.</span></span> <span data-ttu-id="e6ea8-139">O primeiro grupo lida com as propriedades necessárias para um pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-139">The first group deals with properties required for a NuGet package.</span></span> <span data-ttu-id="e6ea8-140">As três configurações `<Package*>` têm a ver com as propriedades do pacote NuGet para identificar seu pacote em um feed do NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-140">The three `<Package*>` settings have to do with the NuGet package properties to identify your package on a NuGet feed.</span></span> <span data-ttu-id="e6ea8-141">Especificamente, o valor `<PackageId>` é usado para desinstalar o pacote de modelos com um único nome em vez de um caminho de diretório.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-141">Specifically the `<PackageId>` value is used to uninstall the template pack with a single name instead of a directory path.</span></span> <span data-ttu-id="e6ea8-142">Ele também pode ser usado para instalar o pacote de modelos de um feed do NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-142">It can also be used to install the template pack from a NuGet feed.</span></span> <span data-ttu-id="e6ea8-143">As configurações restantes, como `<Title>` e `<PackageTags>`, têm a ver com os metadados exibidos no feed do NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-143">The remaining settings such as `<Title>` and `<PackageTags>` have to do with metadata displayed on the NuGet feed.</span></span> <span data-ttu-id="e6ea8-144">Para saber mais sobre as configurações do NuGet, confira [Propriedades do NuGet e do MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="e6ea8-144">For more information about NuGet settings, see [NuGet and MSBuild properties](/nuget/reference/msbuild-targets).</span></span>

<span data-ttu-id="e6ea8-145">A configuração `<TargetFramework>` deve ser definida para que o MSBuild seja executado corretamente quando você executar o comando do pacote para compilar e empacotar o projeto.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-145">The `<TargetFramework>` setting must be set so that MSBuild will run properly when you run the pack command to compile and pack the project.</span></span>

<span data-ttu-id="e6ea8-146">As próximas três configurações devem ser feitas com a configuração correta do projeto para incluir os modelos na pasta apropriada no pacote NuGet quando ele é criado.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-146">The next three settings have to do with configuring the project correctly to include the templates in the appropriate folder in the NuGet pack when it's created.</span></span>

<span data-ttu-id="e6ea8-147">A última configuração suprime uma mensagem de aviso que não se aplica aos projetos do pacote de modelos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-147">The last setting suppresses a warning message that doesn't apply to template pack projects.</span></span>

<span data-ttu-id="e6ea8-148">O `<ItemGroup>` contém duas configurações.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-148">The `<ItemGroup>` contains two settings.</span></span> <span data-ttu-id="e6ea8-149">Primeiro, a configuração `<Content>` inclui tudo que se encontra na pasta _templates_ como conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-149">First, the `<Content>` setting includes everything in the _templates_ folder as content.</span></span> <span data-ttu-id="e6ea8-150">Ele também é configurado para excluir a pasta _bin_ ou _obj_ para evitar que qualquer código compilado (se você testou e compilou seus modelos) seja incluído.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-150">It's also set to exclude any _bin_ folder or _obj_ folder to prevent any compiled code (if you tested and compiled your templates) from being included.</span></span> <span data-ttu-id="e6ea8-151">Segundo, a configuração `<Compile>` exclui a compilação de todos os arquivos de código, independentemente de onde eles estejam localizados.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-151">Second, the `<Compile>` setting excludes all code files from compiling no matter where they're located.</span></span> <span data-ttu-id="e6ea8-152">Essa configuração impede que o projeto usado para criar um pacote de modelos tente compilar o código na hierarquia de pastas _templates_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-152">This setting prevents the project being used to create a template pack from trying to compile the code in the _templates_ folder hierarchy.</span></span>

## <a name="build-and-install"></a><span data-ttu-id="e6ea8-153">Compilar e instalar</span><span class="sxs-lookup"><span data-stu-id="e6ea8-153">Build and install</span></span>

<span data-ttu-id="e6ea8-154">Salve esse arquivo e execute o comando do pacote</span><span class="sxs-lookup"><span data-stu-id="e6ea8-154">Save this file and then run the pack command</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="e6ea8-155">Esse comando criará seu projeto e criará um pacote NuGet. A pasta deve ser _working\bin\Debug_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-155">This command will build your project and create a NuGet package in This should be the _working\bin\Debug_ folder.</span></span>

```dotnetcli
dotnet pack
```

```console
Microsoft (R) Build Engine version 16.8.0+126527ff1 for .NET
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

<span data-ttu-id="e6ea8-156">Em seguida, instale o arquivo do pacote de modelos com o comando `dotnet new -i PATH_TO_NUPKG_FILE`.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-156">Next, install the template pack file with the `dotnet new -i PATH_TO_NUPKG_FILE` command.</span></span>

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Example templates: string extensions              stringext                [C#]              Common/Code
Console Application                               console                  [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync             [C#]              Common/Console/C#9
Class library                                     classlib                 [C#], F#, VB      Common/Library
```

<span data-ttu-id="e6ea8-157">Se você baixou o pacote NuGet para um feed do NuGet, é possível usar o comando `dotnet new -i PACKAGEID`, em que `PACKAGEID` é igual à configuração `<PackageId>` do arquivo _.csproj_.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-157">If you uploaded the NuGet package to a NuGet feed, you can use the `dotnet new -i PACKAGEID` command where `PACKAGEID` is the same as the `<PackageId>` setting from the _.csproj_ file.</span></span> <span data-ttu-id="e6ea8-158">Essa ID do pacote é igual ao identificador do pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-158">This package ID is the same as the NuGet package identifier.</span></span>

## <a name="uninstall-the-template-pack"></a><span data-ttu-id="e6ea8-159">Desinstalar o pacote de modelos</span><span class="sxs-lookup"><span data-stu-id="e6ea8-159">Uninstall the template pack</span></span>

<span data-ttu-id="e6ea8-160">Não importa como você instalou o pacote de modelos, seja com o arquivo _.nupkg_ diretamente ou com o feed do NuGet, a remoção de um pacote de modelos é igual.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-160">No matter how you installed the template pack, either with the _.nupkg_ file directly or by NuGet feed, removing a template pack is the same.</span></span> <span data-ttu-id="e6ea8-161">Use o `<PackageId>` do modelo que você deseja desinstalar.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-161">Use the `<PackageId>` of the template you want to uninstall.</span></span> <span data-ttu-id="e6ea8-162">Você pode obter uma lista de modelos instalados executando o comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-162">You can get a list of templates that are installed by running the `dotnet new -u` command.</span></span>

```dotnetcli
dotnet new -u
```

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

  AdatumCorporation.Utility.Templates
    Details:
      NuGetPackageId: AdatumCorporation.Utility.Templates
      Version: 1.0.0
      Author: Me
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
    Uninstall Command:
      dotnet new -u AdatumCorporation.Utility.Templates
```

<span data-ttu-id="e6ea8-163">Execute `dotnet new -u AdatumCorporation.Utility.Templates` para desinstalar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-163">Run `dotnet new -u AdatumCorporation.Utility.Templates` to uninstall the template.</span></span> <span data-ttu-id="e6ea8-164">O comando `dotnet new` gerará informações de ajuda que devem omitir os modelos que você instalou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-164">The `dotnet new` command will output help information that should omit the templates you previously installed.</span></span>

<span data-ttu-id="e6ea8-165">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="e6ea8-165">Congratulations!</span></span> <span data-ttu-id="e6ea8-166">você instalou e desinstalou um pacote de modelos.</span><span class="sxs-lookup"><span data-stu-id="e6ea8-166">you've installed and uninstalled a template pack.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6ea8-167">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e6ea8-167">Next steps</span></span>

<span data-ttu-id="e6ea8-168">Para saber mais sobre modelos, a maioria dos quais você já aprendeu, confira o artigo [Modelos personalizados para o dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e6ea8-168">To learn more about templates, most of which you've already learned, see the [Custom templates for dotnet new](../tools/custom-templates.md) article.</span></span>

* [<span data-ttu-id="e6ea8-169">Wiki do repositório GitHub dotnet/modelagem</span><span class="sxs-lookup"><span data-stu-id="e6ea8-169">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
* [<span data-ttu-id="e6ea8-170">Repositório do GitHub de dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e6ea8-170">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
* [<span data-ttu-id="e6ea8-171">Esquema *template.json* no Repositório de Esquema JSON</span><span class="sxs-lookup"><span data-stu-id="e6ea8-171">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
