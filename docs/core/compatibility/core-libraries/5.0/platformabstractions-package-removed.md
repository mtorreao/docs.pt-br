---
title: 'Alteração significativa: pacote Microsoft. DotNet. PlatformAbstractions removido'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que o pacote Microsoft. DotNet. PlatformAbstractions foi removido.
ms.date: 11/01/2020
ms.openlocfilehash: 38ffe5e592d01c3bae14fc41becb594283b975a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760400"
---
# <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="ce3d9-103">Pacote Microsoft. DotNet. PlatformAbstractions removido</span><span class="sxs-lookup"><span data-stu-id="ce3d9-103">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="ce3d9-104">Nenhuma nova versão do [pacote NuGet Microsoft. dotnet. PlatformAbstractions](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) será produzida.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-104">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

## <a name="change-description"></a><span data-ttu-id="ce3d9-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="ce3d9-105">Change description</span></span>

<span data-ttu-id="ce3d9-106">Anteriormente, novas versões da <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> biblioteca foram produzidas junto com as novas versões do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-106">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="ce3d9-107">No futuro, nenhuma nova funcionalidade será adicionada à biblioteca e nenhuma nova versão principal será lançada.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-107">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="ce3d9-108">No entanto, as versões existentes da biblioteca continuarão funcionando e serão atendidas.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-108">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="ce3d9-109">A <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> biblioteca se sobrepõe a APIs que já estão estabelecidas em System. \* namespaces.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-109">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="ce3d9-110">Além disso, algumas <xref:Microsoft.DotNet.PlatformAbstractions> APIs não foram projetadas com o mesmo nível de análise e suporte a longo prazo como o restante do sistema. \* API.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-110">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="ce3d9-111">Por exemplo, <xref:Microsoft.DotNet.PlatformAbstractions> o usa a `Platform` enumeração para descrever a plataforma atual do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-111">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="ce3d9-112">Esse design de enumeração foi explicitamente rejeitado quando a <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API foi projetada para permitir novas plataformas e futura flexibilidade.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-112">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="ce3d9-113">Os cenários habilitados pela <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> biblioteca agora são possíveis sem ele.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-113">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="ce3d9-114">As versões existentes continuarão funcionando, mesmo no .NET 5,0 e posterior, e serão atendidas junto com as versões anteriores do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-114">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="ce3d9-115">No entanto, a nova funcionalidade não será adicionada à biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-115">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="ce3d9-116">Em vez disso, novas funcionalidades serão adicionadas a outras bibliotecas e APIs.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-116">Instead, new functionality will be added to other libraries and APIs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ce3d9-117">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ce3d9-117">Version introduced</span></span>

<span data-ttu-id="ce3d9-118">5.0</span><span class="sxs-lookup"><span data-stu-id="ce3d9-118">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ce3d9-119">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ce3d9-119">Recommended action</span></span>

- <span data-ttu-id="ce3d9-120">Você pode continuar a usar versões mais antigas da biblioteca se elas atenderem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-120">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="ce3d9-121">Se as versões mais antigas não atenderem às suas necessidades, substitua os usos das `PlatformAbstractions` APIs pelas substituições recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-121">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="ce3d9-122">`PlatformAbstractions` API</span><span class="sxs-lookup"><span data-stu-id="ce3d9-122">`PlatformAbstractions` API</span></span> | <span data-ttu-id="ce3d9-123">Substituição recomendada</span><span class="sxs-lookup"><span data-stu-id="ce3d9-123">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="ce3d9-124"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> e <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ce3d9-124"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="ce3d9-125">A maioria dos casos de uso para `RuntimeEnvironment.OperatingSystem` `RuntimeEnvironment.OperatingSystemVersion` o e o são para fins de exibição, por exemplo, exibindo para um usuário, registro em log e telemetria.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-125">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="ce3d9-126">Não é recomendável tomar decisões de tempo de execução com base em uma versão do sistema operacional (SO).</span><span class="sxs-lookup"><span data-stu-id="ce3d9-126">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="ce3d9-127"><xref:System.Environment.OSVersion?displayProperty=nameWithType> Agora [retorna a versão correta para os](environment-osversion-returns-correct-version.md) sistemas operacionais Windows e MacOS.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-127"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now [returns the correct version](environment-osversion-returns-correct-version.md) for Windows and macOS operating systems.</span></span> <span data-ttu-id="ce3d9-128">No entanto, para a maioria das distribuições do UNIX, o que é considerado como "versão do sistema operacional" não é tão simples.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-128">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="ce3d9-129">Por exemplo, pode ser a versão do kernel do Linux ou pode ser a versão distribuição.</span><span class="sxs-lookup"><span data-stu-id="ce3d9-129">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="ce3d9-130">Para a maioria das plataformas UNIX, <xref:System.Environment.OSVersion?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> retorne a versão retornada pelo `uname` .</span><span class="sxs-lookup"><span data-stu-id="ce3d9-130">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="ce3d9-131">Para obter as informações de nome e versão do distribuição do Linux, a abordagem recomendada é ler o arquivo */etc/os-Release* .</span><span class="sxs-lookup"><span data-stu-id="ce3d9-131">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ce3d9-132">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ce3d9-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
