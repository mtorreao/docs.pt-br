---
title: Comparação entre project.json e csproj
description: Veja um mapeamento entre os elementos project.json e csproj.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: 7de9f623a57a6a094debd3e018edc1560d837fc2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970870"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="a3485-103">Um mapeamento entre as propriedades de project.json e csproj</span><span class="sxs-lookup"><span data-stu-id="a3485-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="a3485-104">Por [Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="a3485-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="a3485-105">Durante o desenvolvimento das ferramentas do .NET Core, foi feita uma importante alteração de design para que os arquivos *project.json* não tivessem mais suporte e, em vez disso, os projetos do .NET Core fossem movidos para o formato MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="a3485-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="a3485-106">Este artigo mostra como as configurações em *project.json* são representadas no formato MSBuild/csproj para que você saiba como usar o novo formato e entenda as alterações feitas pelas ferramentas de migração ao atualizar o projeto para a última versão da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="a3485-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span>

## <a name="the-csproj-format"></a><span data-ttu-id="a3485-107">O formato csproj</span><span class="sxs-lookup"><span data-stu-id="a3485-107">The csproj format</span></span>

<span data-ttu-id="a3485-108">O novo formato, \*.csproj, é um formato baseado em XML.</span><span class="sxs-lookup"><span data-stu-id="a3485-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="a3485-109">O exemplo a seguir mostra o nó raiz de um projeto do .NET Core que usa o `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="a3485-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="a3485-110">Para projetos Web, o SDK usado é `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="a3485-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="a3485-111">Propriedades comuns de nível superior</span><span class="sxs-lookup"><span data-stu-id="a3485-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="a3485-112">name</span><span class="sxs-lookup"><span data-stu-id="a3485-112">name</span></span>

```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="a3485-113">Não tem mais suporte.</span><span class="sxs-lookup"><span data-stu-id="a3485-113">No longer supported.</span></span> <span data-ttu-id="a3485-114">Em csproj, isso é determinado pelo nome de arquivo do projeto, que normalmente corresponde ao nome do diretório.</span><span class="sxs-lookup"><span data-stu-id="a3485-114">In csproj, this is determined by the project filename, which usually matches the directory name.</span></span> <span data-ttu-id="a3485-115">Por exemplo, `MyProjectName.csproj`.</span><span class="sxs-lookup"><span data-stu-id="a3485-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="a3485-116">Por padrão, o nome de arquivo do projeto também especifica o valor das propriedades `<AssemblyName>` e `<PackageId>`.</span><span class="sxs-lookup"><span data-stu-id="a3485-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span>

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="a3485-117">O `<AssemblyName>` terá um valor diferente de `<PackageId>` se a propriedade `buildOptions\outputName` tiver sido definida em project.json.</span><span class="sxs-lookup"><span data-stu-id="a3485-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span>
<span data-ttu-id="a3485-118">Para obter mais informações, consulte [Outras opções comuns de build](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="a3485-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="a3485-119">version</span><span class="sxs-lookup"><span data-stu-id="a3485-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```

<span data-ttu-id="a3485-120">Use as propriedades `VersionPrefix` e `VersionSuffix`:</span><span class="sxs-lookup"><span data-stu-id="a3485-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="a3485-121">Também é possível usar a propriedade `Version`, mas isso poderá substituir as configurações de versão durante o empacotamento:</span><span class="sxs-lookup"><span data-stu-id="a3485-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="a3485-122">Outras opções comuns de nível raiz</span><span class="sxs-lookup"><span data-stu-id="a3485-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="a3485-123">estruturas</span><span class="sxs-lookup"><span data-stu-id="a3485-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="a3485-124">Uma estrutura de destino</span><span class="sxs-lookup"><span data-stu-id="a3485-124">One target framework</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="a3485-125">Várias estruturas de destino</span><span class="sxs-lookup"><span data-stu-id="a3485-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="a3485-126">Use a propriedade `TargetFrameworks` para definir a lista de estruturas de destino.</span><span class="sxs-lookup"><span data-stu-id="a3485-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="a3485-127">Use ponto e vírgula para separar vários valores de estrutura.</span><span class="sxs-lookup"><span data-stu-id="a3485-127">Use semi-colon to separate multiple framework values.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="a3485-128">dependencies</span><span class="sxs-lookup"><span data-stu-id="a3485-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3485-129">Se a dependência for um **projeto** e não um pacote, o formato será diferente.</span><span class="sxs-lookup"><span data-stu-id="a3485-129">If the dependency is a **project** and not a package, the format is different.</span></span>
> <span data-ttu-id="a3485-130">Para obter mais informações, consulte a seção [Tipo de dependência](#dependency-type).</span><span class="sxs-lookup"><span data-stu-id="a3485-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="a3485-131">Metapacote .NETStandard.Library</span><span class="sxs-lookup"><span data-stu-id="a3485-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="a3485-132">Metapacote Microsoft.NETCore.App</span><span class="sxs-lookup"><span data-stu-id="a3485-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="a3485-133">O `<RuntimeFrameworkVersion>` valor no projeto migrado é determinado pela versão do SDK que está instalado.</span><span class="sxs-lookup"><span data-stu-id="a3485-133">The `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of SDK that's installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="a3485-134">Dependências de nível superior</span><span class="sxs-lookup"><span data-stu-id="a3485-134">Top-level dependencies</span></span>

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="a3485-135">Dependências por estrutura</span><span class="sxs-lookup"><span data-stu-id="a3485-135">Per-framework dependencies</span></span>

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="a3485-136">importações</span><span class="sxs-lookup"><span data-stu-id="a3485-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="a3485-137">tipo de dependência</span><span class="sxs-lookup"><span data-stu-id="a3485-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="a3485-138">tipo: projeto</span><span class="sxs-lookup"><span data-stu-id="a3485-138">type: project</span></span>

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="a3485-139">Isso detalhará a maneira pela qual o `dotnet pack --version-suffix $suffix` determina a versão de dependência de uma referência de projeto.</span><span class="sxs-lookup"><span data-stu-id="a3485-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>

#### <a name="type-build"></a><span data-ttu-id="a3485-140">tipo: build</span><span class="sxs-lookup"><span data-stu-id="a3485-140">type: build</span></span>

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="a3485-141">tipo: plataforma</span><span class="sxs-lookup"><span data-stu-id="a3485-141">type: platform</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="a3485-142">Não há nenhum equivalente em csproj.</span><span class="sxs-lookup"><span data-stu-id="a3485-142">There is no equivalent in csproj.</span></span>

## <a name="runtimes"></a><span data-ttu-id="a3485-143">runtimes</span><span class="sxs-lookup"><span data-stu-id="a3485-143">runtimes</span></span>

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="a3485-144">Aplicativos independentes (implantação independente)</span><span class="sxs-lookup"><span data-stu-id="a3485-144">Standalone apps (self-contained deployment)</span></span>

<span data-ttu-id="a3485-145">Em project.json, a definição de uma seção `runtimes` significa que o aplicativo era independente durante o build e a publicação.</span><span class="sxs-lookup"><span data-stu-id="a3485-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="a3485-146">No MSBuild, todos os projetos são *portáteis* durante o build, mas podem ser publicados como independentes.</span><span class="sxs-lookup"><span data-stu-id="a3485-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="a3485-147">Para obter mais informações, consulte [SCD (implantações independentes)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="a3485-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#publish-self-contained).</span></span>

## <a name="tools"></a><span data-ttu-id="a3485-148">tools</span><span class="sxs-lookup"><span data-stu-id="a3485-148">tools</span></span>

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="a3485-149">Não há suporte para `imports` em ferramentas em csproj.</span><span class="sxs-lookup"><span data-stu-id="a3485-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="a3485-150">As ferramentas que precisam de importações não funcionarão com o novo `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="a3485-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="a3485-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="a3485-151">buildOptions</span></span>

<span data-ttu-id="a3485-152">Consulte também [Arquivos](#files).</span><span class="sxs-lookup"><span data-stu-id="a3485-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="a3485-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="a3485-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="a3485-154">Se `emitEntryPoint` era `false`, o valor de `OutputType` é convertido em `Library`, que é o valor padrão:</span><span class="sxs-lookup"><span data-stu-id="a3485-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="a3485-155">keyFile</span><span class="sxs-lookup"><span data-stu-id="a3485-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="a3485-156">O elemento `keyFile` se expande para três propriedades no MSBuild:</span><span class="sxs-lookup"><span data-stu-id="a3485-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="a3485-157">Outras opções comuns de build</span><span class="sxs-lookup"><span data-stu-id="a3485-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="a3485-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="a3485-158">packOptions</span></span>

<span data-ttu-id="a3485-159">Consulte também [Arquivos](#files).</span><span class="sxs-lookup"><span data-stu-id="a3485-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="a3485-160">Opções comuns de pacote</span><span class="sxs-lookup"><span data-stu-id="a3485-160">Common pack options</span></span>

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIcon>ico.png</PackageIcon>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="a3485-161">Não há nenhum equivalente do elemento `owners` no MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a3485-161">There is no equivalent for the `owners` element in MSBuild.</span></span> <span data-ttu-id="a3485-162">Para `summary` o, você pode usar a `<Description>` Propriedade MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a3485-162">For `summary`, you can use the MSBuild `<Description>` property.</span></span> <span data-ttu-id="a3485-163">O valor de `summary` não é migrado automaticamente para essa propriedade, já que essa propriedade é mapeada para o [`description`](#other-common-root-level-options) elemento.</span><span class="sxs-lookup"><span data-stu-id="a3485-163">The value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#other-common-root-level-options) element.</span></span>  <span data-ttu-id="a3485-164">[PackageIconUrl foi preterido](/nuget/reference/msbuild-targets#packageiconurl) em favor de PackageIcon.</span><span class="sxs-lookup"><span data-stu-id="a3485-164">[PackageIconUrl is deprecated](/nuget/reference/msbuild-targets#packageiconurl) in favor of PackageIcon.</span></span>

## <a name="scripts"></a><span data-ttu-id="a3485-165">scripts</span><span class="sxs-lookup"><span data-stu-id="a3485-165">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="a3485-166">Seus equivalentes no MSBuild são [destinos](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="a3485-166">Their equivalents in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a><span data-ttu-id="a3485-167">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="a3485-167">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="a3485-168">Todas as configurações nesse grupo, exceto para a `System.GC.Server` propriedade, são colocadas em um arquivo chamado *runtimeconfig.template.js* na pasta do projeto, com opções levantadas para o objeto raiz durante o processo de migração:</span><span class="sxs-lookup"><span data-stu-id="a3485-168">All settings in this group, except for the `System.GC.Server` property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="a3485-169">A `System.GC.Server` propriedade é migrada para o arquivo csproj:</span><span class="sxs-lookup"><span data-stu-id="a3485-169">The `System.GC.Server` property is migrated into the csproj file:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="a3485-170">No entanto, é possível definir todos esses valores em csproj, bem como propriedades do MSBuild:</span><span class="sxs-lookup"><span data-stu-id="a3485-170">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="a3485-171">shared</span><span class="sxs-lookup"><span data-stu-id="a3485-171">shared</span></span>

```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="a3485-172">Sem suporte em csproj.</span><span class="sxs-lookup"><span data-stu-id="a3485-172">Not supported in csproj.</span></span> <span data-ttu-id="a3485-173">Em vez disso, Crie arquivos de conteúdo de inclusão em seu arquivo *. nuspec* .</span><span class="sxs-lookup"><span data-stu-id="a3485-173">Instead, create include content files in your *.nuspec* file.</span></span>
<span data-ttu-id="a3485-174">Para obter mais informações, consulte [Incluindo arquivos de conteúdo](/nuget/schema/nuspec#including-content-files).</span><span class="sxs-lookup"><span data-stu-id="a3485-174">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="a3485-175">files</span><span class="sxs-lookup"><span data-stu-id="a3485-175">files</span></span>

<span data-ttu-id="a3485-176">Em *project.json*, o build e o pacote poderão ser estendidos para serem compilados e inseridos de pastas diferentes.</span><span class="sxs-lookup"><span data-stu-id="a3485-176">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="a3485-177">No MSBuild, isso é feito com [itens](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="a3485-177">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="a3485-178">O seguinte exemplo é uma conversão comum:</span><span class="sxs-lookup"><span data-stu-id="a3485-178">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="a3485-179">Muitos dos [padrões de recurso de curinga](https://en.wikipedia.org/wiki/Glob_(programming)) são adicionados automaticamente pelo SDK do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a3485-179">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span> <span data-ttu-id="a3485-180">Para obter mais informações, consulte a [compilação padrão inclui](../project-sdk/overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="a3485-180">For more information, see [Default compilation includes](../project-sdk/overview.md#default-includes-and-excludes).</span></span>

<span data-ttu-id="a3485-181">Todos os elementos `ItemGroup` do MSBuild dão suporte a `Include`, `Exclude` e `Remove`.</span><span class="sxs-lookup"><span data-stu-id="a3485-181">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="a3485-182">O layout do pacote dentro do .nupkg pode ser modificado com `PackagePath="path"`.</span><span class="sxs-lookup"><span data-stu-id="a3485-182">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="a3485-183">Com exceção de `Content`, a maioria dos grupos de itens exige a adição explícita de `Pack="true"` a ser incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="a3485-183">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="a3485-184">`Content` será colocado na pasta *conteúdo* de um pacote, pois a propriedade `<IncludeContentInPack>` do MSBuild está definida como `true` por padrão.</span><span class="sxs-lookup"><span data-stu-id="a3485-184">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span>
<span data-ttu-id="a3485-185">Para obter mais informações, consulte [Incluindo conteúdo em um pacote](/nuget/schema/msbuild-targets#including-content-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="a3485-185">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="a3485-186">`PackagePath="%(Identity)"` é uma maneira curta de configurar o caminho do pacote para o caminho do arquivo relativo do projeto.</span><span class="sxs-lookup"><span data-stu-id="a3485-186">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="a3485-187">testRunner</span><span class="sxs-lookup"><span data-stu-id="a3485-187">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="a3485-188">xUnit</span><span class="sxs-lookup"><span data-stu-id="a3485-188">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="a3485-189">MSTest</span><span class="sxs-lookup"><span data-stu-id="a3485-189">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="a3485-190">Veja também</span><span class="sxs-lookup"><span data-stu-id="a3485-190">See also</span></span>

- [<span data-ttu-id="a3485-191">Visão geral de alto nível das alterações na CLI</span><span class="sxs-lookup"><span data-stu-id="a3485-191">High-level overview of changes in CLI</span></span>](cli-msbuild-architecture.md)
