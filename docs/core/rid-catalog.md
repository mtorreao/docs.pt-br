---
title: Catálogo de RID (identificador de tempo de execução) do .NET Core
description: Saiba mais sobre o RID (identificador de tempo de execução) e como os RIDs são usados no .NET Core.
ms.date: 12/15/2020
ms.openlocfilehash: f818ab2d503be7960d9eb8450a7dd749766637a6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633605"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="4ede5-103">Catálogo de RIDs do .NET Core</span><span class="sxs-lookup"><span data-stu-id="4ede5-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="4ede5-104">RID é curto para o *identificador de tempo de execução*.</span><span class="sxs-lookup"><span data-stu-id="4ede5-104">RID is short for *Runtime Identifier*.</span></span> <span data-ttu-id="4ede5-105">Os valores do RID são usados para identificar plataformas de destino onde o aplicativo é executado.</span><span class="sxs-lookup"><span data-stu-id="4ede5-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="4ede5-106">Eles são usados por pacotes .NET para representar ativos específicos de plataforma em pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="4ede5-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="4ede5-107">Os seguintes valores são exemplos de RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` ou `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="4ede5-108">Para os pacotes com dependências nativas, o RID designará as plataformas em que o pacote pode ser restaurado.</span><span class="sxs-lookup"><span data-stu-id="4ede5-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="4ede5-109">Um único RID pode ser definido no elemento `<RuntimeIdentifier>` do arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="4ede5-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="4ede5-110">Vários RIDs podem ser definidos como uma lista separada por ponto-e-vírgula no elemento `<RuntimeIdentifiers>` do arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="4ede5-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="4ede5-111">Eles também são usados por meio da opção `--runtime` com os seguintes [comandos da CLI do .NET Core](./tools/index.md):</span><span class="sxs-lookup"><span data-stu-id="4ede5-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="4ede5-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="4ede5-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="4ede5-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="4ede5-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="4ede5-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="4ede5-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="4ede5-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="4ede5-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="4ede5-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="4ede5-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="4ede5-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="4ede5-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="4ede5-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="4ede5-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="4ede5-119">RIDs que representem sistemas operacionais concretos geralmente seguem este padrão: `[os].[version]-[architecture]-[additional qualifiers]` em que:</span><span class="sxs-lookup"><span data-stu-id="4ede5-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="4ede5-120">`[os]` é o moniker do sistema operacional/plataforma.</span><span class="sxs-lookup"><span data-stu-id="4ede5-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="4ede5-121">Por exemplo, `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="4ede5-122">`[version]` é a versão do sistema operacional na forma de um separado de versão separado por ponto (`.`).</span><span class="sxs-lookup"><span data-stu-id="4ede5-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="4ede5-123">Por exemplo, `15.10`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="4ede5-124">A versão **não deve** ser uma versão de marketing, pois essas geralmente representam várias versões distintas do sistema operacional com diferentes áreas de superfície de API da plataforma.</span><span class="sxs-lookup"><span data-stu-id="4ede5-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="4ede5-125">`[architecture]` é a arquitetura do processador.</span><span class="sxs-lookup"><span data-stu-id="4ede5-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="4ede5-126">Por exemplo: `x86`, `x64`, `arm` ou `arm64`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="4ede5-127">`[additional qualifiers]` distingue diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="4ede5-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="4ede5-128">Por exemplo: `aot`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="4ede5-129">Gráfico RID</span><span class="sxs-lookup"><span data-stu-id="4ede5-129">RID graph</span></span>

<span data-ttu-id="4ede5-130">O gráfico RID ou gráfico de fallback de runtime é uma lista de RIDs que são compatíveis entre si.</span><span class="sxs-lookup"><span data-stu-id="4ede5-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="4ede5-131">Os RIDs são definidos no pacote [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="4ede5-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="4ede5-132">Você pode ver a lista de RIDs com suporte e o grafo RID na [*runtime.jsno*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) arquivo, que está localizado no `dotnet/runtime` repositório.</span><span class="sxs-lookup"><span data-stu-id="4ede5-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the `dotnet/runtime` repository.</span></span> <span data-ttu-id="4ede5-133">Nesse arquivo, você pode ver todos os RIDs, exceto para a base um, que contém uma instrução `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="4ede5-134">Essas instruções indicam RIDs compatíveis.</span><span class="sxs-lookup"><span data-stu-id="4ede5-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="4ede5-135">Quando o NuGet restaura pacotes, ele tenta encontrar uma correspondência exata para o runtime especificado.</span><span class="sxs-lookup"><span data-stu-id="4ede5-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="4ede5-136">Se uma correspondência exata não for encontrada, o NuGet voltará ao gráfico até encontrar o sistema compatível mais próximo de acordo com o gráfico RID.</span><span class="sxs-lookup"><span data-stu-id="4ede5-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="4ede5-137">O exemplo a seguir é a entrada real para o RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="4ede5-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="4ede5-138">O RID acima especifica que `osx.10.12-x64` importa `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="4ede5-139">Desse modo, quando o NuGet restaura pacotes, ele tenta encontrar uma correspondência exata para `osx.10.12-x64` no pacote.</span><span class="sxs-lookup"><span data-stu-id="4ede5-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="4ede5-140">Se o NuGet não puder encontrar o runtime específico, ele poderá restaurar pacotes que especificam runtimes `osx.10.11-x64`, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="4ede5-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="4ede5-141">O seguinte exemplo mostra um gráfico RID ligeiramente maior, também definido no arquivo *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="4ede5-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="4ede5-142">Todos os RIDs eventualmente mapeiam para a raiz de `any` RID.</span><span class="sxs-lookup"><span data-stu-id="4ede5-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="4ede5-143">Há algumas considerações sobre RIDs das quais você precisa se lembrar ao trabalhar com eles:</span><span class="sxs-lookup"><span data-stu-id="4ede5-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="4ede5-144">Não tente analisar RIDs para recuperar partes do componente.</span><span class="sxs-lookup"><span data-stu-id="4ede5-144">Don't try to parse RIDs to retrieve component parts.</span></span>
- <span data-ttu-id="4ede5-145">Não crie RIDs de modo programático.</span><span class="sxs-lookup"><span data-stu-id="4ede5-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="4ede5-146">Use RIDs que já estão definidos para a plataforma.</span><span class="sxs-lookup"><span data-stu-id="4ede5-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="4ede5-147">Os RIDs precisam ser específicos, portanto, não presuma nada usando o valor RID real.</span><span class="sxs-lookup"><span data-stu-id="4ede5-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="4ede5-148">Usando RIDs</span><span class="sxs-lookup"><span data-stu-id="4ede5-148">Using RIDs</span></span>

<span data-ttu-id="4ede5-149">Para poder usar RIDs, você precisa saber quais RIDs existem.</span><span class="sxs-lookup"><span data-stu-id="4ede5-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="4ede5-150">Novos RIDs são adicionados regularmente à plataforma.</span><span class="sxs-lookup"><span data-stu-id="4ede5-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="4ede5-151">Para obter a versão mais recente e completa, consulte o [runtime.jsem](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) arquivo no `dotnet/runtime` repositório.</span><span class="sxs-lookup"><span data-stu-id="4ede5-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

<span data-ttu-id="4ede5-152">O SDK do .NET Core 2.0 apresenta o conceito de RIDs portáteis.</span><span class="sxs-lookup"><span data-stu-id="4ede5-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="4ede5-153">Eles são novos valores adicionados ao gráfico RID que não estão associados a uma versão específica ou distribuição de SO e são a opção preferida ao usar o .NET Core 2.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="4ede5-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="4ede5-154">Eles são particularmente úteis ao lidar com várias distribuições Linux, já que a maioria dos RIDs de distribuição são mapeados para os RIDs portáteis.</span><span class="sxs-lookup"><span data-stu-id="4ede5-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="4ede5-155">A lista a seguir mostra um pequeno subconjunto dos RIDs mais comuns usados para cada SO.</span><span class="sxs-lookup"><span data-stu-id="4ede5-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="4ede5-156">RIDs do Windows</span><span class="sxs-lookup"><span data-stu-id="4ede5-156">Windows RIDs</span></span>

<span data-ttu-id="4ede5-157">Apenas os valores comuns são listados.</span><span class="sxs-lookup"><span data-stu-id="4ede5-157">Only common values are listed.</span></span> <span data-ttu-id="4ede5-158">Para obter a versão mais recente e completa, consulte o [runtime.jsem](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) arquivo no `dotnet/runtime` repositório.</span><span class="sxs-lookup"><span data-stu-id="4ede5-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="4ede5-159">Portátil (.NET Core 2.0 ou versões posteriores)</span><span class="sxs-lookup"><span data-stu-id="4ede5-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="4ede5-160">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4ede5-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="4ede5-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4ede5-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="4ede5-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4ede5-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="4ede5-163">Para obter mais informações, consulte [dependências e requisitos do .NET Core](./install/windows.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="4ede5-163">For more information, see [.NET Core dependencies and requirements](./install/windows.md#dependencies).</span></span>

## <a name="linux-rids"></a><span data-ttu-id="4ede5-164">RIDs do Linux</span><span class="sxs-lookup"><span data-stu-id="4ede5-164">Linux RIDs</span></span>

<span data-ttu-id="4ede5-165">Apenas os valores comuns são listados.</span><span class="sxs-lookup"><span data-stu-id="4ede5-165">Only common values are listed.</span></span> <span data-ttu-id="4ede5-166">Para obter a versão mais recente e completa, consulte o [runtime.jsem](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) arquivo no `dotnet/runtime` repositório.</span><span class="sxs-lookup"><span data-stu-id="4ede5-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span> <span data-ttu-id="4ede5-167">Os dispositivos que executam uma distribuição não listada abaixo podem funcionar com um dos RIDs Portáteis.</span><span class="sxs-lookup"><span data-stu-id="4ede5-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="4ede5-168">Por exemplo, os dispositivos Raspberry Pi executando uma distribuição Linux não listada podem ser direcionados com `linux-arm`.</span><span class="sxs-lookup"><span data-stu-id="4ede5-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="4ede5-169">Portáteis</span><span class="sxs-lookup"><span data-stu-id="4ede5-169">Portable</span></span>
  - <span data-ttu-id="4ede5-170">`linux-x64` (A maioria das distribuições de área de trabalho como CentOS, Debian, Fedora, Ubuntu e derivativos)</span><span class="sxs-lookup"><span data-stu-id="4ede5-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu, and derivatives)</span></span>
  - <span data-ttu-id="4ede5-171">`linux-musl-x64` (Distribuições leves usando [musl](https://wiki.musl-libc.org/projects-using-musl.html), como o Alpine Linux)</span><span class="sxs-lookup"><span data-stu-id="4ede5-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="4ede5-172">`linux-arm` (Distribuições do Linux em execução no ARM, como Raspbian no Raspberry Pi Model 2 +)</span><span class="sxs-lookup"><span data-stu-id="4ede5-172">`linux-arm` (Linux distributions running on ARM like Raspbian on Raspberry Pi Model 2+)</span></span>
  - <span data-ttu-id="4ede5-173">`linux-arm64` (Distribuições do Linux em execução no ARM de 64 bits, como o Ubuntu Server 64-bit no modelo Raspberry Pi 3 +)</span><span class="sxs-lookup"><span data-stu-id="4ede5-173">`linux-arm64` (Linux distributions running on 64-bit ARM like Ubuntu Server 64-bit on Raspberry Pi Model 3+)</span></span>
- <span data-ttu-id="4ede5-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="4ede5-174">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="4ede5-175">`rhel-x64` (Substituído por `linux-x64` para RHEL acima da versão 6)</span><span class="sxs-lookup"><span data-stu-id="4ede5-175">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - `rhel.6-x64`
- <span data-ttu-id="4ede5-176">Tizen</span><span class="sxs-lookup"><span data-stu-id="4ede5-176">Tizen</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="4ede5-177">Para obter mais informações, consulte [dependências e requisitos do .NET Core](./install/linux.md).</span><span class="sxs-lookup"><span data-stu-id="4ede5-177">For more information, see [.NET Core dependencies and requirements](./install/linux.md).</span></span>

## <a name="macos-rids"></a><span data-ttu-id="4ede5-178">RIDs do macOS</span><span class="sxs-lookup"><span data-stu-id="4ede5-178">macOS RIDs</span></span>

<span data-ttu-id="4ede5-179">Os RIDs do macOS usam a identidade visual “OSX” mais antiga.</span><span class="sxs-lookup"><span data-stu-id="4ede5-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="4ede5-180">Apenas os valores comuns são listados.</span><span class="sxs-lookup"><span data-stu-id="4ede5-180">Only common values are listed.</span></span> <span data-ttu-id="4ede5-181">Para obter a versão mais recente e completa, consulte o [runtime.jsem](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) arquivo no `dotnet/runtime` repositório.</span><span class="sxs-lookup"><span data-stu-id="4ede5-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="4ede5-182">Portáteis</span><span class="sxs-lookup"><span data-stu-id="4ede5-182">Portable</span></span>
  - <span data-ttu-id="4ede5-183">`osx-x64` (A versão mínima do sistema operacional é macOS 10.12 Sierra)</span><span class="sxs-lookup"><span data-stu-id="4ede5-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="4ede5-184">macOS 10.10 Yosemite</span><span class="sxs-lookup"><span data-stu-id="4ede5-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="4ede5-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="4ede5-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="4ede5-186">macOS 10.12 Sierra</span><span class="sxs-lookup"><span data-stu-id="4ede5-186">macOS 10.12 Sierra</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="4ede5-187">macOS 10.13 High Sierra</span><span class="sxs-lookup"><span data-stu-id="4ede5-187">macOS 10.13 High Sierra</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="4ede5-188">macOS 10.14 Mojave</span><span class="sxs-lookup"><span data-stu-id="4ede5-188">macOS 10.14 Mojave</span></span>
  - `osx.10.14-x64`
- <span data-ttu-id="4ede5-189">macOS 10.15 Catalina</span><span class="sxs-lookup"><span data-stu-id="4ede5-189">macOS 10.15 Catalina</span></span>
  - `osx.10.15-x64`
- <span data-ttu-id="4ede5-190">macOS 11, 1 Big Sur</span><span class="sxs-lookup"><span data-stu-id="4ede5-190">macOS 11.01 Big Sur</span></span>
  - `osx.11.0-x64`
  - `osx.11.0-arm64`

<span data-ttu-id="4ede5-191">Para obter mais informações, consulte [dependências e requisitos do .NET Core](./install/macos.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="4ede5-191">For more information, see [.NET Core dependencies and requirements](./install/macos.md#dependencies).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ede5-192">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ede5-192">See also</span></span>

- [<span data-ttu-id="4ede5-193">IDs de Runtime</span><span class="sxs-lookup"><span data-stu-id="4ede5-193">Runtime IDs</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
