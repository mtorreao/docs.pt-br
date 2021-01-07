---
title: Propriedades do MSBuild para Microsoft. NET. Sdk
description: Referência para as propriedades e os itens do MSBuild que são compreendidos pelo SDK do .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: e7deb8c32fd01452524122e41f758ab037020ee4
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970701"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="74064-103">Referência do MSBuild para projetos do SDK do .NET</span><span class="sxs-lookup"><span data-stu-id="74064-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="74064-104">Esta página é uma referência para as propriedades e os itens do MSBuild que você pode usar para configurar projetos do .NET.</span><span class="sxs-lookup"><span data-stu-id="74064-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="74064-105">Esta página é um trabalho em andamento e não lista todas as propriedades de MSBuild úteis para o SDK do .NET.</span><span class="sxs-lookup"><span data-stu-id="74064-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="74064-106">Para obter uma lista de propriedades comuns do MSBuild, consulte [Propriedades comuns do MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="74064-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="74064-107">Propriedades da estrutura</span><span class="sxs-lookup"><span data-stu-id="74064-107">Framework properties</span></span>

- [<span data-ttu-id="74064-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="74064-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="74064-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="74064-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="74064-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="74064-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="74064-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="74064-111">TargetFramework</span></span>

<span data-ttu-id="74064-112">A `TargetFramework` propriedade especifica a versão do Framework de destino para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="74064-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="74064-113">Para obter uma lista de monikers de estrutura de destino válidos, consulte [estruturas de destino em projetos em estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="74064-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="74064-114">Para obter mais informações, consulte [estruturas de destino em projetos em estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="74064-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="74064-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="74064-115">TargetFrameworks</span></span>

<span data-ttu-id="74064-116">Use a `TargetFrameworks` propriedade quando desejar que seu aplicativo direcione várias plataformas.</span><span class="sxs-lookup"><span data-stu-id="74064-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="74064-117">Para obter uma lista de monikers de estrutura de destino válidos, consulte [estruturas de destino em projetos em estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="74064-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="74064-118">Essa propriedade será ignorada se `TargetFramework` (singular) for especificado.</span><span class="sxs-lookup"><span data-stu-id="74064-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="74064-119">Para obter mais informações, consulte [estruturas de destino em projetos em estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="74064-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="74064-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="74064-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="74064-121">Essa propriedade só se aplica a projetos que usam o `netstandard1.x` .</span><span class="sxs-lookup"><span data-stu-id="74064-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="74064-122">Ele não se aplica a projetos que usam o `netstandard2.x` .</span><span class="sxs-lookup"><span data-stu-id="74064-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="74064-123">Use a `NetStandardImplicitPackageVersion` propriedade quando desejar especificar uma versão de estrutura inferior à versão do metapacote.</span><span class="sxs-lookup"><span data-stu-id="74064-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="74064-124">O arquivo de projeto no exemplo a seguir tem `netstandard1.3` como destino, mas usa a versão 1.6.0 do `NETStandard.Library` .</span><span class="sxs-lookup"><span data-stu-id="74064-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="74064-125">Propriedades do pacote</span><span class="sxs-lookup"><span data-stu-id="74064-125">Package properties</span></span>

<span data-ttu-id="74064-126">Você pode especificar propriedades como `PackageId` ,, `PackageVersion` , `PackageIcon` `Title` e `Description` para descrever o pacote que é criado a partir do seu projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="74064-127">Para obter informações sobre essas e outras propriedades, consulte [pacote de destino](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="74064-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="74064-128">Publicar Propriedades e itens</span><span class="sxs-lookup"><span data-stu-id="74064-128">Publish properties and items</span></span>

- [<span data-ttu-id="74064-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="74064-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="74064-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="74064-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="74064-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="74064-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="74064-132">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="74064-132">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="74064-133">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="74064-133">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="74064-134">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="74064-134">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="74064-135">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="74064-135">UseAppHost</span></span>](#useapphost)

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="74064-136">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="74064-136">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="74064-137">A `AppendTargetFrameworkToOutputPath` propriedade controla se o [moniker da estrutura de destino (TFM)](../../standard/frameworks.md) é anexado ao caminho de saída (que é definido por [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span><span class="sxs-lookup"><span data-stu-id="74064-137">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="74064-138">O SDK do .NET acrescenta automaticamente a estrutura de destino e, se presente, o identificador de tempo de execução ao caminho de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-138">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="74064-139">`AppendTargetFrameworkToOutputPath`A configuração para `false` impede que o TFM seja anexado ao caminho de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-139">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="74064-140">No entanto, sem o TFM no caminho de saída, vários artefatos de compilação podem substituir um ao outro.</span><span class="sxs-lookup"><span data-stu-id="74064-140">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="74064-141">Por exemplo, para um aplicativo .NET 5,0, o caminho de saída muda de `bin\Debug\net5.0` para `bin\Debug` com a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="74064-141">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="74064-142">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="74064-142">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="74064-143">A `AppendRuntimeIdentifierToOutputPath` propriedade controla se o [RID (identificador de tempo de execução)](../rid-catalog.md) é anexado ao caminho de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-143">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="74064-144">O SDK do .NET acrescenta automaticamente a estrutura de destino e, se presente, o identificador de tempo de execução ao caminho de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-144">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="74064-145">`AppendRuntimeIdentifierToOutputPath`A configuração para `false` impede que o RID seja anexado ao caminho de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-145">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="74064-146">Por exemplo, para um aplicativo .NET 5,0 e um RID do `win10-x64` , o caminho de saída muda de `bin\Debug\net5.0\win10-x64` para `bin\Debug\net5.0` com a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="74064-146">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="74064-147">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="74064-147">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="74064-148">A `CopyLocalLockFileAssemblies` propriedade é útil para projetos de plug-in que têm dependências em outras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="74064-148">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="74064-149">Se você definir essa propriedade como `true` , todas as dependências de pacote NuGet serão copiadas para o diretório de saída.</span><span class="sxs-lookup"><span data-stu-id="74064-149">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="74064-150">Isso significa que você pode usar a saída de `dotnet build` para executar o plug-in em qualquer computador.</span><span class="sxs-lookup"><span data-stu-id="74064-150">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="74064-151">Como alternativa, você pode usar `dotnet publish` para publicar a biblioteca de classes.</span><span class="sxs-lookup"><span data-stu-id="74064-151">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="74064-152">Para obter mais informações, consulte [dotnet Publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="74064-152">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="74064-153">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="74064-153">RuntimeIdentifier</span></span>

<span data-ttu-id="74064-154">A `RuntimeIdentifier` propriedade permite que você especifique um único [identificador de tempo de execução (RID)](../rid-catalog.md) para o projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-154">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="74064-155">O RID permite a publicação de uma implantação autossuficiente.</span><span class="sxs-lookup"><span data-stu-id="74064-155">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="74064-156">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="74064-156">RuntimeIdentifiers</span></span>

<span data-ttu-id="74064-157">A `RuntimeIdentifiers` propriedade permite que você especifique uma lista delimitada por ponto-e-vírgula de [RIDs (identificadores de tempo de execução)](../rid-catalog.md) para o projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-157">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="74064-158">Use essa propriedade se você precisar publicar para vários tempos de execução.</span><span class="sxs-lookup"><span data-stu-id="74064-158">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="74064-159">`RuntimeIdentifiers` é usado no momento da restauração para garantir que os ativos corretos estejam no grafo.</span><span class="sxs-lookup"><span data-stu-id="74064-159">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="74064-160">`RuntimeIdentifier` (singular) pode fornecer compilações mais rápidas quando apenas um único tempo de execução é necessário.</span><span class="sxs-lookup"><span data-stu-id="74064-160">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="74064-161">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="74064-161">TrimmerRootAssembly</span></span>

<span data-ttu-id="74064-162">O `TrimmerRootAssembly` Item permite que você exclua um assembly de [*corte*](../deploying/trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="74064-162">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="74064-163">O corte é o processo de remover partes não usadas do tempo de execução de um aplicativo empacotado.</span><span class="sxs-lookup"><span data-stu-id="74064-163">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="74064-164">Em alguns casos, a remoção pode remover incorretamente as referências necessárias.</span><span class="sxs-lookup"><span data-stu-id="74064-164">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="74064-165">O XML a seguir exclui o `System.Security` assembly de corte.</span><span class="sxs-lookup"><span data-stu-id="74064-165">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="74064-166">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="74064-166">UseAppHost</span></span>

<span data-ttu-id="74064-167">A `UseAppHost` propriedade controla se um executável nativo é criado para uma implantação ou não.</span><span class="sxs-lookup"><span data-stu-id="74064-167">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="74064-168">Um executável nativo é necessário para implantações independentes.</span><span class="sxs-lookup"><span data-stu-id="74064-168">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="74064-169">No .NET Core 3,0 e versões posteriores, um executável dependente da estrutura é criado por padrão.</span><span class="sxs-lookup"><span data-stu-id="74064-169">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="74064-170">Defina a `UseAppHost` propriedade como `false` para desabilitar a geração do executável.</span><span class="sxs-lookup"><span data-stu-id="74064-170">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="74064-171">Para obter mais informações sobre a implantação, consulte [implantação de aplicativos .net](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="74064-171">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="74064-172">Compilar propriedades</span><span class="sxs-lookup"><span data-stu-id="74064-172">Compile properties</span></span>

- [<span data-ttu-id="74064-173">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="74064-173">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="74064-174">LangVersion</span><span class="sxs-lookup"><span data-stu-id="74064-174">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="74064-175">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="74064-175">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="74064-176">A `EmbeddedResourceUseDependentUponConvention` propriedade define se os nomes de arquivo de manifesto de recurso são gerados a partir de informações de tipo em arquivos de origem que são colocados com arquivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="74064-176">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="74064-177">Por exemplo, se *Form1. resx* estiver na mesma pasta que *Form1.cs* e `EmbeddedResourceUseDependentUponConvention` for definido como `true` , o arquivo *. Resources* gerado usará seu nome do primeiro tipo definido em *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="74064-177">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="74064-178">Por exemplo, se `MyNamespace.Form1` for o primeiro tipo definido em *Form1.cs*, o nome de arquivo gerado *será MyNamespace. Form1. Resources*.</span><span class="sxs-lookup"><span data-stu-id="74064-178">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="74064-179">Se `LogicalName` `ManifestResourceName` os metadados,, ou `DependentUpon` forem especificados para um `EmbeddedResource` Item, o nome do arquivo de manifesto gerado para esse arquivo de recurso será baseado nesses metadados em vez disso.</span><span class="sxs-lookup"><span data-stu-id="74064-179">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="74064-180">Por padrão, em um novo projeto .NET, essa propriedade é definida como `true` .</span><span class="sxs-lookup"><span data-stu-id="74064-180">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="74064-181">Se for definido como `false` , e não `LogicalName` , ou os `ManifestResourceName` `DependentUpon` metadados forem especificados para o `EmbeddedResource` item no arquivo de projeto, o nome do arquivo de manifesto de recurso será baseado no namespace raiz do projeto e no caminho de arquivo relativo para o arquivo *. resx* .</span><span class="sxs-lookup"><span data-stu-id="74064-181">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="74064-182">Para obter mais informações, consulte [como os arquivos de manifesto de recurso são nomeados](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="74064-182">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="74064-183">LangVersion</span><span class="sxs-lookup"><span data-stu-id="74064-183">LangVersion</span></span>

<span data-ttu-id="74064-184">A `LangVersion` propriedade permite especificar uma versão de linguagem de programação específica.</span><span class="sxs-lookup"><span data-stu-id="74064-184">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="74064-185">Por exemplo, se você quiser acessar os recursos do C# Preview, defina `LangVersion` como `preview` .</span><span class="sxs-lookup"><span data-stu-id="74064-185">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="74064-186">Para obter mais informações, consulte [controle de versão da linguagem C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="74064-186">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="74064-187">Propriedades de inclusão de item padrão</span><span class="sxs-lookup"><span data-stu-id="74064-187">Default item inclusion properties</span></span>

- [<span data-ttu-id="74064-188">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="74064-188">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="74064-189">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="74064-189">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="74064-190">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="74064-190">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="74064-191">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="74064-191">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="74064-192">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="74064-192">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="74064-193">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="74064-193">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="74064-194">Para obter mais informações, consulte [inclusões e exclusões padrão](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="74064-194">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="74064-195">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="74064-195">DefaultItemExcludes</span></span>

<span data-ttu-id="74064-196">Use a `DefaultItemExcludes` propriedade para definir padrões de glob para arquivos e pastas que devem ser excluídos do globs de inclusão, exclusão e remoção.</span><span class="sxs-lookup"><span data-stu-id="74064-196">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="74064-197">Por padrão, as pastas *./bin* e *./obj* são excluídas dos padrões de glob.</span><span class="sxs-lookup"><span data-stu-id="74064-197">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="74064-198">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="74064-198">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="74064-199">Use a `DefaultExcludesInProjectFolder` propriedade para definir padrões de glob para arquivos e pastas na pasta do projeto que deve ser excluída da inclusão, exclusão e remoção de globs.</span><span class="sxs-lookup"><span data-stu-id="74064-199">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="74064-200">Por padrão, as pastas que começam com um ponto ( `.` ), como *. git* e *. vs*, são excluídas dos padrões de glob.</span><span class="sxs-lookup"><span data-stu-id="74064-200">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="74064-201">Essa propriedade é muito semelhante à `DefaultItemExcludes` propriedade, exceto pelo fato de que ela só considera arquivos e pastas na pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-201">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="74064-202">Quando um padrão glob não corresponde intencionalmente a itens fora da pasta do projeto com um caminho relativo, use a `DefaultExcludesInProjectFolder` propriedade em vez da `DefaultItemExcludes` propriedade.</span><span class="sxs-lookup"><span data-stu-id="74064-202">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="74064-203">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="74064-203">EnableDefaultItems</span></span>

<span data-ttu-id="74064-204">A `EnableDefaultItems` propriedade controla se os itens de compilação, itens de recursos inseridos e `None` itens são incluídos implicitamente no projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-204">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="74064-205">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="74064-205">The default value is `true`.</span></span> <span data-ttu-id="74064-206">Defina a `EnableDefaultItems` propriedade como `false` para desabilitar toda a inclusão de arquivo implícita.</span><span class="sxs-lookup"><span data-stu-id="74064-206">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="74064-207">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="74064-207">EnableDefaultCompileItems</span></span>

<span data-ttu-id="74064-208">A `EnableDefaultCompileItems` propriedade controla se os itens de compilação são incluídos implicitamente no projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-208">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="74064-209">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="74064-209">The default value is `true`.</span></span> <span data-ttu-id="74064-210">Defina a `EnableDefaultCompileItems` propriedade como `false` para desabilitar a inclusão implícita de \*. cs e outros arquivos de extensão de idioma.</span><span class="sxs-lookup"><span data-stu-id="74064-210">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="74064-211">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="74064-211">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="74064-212">A `EnableDefaultEmbeddedResourceItems` propriedade controla se os itens de recurso incorporados estão implicitamente incluídos no projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-212">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="74064-213">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="74064-213">The default value is `true`.</span></span> <span data-ttu-id="74064-214">Defina a `EnableDefaultEmbeddedResourceItems` propriedade como `false` para desabilitar a inclusão implícita de arquivos de recursos inseridos.</span><span class="sxs-lookup"><span data-stu-id="74064-214">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="74064-215">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="74064-215">EnableDefaultNoneItems</span></span>

<span data-ttu-id="74064-216">A `EnableDefaultNoneItems` propriedade controla se os `None` itens (arquivos que não têm nenhuma função no processo de compilação) são incluídos implicitamente no projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-216">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="74064-217">O valor padrão é `true`.</span><span class="sxs-lookup"><span data-stu-id="74064-217">The default value is `true`.</span></span> <span data-ttu-id="74064-218">Defina a `EnableDefaultNoneItems` propriedade como `false` para desabilitar a inclusão implícita de `None` itens.</span><span class="sxs-lookup"><span data-stu-id="74064-218">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="74064-219">Propriedades de análise de código</span><span class="sxs-lookup"><span data-stu-id="74064-219">Code analysis properties</span></span>

- [<span data-ttu-id="74064-220">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="74064-220">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="74064-221">Analysismode</span><span class="sxs-lookup"><span data-stu-id="74064-221">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="74064-222">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="74064-222">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="74064-223">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="74064-223">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="74064-224">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="74064-224">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="74064-225">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="74064-225">AnalysisLevel</span></span>

<span data-ttu-id="74064-226">A `AnalysisLevel` propriedade permite especificar um nível de análise de código.</span><span class="sxs-lookup"><span data-stu-id="74064-226">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="74064-227">Por exemplo, se você quiser acessar analisadores de código de visualização, defina `AnalysisLevel` como `preview` .</span><span class="sxs-lookup"><span data-stu-id="74064-227">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="74064-228">O valor padrão é `latest`.</span><span class="sxs-lookup"><span data-stu-id="74064-228">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="74064-229">A tabela a seguir mostra as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74064-229">The following table shows the available options.</span></span>

| <span data-ttu-id="74064-230">Valor</span><span class="sxs-lookup"><span data-stu-id="74064-230">Value</span></span> | <span data-ttu-id="74064-231">Significado</span><span class="sxs-lookup"><span data-stu-id="74064-231">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="74064-232">Os analisadores de código mais recentes que foram lançados são usados.</span><span class="sxs-lookup"><span data-stu-id="74064-232">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="74064-233">Este é o padrão.</span><span class="sxs-lookup"><span data-stu-id="74064-233">This is the default.</span></span> |
| `preview` | <span data-ttu-id="74064-234">Os analisadores de código mais recentes são usados, mesmo se estiverem em versão prévia.</span><span class="sxs-lookup"><span data-stu-id="74064-234">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="74064-235">O conjunto de regras que foi habilitado para a versão 5,0 do .NET é usado, mesmo se as regras mais recentes estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74064-235">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="74064-236">O conjunto de regras que foi habilitado para a versão 5,0 do .NET é usado, mesmo se as regras mais recentes estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74064-236">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="74064-237">Analysismode</span><span class="sxs-lookup"><span data-stu-id="74064-237">AnalysisMode</span></span>

<span data-ttu-id="74064-238">A partir do .NET 5,0, o SDK do .NET é fornecido com todas as [regras de qualidade de código "CA"](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="74064-238">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="74064-239">Por padrão, somente [algumas regras são habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como avisos de compilação.</span><span class="sxs-lookup"><span data-stu-id="74064-239">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="74064-240">A `AnalysisMode` propriedade permite que você personalize o conjunto de regras habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="74064-240">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="74064-241">Você pode alternar para um modo de análise mais agressivo (recusar) ou um modo de análise mais conservador (opcional).</span><span class="sxs-lookup"><span data-stu-id="74064-241">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="74064-242">Por exemplo, se você quiser habilitar todas as regras por padrão como avisos de compilação, defina o valor como `AllEnabledByDefault` .</span><span class="sxs-lookup"><span data-stu-id="74064-242">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="74064-243">A tabela a seguir mostra as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="74064-243">The following table shows the available options.</span></span>

| <span data-ttu-id="74064-244">Valor</span><span class="sxs-lookup"><span data-stu-id="74064-244">Value</span></span> | <span data-ttu-id="74064-245">Significado</span><span class="sxs-lookup"><span data-stu-id="74064-245">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="74064-246">Modo padrão, em que determinadas regras são habilitadas como avisos de compilação, determinadas regras são habilitadas como sugestões de IDE do Visual Studio e o restante é desabilitado.</span><span class="sxs-lookup"><span data-stu-id="74064-246">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="74064-247">Modo agressivo ou de aceitação, em que todas as regras são habilitadas por padrão como avisos de compilação.</span><span class="sxs-lookup"><span data-stu-id="74064-247">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="74064-248">Você pode [recusar](../../fundamentals/code-analysis/configuration-options.md) seletivamente as regras individuais para desabilitá-las.</span><span class="sxs-lookup"><span data-stu-id="74064-248">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="74064-249">Modo conservador ou opt, onde todas as regras estão desabilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="74064-249">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="74064-250">Você pode [optar](../../fundamentals/code-analysis/configuration-options.md) seletivamente por regras individuais para habilitá-las.</span><span class="sxs-lookup"><span data-stu-id="74064-250">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="74064-251">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="74064-251">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="74064-252">A `CodeAnalysisTreatWarningsAsErrors` propriedade permite que você configure se os avisos de análise de qualidade de código (CAxxxx) devem ser tratados como avisos e interromper a compilação.</span><span class="sxs-lookup"><span data-stu-id="74064-252">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="74064-253">Se você usar o `-warnaserror` sinalizador ao compilar seus projetos, os avisos de [análise de qualidade de código do .net](../../fundamentals/code-analysis/overview.md#code-quality-analysis) também serão tratados como erros.</span><span class="sxs-lookup"><span data-stu-id="74064-253">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="74064-254">Se você não quiser que os avisos de análise de qualidade de código sejam tratados como erros, você poderá definir a `CodeAnalysisTreatWarningsAsErrors` Propriedade do MSBuild como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-254">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="74064-255">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="74064-255">EnableNETAnalyzers</span></span>

<span data-ttu-id="74064-256">A [análise de qualidade de código .net](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitada, por padrão, para projetos direcionados ao .NET 5,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="74064-256">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="74064-257">Você pode habilitar a análise de código .NET para projetos destinados a versões anteriores do .NET, definindo a `EnableNETAnalyzers` propriedade como `true` .</span><span class="sxs-lookup"><span data-stu-id="74064-257">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="74064-258">Para desabilitar a análise de código em qualquer projeto, defina essa propriedade como `false` .</span><span class="sxs-lookup"><span data-stu-id="74064-258">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="74064-259">Outra maneira de habilitar a análise de código .NET em projetos que visam versões .NET anteriores ao .NET 5,0 é definir a propriedade [AnalysisLevel](#analysislevel) como `latest` .</span><span class="sxs-lookup"><span data-stu-id="74064-259">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="74064-260">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="74064-260">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="74064-261">Este recurso está experimental no momento e pode ser alterado entre as versões do .NET 5 e do .NET 6.</span><span class="sxs-lookup"><span data-stu-id="74064-261">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="74064-262">A [análise de estilo de código .net](../../fundamentals/code-analysis/overview.md#code-style-analysis) está desabilitada, por padrão, na compilação para todos os projetos .net.</span><span class="sxs-lookup"><span data-stu-id="74064-262">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="74064-263">Você pode habilitar a análise de estilo de código para projetos .NET definindo a `EnforceCodeStyleInBuild` propriedade como `true` .</span><span class="sxs-lookup"><span data-stu-id="74064-263">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="74064-264">Todas as regras de estilo de código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) para serem avisos ou erros serão executadas em violações de compilação e relatório.</span><span class="sxs-lookup"><span data-stu-id="74064-264">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="74064-265">Propriedades de configuração de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="74064-265">Run-time configuration properties</span></span>

<span data-ttu-id="74064-266">Você pode configurar alguns comportamentos de tempo de execução especificando as propriedades do MSBuild no arquivo de projeto do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="74064-266">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="74064-267">Para obter informações sobre outras maneiras de configurar o comportamento de tempo de execução, consulte [definições de configuração de tempo de execução](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="74064-267">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="74064-268">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-268">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="74064-269">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="74064-269">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="74064-270">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-270">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="74064-271">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-271">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="74064-272">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="74064-272">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="74064-273">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="74064-273">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="74064-274">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="74064-274">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="74064-275">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="74064-275">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="74064-276">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="74064-276">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="74064-277">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-277">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="74064-278">A `ConcurrentGarbageCollection` propriedade define se a [coleta de lixo em segundo plano (simultânea)](../../standard/garbage-collection/background-gc.md) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="74064-278">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="74064-279">Defina o valor como `false` para desabilitar a coleta de lixo em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="74064-279">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="74064-280">Para obter mais informações, consulte [background GC](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="74064-280">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="74064-281">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="74064-281">InvariantGlobalization</span></span>

<span data-ttu-id="74064-282">A `InvariantGlobalization` propriedade define se o aplicativo é executado no modo *invariável-globalização* , o que significa que ele não tem acesso a dados específicos de cultura.</span><span class="sxs-lookup"><span data-stu-id="74064-282">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="74064-283">Defina o valor a `true` ser executado no modo invariável-Globally.</span><span class="sxs-lookup"><span data-stu-id="74064-283">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="74064-284">Para obter mais informações, consulte [modo invariável](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="74064-284">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="74064-285">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-285">RetainVMGarbageCollection</span></span>

<span data-ttu-id="74064-286">A `RetainVMGarbageCollection` Propriedade configura o coletor de lixo para colocar os segmentos de memória excluídos em uma lista em espera para uso futuro ou liberá-los.</span><span class="sxs-lookup"><span data-stu-id="74064-286">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="74064-287">Definir o valor para `true` instruir o coletor de lixo a colocar os segmentos em uma lista de espera.</span><span class="sxs-lookup"><span data-stu-id="74064-287">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="74064-288">Para obter mais informações, consulte [reter VM](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="74064-288">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="74064-289">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="74064-289">ServerGarbageCollection</span></span>

<span data-ttu-id="74064-290">A `ServerGarbageCollection` propriedade define se o aplicativo usa a coleta de lixo da [estação de trabalho ou a coleta de lixo do servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="74064-290">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="74064-291">Defina o valor como para `true` usar a coleta de lixo do servidor.</span><span class="sxs-lookup"><span data-stu-id="74064-291">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="74064-292">Para obter mais informações, consulte [estação de trabalho versus servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="74064-292">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="74064-293">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="74064-293">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="74064-294">A `ThreadPoolMaxThreads` Propriedade configura o número máximo de threads para o pool de threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74064-294">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="74064-295">Para obter mais informações, consulte [Maximum threads](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="74064-295">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="74064-296">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="74064-296">ThreadPoolMinThreads</span></span>

<span data-ttu-id="74064-297">A `ThreadPoolMinThreads` Propriedade configura o número mínimo de threads para o pool de threads de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74064-297">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="74064-298">Para obter mais informações, consulte [mínimo de threads](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="74064-298">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="74064-299">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="74064-299">TieredCompilation</span></span>

<span data-ttu-id="74064-300">A `TieredCompilation` propriedade define se o compilador JIT (just-in-time) usa compilação em [camadas](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="74064-300">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="74064-301">Defina o valor como `false` para desabilitar a compilação em camadas.</span><span class="sxs-lookup"><span data-stu-id="74064-301">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="74064-302">Para obter mais informações, consulte [compilação em camadas](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="74064-302">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="74064-303">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="74064-303">TieredCompilationQuickJit</span></span>

<span data-ttu-id="74064-304">A `TieredCompilationQuickJit` propriedade define se o compilador JIT usa o JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="74064-304">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="74064-305">Defina o valor como `false` para desabilitar o JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="74064-305">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="74064-306">Para obter mais informações, consulte [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="74064-306">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="74064-307">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="74064-307">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="74064-308">A `TieredCompilationQuickJitForLoops` propriedade define se o compilador JIT usa o JIT rápido em métodos que contêm loops.</span><span class="sxs-lookup"><span data-stu-id="74064-308">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="74064-309">Defina o valor como `true` para habilitar o JIT rápido em métodos que contêm loops.</span><span class="sxs-lookup"><span data-stu-id="74064-309">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="74064-310">Para obter mais informações, consulte [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="74064-310">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="74064-311">Propriedades e itens de referência</span><span class="sxs-lookup"><span data-stu-id="74064-311">Reference properties and items</span></span>

- [<span data-ttu-id="74064-312">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="74064-312">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="74064-313">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="74064-313">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="74064-314">PackageReference</span><span class="sxs-lookup"><span data-stu-id="74064-314">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="74064-315">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="74064-315">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="74064-316">Referência</span><span class="sxs-lookup"><span data-stu-id="74064-316">Reference</span></span>](#reference)
- [<span data-ttu-id="74064-317">Propriedades relacionadas a restauração</span><span class="sxs-lookup"><span data-stu-id="74064-317">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="74064-318">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="74064-318">AssetTargetFallback</span></span>

<span data-ttu-id="74064-319">A `AssetTargetFallback` propriedade permite que você especifique versões de estrutura compatíveis adicionais para referências de projeto e pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="74064-319">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="74064-320">Por exemplo, se você especificar uma dependência de pacote usando `PackageReference` , mas esse pacote não contiver ativos que são compatíveis com seus projetos `TargetFramework` , a `AssetTargetFallback` Propriedade entrará em cena.</span><span class="sxs-lookup"><span data-stu-id="74064-320">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="74064-321">A compatibilidade do pacote referenciado é verificada novamente usando cada estrutura de destino especificada em `AssetTargetFallback` .</span><span class="sxs-lookup"><span data-stu-id="74064-321">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="74064-322">Você pode definir a `AssetTargetFallback` propriedade para uma ou mais [versões da estrutura de destino](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="74064-322">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="74064-323">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="74064-323">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="74064-324">A `DisableImplicitFrameworkReferences` propriedade controla itens implícitos `FrameworkReference` ao direcionar o .net Core 3,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="74064-324">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="74064-325">Ao direcionar o .NET Core 2,1 ou .NET Standard 2,0 e versões anteriores, ele controla os itens [PackageReference](#packagereference) implícitos em pacotes em um metapacote.</span><span class="sxs-lookup"><span data-stu-id="74064-325">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="74064-326">(Um metapacote é um pacote baseado em estrutura que consiste apenas em dependências em outros pacotes.) Essa propriedade também controla referências implícitas, como `System` e `System.Core` ao direcionamento de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74064-326">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="74064-327">Defina essa propriedade como `true` para Desabilitar itens implícitos `FrameworkReference` ou [PackageReference](#packagereference) .</span><span class="sxs-lookup"><span data-stu-id="74064-327">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="74064-328">Se você definir essa propriedade como `true` , poderá adicionar referências explícitas apenas às estruturas ou aos pacotes necessários.</span><span class="sxs-lookup"><span data-stu-id="74064-328">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="74064-329">PackageReference</span><span class="sxs-lookup"><span data-stu-id="74064-329">PackageReference</span></span>

<span data-ttu-id="74064-330">O `PackageReference` Item define uma referência a um pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="74064-330">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="74064-331">O atributo `Include` especifica a ID do pacote.</span><span class="sxs-lookup"><span data-stu-id="74064-331">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="74064-332">O `Version` atributo especifica a versão ou o intervalo de versão.</span><span class="sxs-lookup"><span data-stu-id="74064-332">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="74064-333">Para obter informações sobre como especificar uma versão mínima, a versão máxima, o intervalo ou a correspondência exata, consulte [intervalos de versão](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="74064-333">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="74064-334">Você também pode adicionar os seguintes metadados a uma referência de projeto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="74064-334">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="74064-335">O trecho do arquivo de projeto no exemplo a seguir faz referência ao pacote [System. Runtime](https://www.nuget.org/packages/System.Runtime/) .</span><span class="sxs-lookup"><span data-stu-id="74064-335">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="74064-336">Para obter mais informações, consulte [referências de pacote em arquivos de projeto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="74064-336">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="74064-337">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="74064-337">ProjectReference</span></span>

<span data-ttu-id="74064-338">O `ProjectReference` Item define uma referência a outro projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-338">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="74064-339">O projeto referenciado é adicionado como uma dependência de pacote NuGet, ou seja, é tratado da mesma forma que um `PackageReference` .</span><span class="sxs-lookup"><span data-stu-id="74064-339">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="74064-340">O `Include` atributo especifica o caminho para o projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-340">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="74064-341">Você também pode adicionar os seguintes metadados a uma referência de projeto: `IncludeAssets` , `ExcludeAssets` e `PrivateAssets` .</span><span class="sxs-lookup"><span data-stu-id="74064-341">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="74064-342">O trecho do arquivo de projeto no exemplo a seguir faz referência a um projeto chamado `Project2` .</span><span class="sxs-lookup"><span data-stu-id="74064-342">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="74064-343">Referência</span><span class="sxs-lookup"><span data-stu-id="74064-343">Reference</span></span>

<span data-ttu-id="74064-344">O `Reference` Item define uma referência a um arquivo de assembly.</span><span class="sxs-lookup"><span data-stu-id="74064-344">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="74064-345">O `Include` atributo especifica o nome do arquivo e os `HintPath` metadados especificam o caminho para o assembly.</span><span class="sxs-lookup"><span data-stu-id="74064-345">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="74064-346">Propriedades relacionadas a restauração</span><span class="sxs-lookup"><span data-stu-id="74064-346">Restore-related properties</span></span>

<span data-ttu-id="74064-347">A restauração de um pacote referenciado instala todas as suas dependências diretas e todas as dependências dessas dependências.</span><span class="sxs-lookup"><span data-stu-id="74064-347">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="74064-348">Você pode personalizar a restauração do pacote especificando propriedades como `RestorePackagesPath` e `RestoreIgnoreFailedSources` .</span><span class="sxs-lookup"><span data-stu-id="74064-348">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="74064-349">Para obter mais informações sobre essas e outras propriedades, consulte [Restore Target](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="74064-349">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="74064-350">Propriedades da execução</span><span class="sxs-lookup"><span data-stu-id="74064-350">Run properties</span></span>

<span data-ttu-id="74064-351">As propriedades a seguir são usadas para iniciar um aplicativo com o [`dotnet run`](../tools/dotnet-run.md) comando:</span><span class="sxs-lookup"><span data-stu-id="74064-351">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="74064-352">RunArguments</span><span class="sxs-lookup"><span data-stu-id="74064-352">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="74064-353">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="74064-353">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="74064-354">RunArguments</span><span class="sxs-lookup"><span data-stu-id="74064-354">RunArguments</span></span>

<span data-ttu-id="74064-355">A `RunArguments` propriedade define os argumentos que são passados para o aplicativo quando ele é executado.</span><span class="sxs-lookup"><span data-stu-id="74064-355">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="74064-356">Você pode especificar argumentos adicionais a serem passados para o aplicativo usando a [ `--` opção para `dotnet run` ](../tools/dotnet-run.md#options).</span><span class="sxs-lookup"><span data-stu-id="74064-356">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="74064-357">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="74064-357">RunWorkingDirectory</span></span>

<span data-ttu-id="74064-358">A `RunWorkingDirectory` propriedade define o diretório de trabalho no qual o processo do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="74064-358">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="74064-359">Pode ser um caminho absoluto ou um caminho relativo ao diretório do projeto.</span><span class="sxs-lookup"><span data-stu-id="74064-359">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="74064-360">Se você não especificar um diretório, `OutDir` será usado como o diretório de trabalho.</span><span class="sxs-lookup"><span data-stu-id="74064-360">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="74064-361">Propriedades de hospedagem</span><span class="sxs-lookup"><span data-stu-id="74064-361">Hosting properties</span></span>

- [<span data-ttu-id="74064-362">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="74064-362">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="74064-363">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="74064-363">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="74064-364">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="74064-364">EnableComHosting</span></span>

<span data-ttu-id="74064-365">A `EnableComHosting` propriedade indica que um assembly fornece um servidor com.</span><span class="sxs-lookup"><span data-stu-id="74064-365">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="74064-366">Definir o `EnableComHosting` como `true` também implica que [EnableDynamicLoading](#enabledynamicloading) é `true` .</span><span class="sxs-lookup"><span data-stu-id="74064-366">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="74064-367">Para obter mais informações, consulte [expor componentes .net ao com](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="74064-367">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="74064-368">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="74064-368">EnableDynamicLoading</span></span>

<span data-ttu-id="74064-369">A `EnableDynamicLoading` propriedade indica que um assembly é um componente carregado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="74064-369">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="74064-370">O componente pode ser uma [biblioteca com](/windows/win32/com/the-component-object-model) ou uma biblioteca não com que pode ser [usada em um host nativo](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="74064-370">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="74064-371">Definir essa propriedade como `true` tem os seguintes efeitos:</span><span class="sxs-lookup"><span data-stu-id="74064-371">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="74064-372">Um *.runtimeconfig.jsno* arquivo é gerado.</span><span class="sxs-lookup"><span data-stu-id="74064-372">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="74064-373">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) é definido como `LatestMinor` .</span><span class="sxs-lookup"><span data-stu-id="74064-373">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="74064-374">As referências do NuGet são copiadas localmente.</span><span class="sxs-lookup"><span data-stu-id="74064-374">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="74064-375">Veja também</span><span class="sxs-lookup"><span data-stu-id="74064-375">See also</span></span>

- [<span data-ttu-id="74064-376">Referência de esquema do MSBuild</span><span class="sxs-lookup"><span data-stu-id="74064-376">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="74064-377">Propriedades comuns do MSBuild</span><span class="sxs-lookup"><span data-stu-id="74064-377">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="74064-378">Propriedades do MSBuild para o pacote NuGet</span><span class="sxs-lookup"><span data-stu-id="74064-378">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="74064-379">Propriedades do MSBuild para restauração do NuGet</span><span class="sxs-lookup"><span data-stu-id="74064-379">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="74064-380">Personalizar uma compilação</span><span class="sxs-lookup"><span data-stu-id="74064-380">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
