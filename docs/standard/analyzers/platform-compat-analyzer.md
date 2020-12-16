---
title: Analisador de compatibilidade de plataforma
description: Um analisador de Roslyn que pode ajudar a detectar problemas de compatibilidade de plataforma em aplicativos e bibliotecas de plataforma cruzada.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 427a2d8ae61a82699e5cf0987fcd1c5a45152cac
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97594911"
---
# <a name="platform-compatibility-analyzer"></a><span data-ttu-id="5a37c-103">Analisador de compatibilidade de plataforma</span><span class="sxs-lookup"><span data-stu-id="5a37c-103">Platform compatibility analyzer</span></span>

<span data-ttu-id="5a37c-104">Você provavelmente já ouviu o lema de "um .NET": uma única plataforma unificada para criar qualquer tipo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5a37c-104">You've probably heard the motto of "One .NET": a single, unified platform for building any type of application.</span></span> <span data-ttu-id="5a37c-105">O SDK do .NET 5,0 inclui ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin e ML.NET, e adicionará suporte para mais plataformas ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="5a37c-105">The .NET 5.0 SDK includes ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin, and ML.NET, and will add support for more platforms over time.</span></span> <span data-ttu-id="5a37c-106">O .NET 5,0 se esforça para fornecer uma experiência em que você não tem de ponderar sobre os diferentes tipos de .NET, mas não tenta abstrair completamente o sistema operacional subjacente (SO).</span><span class="sxs-lookup"><span data-stu-id="5a37c-106">.NET 5.0 strives to provide an experience where you don't have to reason about the different flavors of .NET, but doesn't attempt to fully abstract away the underlying operating system (OS).</span></span> <span data-ttu-id="5a37c-107">Você continuará a ser capaz de chamar APIs específicas da plataforma, por exemplo, P/Invokes, WinRT ou as associações do Xamarin para iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="5a37c-107">You'll continue to be able to call platform-specific APIs, for example, P/Invokes, WinRT, or the Xamarin bindings for iOS and Android.</span></span>

<span data-ttu-id="5a37c-108">Mas usar APIs específicas da plataforma em um componente significa que o código não funciona mais em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-108">But using platform-specific APIs on a component means the code no longer works across all platforms.</span></span> <span data-ttu-id="5a37c-109">Precisávamos de uma maneira de detectar isso em tempo de design para que os desenvolvedores obtenham diagnósticos quando inadvertidamente usam APIs específicas da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-109">We needed a way to detect this at design time so developers get diagnostics when they inadvertently use platform-specific APIs.</span></span> <span data-ttu-id="5a37c-110">Para atingir esse objetivo, o .NET 5,0 apresenta o [analisador de compatibilidade de plataforma](../../fundamentals/code-analysis/quality-rules/ca1416.md) e APIs complementares para ajudar os desenvolvedores a identificar e usar APIs específicas da plataforma, quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="5a37c-110">To achieve this goal, .NET 5.0 introduces the [platform compatibility analyzer](../../fundamentals/code-analysis/quality-rules/ca1416.md) and complementary APIs to help developers identify and use platform-specific APIs where appropriate.</span></span>

<span data-ttu-id="5a37c-111">As novas APIs incluem:</span><span class="sxs-lookup"><span data-stu-id="5a37c-111">The new APIs include:</span></span>

- <span data-ttu-id="5a37c-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> anotar APIs como sendo específicas da plataforma e <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> anotar APIs como sem suporte em um sistema operacional específico.</span><span class="sxs-lookup"><span data-stu-id="5a37c-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> to annotate APIs as being platform-specific and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> to annotate APIs as being unsupported on a particular OS.</span></span> <span data-ttu-id="5a37c-113">Esses atributos podem, opcionalmente, incluir o número de versão e já foram aplicados a algumas APIs específicas da plataforma nas principais bibliotecas do .NET.</span><span class="sxs-lookup"><span data-stu-id="5a37c-113">These attributes can optionally include the version number, and have already been applied to some platform-specific APIs in the core .NET libraries.</span></span>
- <span data-ttu-id="5a37c-114">`Is<Platform>()` e `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` métodos estáticos na <xref:System.OperatingSystem?displayProperty=nameWithType> classe para chamar com segurança APIs específicas da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-114">`Is<Platform>()` and `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` static methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class for safely calling platform-specific APIs.</span></span> <span data-ttu-id="5a37c-115">Por exemplo, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> pode ser usado para proteger uma chamada para uma API específica do Windows e <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType> () pode ser usado para proteger uma chamada de API específica do Windows com versão.</span><span class="sxs-lookup"><span data-stu-id="5a37c-115">For example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> can be used to guard a call to a Windows-specific API, and <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() can be used to guard a versioned Windows-specific API call.</span></span> <span data-ttu-id="5a37c-116">Veja esses [exemplos](#guard-platform-specific-apis-with-guard-methods) de como esses métodos podem ser usados como proteções de referências de API específicas da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-116">See these [examples](#guard-platform-specific-apis-with-guard-methods) of how these methods can be used as guards of platform-specific API references.</span></span>

> [!TIP]
> <span data-ttu-id="5a37c-117">O analisador de compatibilidade de plataforma atualiza e substitui o recurso de [detecção de problemas entre plataformas](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) do [analisador de API .net](../../standard/analyzers/api-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="5a37c-117">The platform compatibility analyzer upgrades and replaces the [Discovering cross-platform issues](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) feature of the [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a37c-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5a37c-118">Prerequisites</span></span>

<span data-ttu-id="5a37c-119">O analisador de compatibilidade de plataforma é um dos analisadores de qualidade de código Roslyn.</span><span class="sxs-lookup"><span data-stu-id="5a37c-119">The platform compatibility analyzer is one of the Roslyn code quality analyzers.</span></span> <span data-ttu-id="5a37c-120">Do .NET 5.0 em diante, esses analisadores estão [incluídos no SDK do .NET](../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="5a37c-120">Starting in .NET 5.0, these analyzers are [included with the .NET SDK](../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="5a37c-121">O analisador de compatibilidade de plataforma é habilitado por padrão somente para projetos direcionados `net5.0` ou para uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="5a37c-121">The platform compatibility analyzer is enabled by default only for projects that target `net5.0` or a later version.</span></span> <span data-ttu-id="5a37c-122">No entanto, você pode [habilitá-lo](../../fundamentals/code-analysis/quality-rules/ca1416.md#configure-code-to-analyze) para projetos direcionados a outras estruturas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-122">However, you can [enable it](../../fundamentals/code-analysis/quality-rules/ca1416.md#configure-code-to-analyze) for projects that target other frameworks.</span></span>

## <a name="how-the-analyzer-determines-platform-dependency"></a><span data-ttu-id="5a37c-123">Como o analisador determina a dependência da plataforma</span><span class="sxs-lookup"><span data-stu-id="5a37c-123">How the analyzer determines platform dependency</span></span>

- <span data-ttu-id="5a37c-124">Uma **API** não-atributo é considerada para funcionar em **todas as plataformas de sistema operacional**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-124">An **unattributed API** is considered to work on **all OS platforms**.</span></span>
- <span data-ttu-id="5a37c-125">Uma API marcada com `[SupportedOSPlatform("platform")]` é considerada apenas portátil para o sistema operacional especificado `platform` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-125">An API marked with `[SupportedOSPlatform("platform")]` is considered only portable to the specified OS `platform`.</span></span>
  - <span data-ttu-id="5a37c-126">O atributo pode ser aplicado várias vezes para indicar **suporte a várias plataformas** ( `[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-126">The attribute can be applied multiple times to indicate **multiple platform support** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span></span>
  - <span data-ttu-id="5a37c-127">O analisador produzirá um **aviso** se as APIs específicas da plataforma forem referenciadas sem um **contexto de plataforma** adequado:</span><span class="sxs-lookup"><span data-stu-id="5a37c-127">The analyzer will produce a **warning** if platform-specific APIs are referenced without a proper **platform context**:</span></span>
    - <span data-ttu-id="5a37c-128">**Avisa** se o projeto não visa a plataforma com suporte (por exemplo, uma chamada à API específica do Windows e os destinos do projeto `<TargetFramework>net5.0-ios14.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-128">**Warns** if the project doesn't target the supported platform (for example, a Windows-specific API call and the project targets `<TargetFramework>net5.0-ios14.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="5a37c-129">**Avisa** se o projeto tem vários destinos ( `<TargetFramework>net5.0</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-129">**Warns** if the project is multi-targeted (`<TargetFramework>net5.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="5a37c-130">**Não avisa** se a API específica da plataforma é referenciada em um projeto que se destina a qualquer uma das **plataformas especificadas** (por exemplo, para uma chamada de API específica do Windows e os destinos do projeto `<TargetFramework>net5.0-windows</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-130">**Doesn't warn** if the platform-specific API is referenced within a project that targets any of the **specified platforms** (for example, for a Windows-specific API call and the project targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="5a37c-131">**Não avisará** se a chamada à API específica da plataforma for protegida por métodos de verificação de plataforma correspondentes (por exemplo, `if(OperatingSystem.IsWindows())` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-131">**Doesn't warn** if the platform-specific API call is guarded by corresponding platform-check methods (for example, `if(OperatingSystem.IsWindows())`).</span></span>
    - <span data-ttu-id="5a37c-132">**Não avisa** se a API específica da plataforma é referenciada do mesmo contexto específico da plataforma (o **site de chamada também é atribuído** com `[SupportedOSPlatform("platform")` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-132">**Doesn't warn** if the platform-specific API is referenced from the same platform-specific context (**call site also attributed** with `[SupportedOSPlatform("platform")`).</span></span>
- <span data-ttu-id="5a37c-133">Uma API marcada com `[UnsupportedOSPlatform("platform")]` é considerada não suportada apenas no sistema operacional especificado `platform` , mas com suporte para todas as outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-133">An API marked with `[UnsupportedOSPlatform("platform")]` is considered unsupported only on the specified OS `platform` but supported for all other platforms.</span></span>
  - <span data-ttu-id="5a37c-134">O atributo pode ser aplicado várias vezes com diferentes plataformas, por exemplo, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-134">The attribute can be applied multiple times with different platforms, for example, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span></span>
  - <span data-ttu-id="5a37c-135">O analisador produzirá um **aviso** somente se o `platform` estiver em vigor para o site de chamada:</span><span class="sxs-lookup"><span data-stu-id="5a37c-135">The analyzer produces a **warning** only if the `platform` is effective for the call site:</span></span>
    - <span data-ttu-id="5a37c-136">**Avisa** se o projeto se destina à plataforma que é atribuída como sem suporte (por exemplo, se a API for atribuída com `[UnsupportedOSPlatform("windows")]` e os destinos do site de chamada `<TargetFramework>net5.0-windows</TargetFramework>` ).</span><span class="sxs-lookup"><span data-stu-id="5a37c-136">**Warns** if the project targets the platform that's attributed as unsupported (for example, if the API is attributed with `[UnsupportedOSPlatform("windows")]` and the call site targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="5a37c-137">**Avisa** se o projeto tem vários destinos e se `platform` está incluído no grupo de itens padrão [do `<SupportedPlatform>` MSBuild](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) ou `platform` se está incluído manualmente dentro do grupo de `MSBuild` \<SupportedPlatform> itens:</span><span class="sxs-lookup"><span data-stu-id="5a37c-137">**Warns** if the project is multi-targeted and the `platform` is included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group, or the `platform` is manually included within the `MSBuild` \<SupportedPlatform> items group:</span></span>

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - <span data-ttu-id="5a37c-138">**Não avisará** se você estiver criando um aplicativo que não tem como alvo a plataforma sem suporte ou que tem vários destinos e a plataforma não está incluída no grupo de itens padrão do [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) .</span><span class="sxs-lookup"><span data-stu-id="5a37c-138">**Doesn't warn** if you're building an app that doesn't target the unsupported platform or is multi-targeted and the platform is not included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group.</span></span>
- <span data-ttu-id="5a37c-139">Ambos os atributos podem ser instanciados com ou sem números de versão como parte do nome da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-139">Both attributes can be instantiated with or without version numbers as part of the platform name.</span></span>
  - <span data-ttu-id="5a37c-140">Os números de versão estão no formato de `major.minor[.build[.revision]]` ; `major.minor` é necessário e `build` as `revision` partes e são opcionais.</span><span class="sxs-lookup"><span data-stu-id="5a37c-140">Version numbers are in the format of `major.minor[.build[.revision]]`; `major.minor` is required and the `build` and `revision` parts are optional.</span></span> <span data-ttu-id="5a37c-141">Por exemplo, "Windows 7.0" indica a versão 7,0 do Windows, mas "Windows" é interpretado como Windows 0,0.</span><span class="sxs-lookup"><span data-stu-id="5a37c-141">For example, "Windows7.0" indicates Windows version 7.0, but "Windows" is interpreted as Windows 0.0.</span></span>

<span data-ttu-id="5a37c-142">Para obter mais informações, consulte [exemplos de como os atributos funcionam e quais diagnósticos eles causam](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span><span class="sxs-lookup"><span data-stu-id="5a37c-142">For more information, see [examples of how the attributes work and what diagnostics they cause](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span></span>

### <a name="advanced-scenarios-for-combining-attributes"></a><span data-ttu-id="5a37c-143">Cenários avançados para combinar atributos</span><span class="sxs-lookup"><span data-stu-id="5a37c-143">Advanced scenarios for combining attributes</span></span>

- <span data-ttu-id="5a37c-144">Se uma combinação de `[SupportedOSPlatform]` `[UnsupportedOSPlatform]` atributos e estiver presente, todos os atributos serão agrupados pelo identificador de plataforma do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="5a37c-144">If a combination of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are present, all attributes are grouped by OS platform identifier:</span></span>
  - <span data-ttu-id="5a37c-145">**Lista somente com suporte**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-145">**Supported only list**.</span></span> <span data-ttu-id="5a37c-146">Se a versão mais baixa de cada plataforma do sistema operacional for um `[SupportedOSPlatform]` atributo, a API será considerada como somente tendo suporte nas plataformas listadas e sem suporte por todas as outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-146">If the lowest version for each OS platform is a `[SupportedOSPlatform]` attribute, the API is considered to only be supported by the listed platforms and unsupported by all other platforms.</span></span> <span data-ttu-id="5a37c-147">Os atributos opcionais `[UnsupportedOSPlatform]` para cada plataforma só podem ter uma versão mais alta da versão mínima com suporte, o que denota que a API é removida a partir da versão especificada.</span><span class="sxs-lookup"><span data-stu-id="5a37c-147">The optional `[UnsupportedOSPlatform]` attributes for each platform can only have higher version of the minimum supported version, which denotes that the API is removed starting from the specified version.</span></span>

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - <span data-ttu-id="5a37c-148">**Lista somente sem suporte**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-148">**Unsupported only list**.</span></span> <span data-ttu-id="5a37c-149">Se a versão mais baixa de cada plataforma do sistema operacional for um `[UnsupportedOSPlatform]` atributo, a API será considerada como sem suporte nas plataformas listadas e com suporte de todas as outras plataformas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-149">If the lowest version for each OS platform is an `[UnsupportedOSPlatform]` attribute, then the API is considered to only be unsupported by the listed platforms and supported by all other platforms.</span></span> <span data-ttu-id="5a37c-150">A lista pode ter `[SupportedOSPlatform]` um atributo com a mesma plataforma, mas uma versão superior, que indica que a API tem suporte a partir dessa versão.</span><span class="sxs-lookup"><span data-stu-id="5a37c-150">The list could have `[SupportedOSPlatform]` attribute with the same platform but a higher version, which denotes that the API is supported starting from that version.</span></span>

    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - <span data-ttu-id="5a37c-151">**Lista inconsistente**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-151">**Inconsistent list**.</span></span> <span data-ttu-id="5a37c-152">Se a versão mais baixa de algumas plataformas for `[SupportedOSPlatform]` `[UnsupportedOSPlatform]` para outras plataformas, será considerada inconsistente, o que não tem suporte para o analisador.</span><span class="sxs-lookup"><span data-stu-id="5a37c-152">If the lowest version for some platforms is `[SupportedOSPlatform]` while it is `[UnsupportedOSPlatform]` for other platforms, it's considered to be inconsistent, which is not supported for the analyzer.</span></span>
  - <span data-ttu-id="5a37c-153">Se as versões mais baixas `[SupportedOSPlatform]` dos `[UnsupportedOSPlatform]` atributos e forem iguais, o analisador considerará a plataforma como parte da **lista somente com suporte**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-153">If the lowest versions of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are equal, the analyzer considers the platform as part of the **Supported only list**.</span></span>
- <span data-ttu-id="5a37c-154">Atributos de plataforma podem ser aplicados a tipos, Membros (métodos, campos, propriedades e eventos) e assemblies com diferentes nomes de plataforma ou versões.</span><span class="sxs-lookup"><span data-stu-id="5a37c-154">Platform attributes can be applied to types, members (methods, fields, properties, and events) and assemblies with different platform names or versions.</span></span>
  - <span data-ttu-id="5a37c-155">Os atributos aplicados no nível superior `target` afetam todos os seus membros e tipos.</span><span class="sxs-lookup"><span data-stu-id="5a37c-155">Attributes applied at the top level `target` affect all of its members and types.</span></span>
  - <span data-ttu-id="5a37c-156">Os atributos de nível filho só se aplicam se eles aderem à regra "as anotações filhas podem restringir o suporte a plataformas, mas não podem ampliá-la".</span><span class="sxs-lookup"><span data-stu-id="5a37c-156">Child-level attributes only apply if they adhere to the rule "child annotations can narrow the platforms support, but they cannot widen it".</span></span>
    - <span data-ttu-id="5a37c-157">Quando o pai tem **suporte apenas para** a lista, os atributos de membro filho não podem adicionar um novo suporte de plataforma, pois isso estaria estendendo o suporte pai.</span><span class="sxs-lookup"><span data-stu-id="5a37c-157">When parent has **Supported only** list, then child member attributes cannot add a new platform support, as that would be extending parent support.</span></span> <span data-ttu-id="5a37c-158">O suporte para uma nova plataforma só pode ser adicionado ao próprio pai.</span><span class="sxs-lookup"><span data-stu-id="5a37c-158">Support for a new platform can only be added to the parent itself.</span></span> <span data-ttu-id="5a37c-159">Mas o filho pode ter o `Supported` atributo para a mesma plataforma com versões posteriores que reduz o suporte.</span><span class="sxs-lookup"><span data-stu-id="5a37c-159">But the child can have the `Supported` attribute for the same platform with later versions as that narrows the support.</span></span> <span data-ttu-id="5a37c-160">Além disso, o filho pode ter o `Unsupported` atributo com a mesma plataforma que também limita o suporte pai.</span><span class="sxs-lookup"><span data-stu-id="5a37c-160">Also, the child can have the `Unsupported` attribute with the same platform as that also narrows parent support.</span></span>
    - <span data-ttu-id="5a37c-161">Quando o pai tem uma lista **somente sem suporte** , os atributos de membro filho podem adicionar suporte para uma nova plataforma, pois isso limita o suporte pai.</span><span class="sxs-lookup"><span data-stu-id="5a37c-161">When parent has **Unsupported only** list, then child member attributes can add support for a new platform, as that narrows parent support.</span></span> <span data-ttu-id="5a37c-162">Mas ele não pode ter o `Supported` atributo para a mesma plataforma que o pai, pois isso estende o suporte pai.</span><span class="sxs-lookup"><span data-stu-id="5a37c-162">But it cannot have the `Supported` attribute for the same platform as the parent, because that extends parent support.</span></span> <span data-ttu-id="5a37c-163">O suporte para a mesma plataforma só pode ser adicionado ao pai em que o `Unsupported` atributo original foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="5a37c-163">Support for the same platform can only be added to the parent where the original `Unsupported` attribute was applied.</span></span>
  - <span data-ttu-id="5a37c-164">Se `[SupportedOSPlatform("platformVersion")]` for aplicado mais de uma vez para uma API com o mesmo `platform` nome, o analisador apenas considerará aquela com a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="5a37c-164">If `[SupportedOSPlatform("platformVersion")]` is applied more than once for an API with the same `platform` name, the analyzer only considers the one with the minimum version.</span></span>
  - <span data-ttu-id="5a37c-165">Se `[UnsupportedOSPlatform("platformVersion")]` for aplicado mais de duas vezes para uma API com o mesmo `platform` nome, o analisador apenas considerará as duas com as versões mais antigas.</span><span class="sxs-lookup"><span data-stu-id="5a37c-165">If `[UnsupportedOSPlatform("platformVersion")]` is applied more than twice for an API with the same `platform` name, the analyzer only considers the two with the earliest versions.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5a37c-166">Uma API que era suportada inicialmente, mas sem suporte (removida) em uma versão posterior não é esperada para ser suportada novamente em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="5a37c-166">An API that was supported initially but unsupported (removed) in a later version is not expected to get resupported in an even later version.</span></span>

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a><span data-ttu-id="5a37c-167">Exemplos de como os atributos funcionam e quais diagnósticos eles produzem</span><span class="sxs-lookup"><span data-stu-id="5a37c-167">Examples of how the attributes work and what diagnostics they produce</span></span>

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a><span data-ttu-id="5a37c-168">Manipular avisos relatados</span><span class="sxs-lookup"><span data-stu-id="5a37c-168">Handle reported warnings</span></span>

<span data-ttu-id="5a37c-169">A maneira recomendada de lidar com esses diagnósticos é certificar-se de que você só chame APIs específicas da plataforma ao executar em uma plataforma apropriada.</span><span class="sxs-lookup"><span data-stu-id="5a37c-169">The recommended way to deal with these diagnostics is to make sure you only call platform-specific APIs when running on an appropriate platform.</span></span> <span data-ttu-id="5a37c-170">A seguir estão as opções que você pode usar para resolver os avisos; Escolha o que for mais apropriado para sua situação:</span><span class="sxs-lookup"><span data-stu-id="5a37c-170">Following are the options you can use to address the warnings; choose whichever is most appropriate for your situation:</span></span>

- <span data-ttu-id="5a37c-171">**Proteja a chamada**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-171">**Guard the call**.</span></span> <span data-ttu-id="5a37c-172">Você pode conseguir isso chamando condicionalmente o código em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5a37c-172">You can achieve this by conditionally calling the code at run time.</span></span> <span data-ttu-id="5a37c-173">Verifique se você está executando o em um desejado `Platform` usando um dos métodos de verificação de plataforma, por exemplo, `OperatingSystem.Is<Platform>()` ou `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-173">Check whether you're running on a desired `Platform` by using one of platform-check methods, for example, `OperatingSystem.Is<Platform>()` or `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span></span>

- <span data-ttu-id="5a37c-174">**Marque o local de chamada como específico da plataforma**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-174">**Mark the call site as platform-specific**.</span></span> <span data-ttu-id="5a37c-175">Você também pode optar por marcar suas próprias APIs como sendo específicas da plataforma, apenas encaminhando efetivamente os requisitos para seus chamadores.</span><span class="sxs-lookup"><span data-stu-id="5a37c-175">You can also choose to mark your own APIs as being platform-specific, thus effectively just forwarding the requirements to your callers.</span></span> <span data-ttu-id="5a37c-176">Marque o método ou tipo recipiente ou o assembly inteiro com os mesmos atributos que a chamada dependente de plataforma referenciada.</span><span class="sxs-lookup"><span data-stu-id="5a37c-176">Mark the containing method or type or the entire assembly with the same attributes as the referenced platform-dependent call.</span></span> <span data-ttu-id="5a37c-177">[Exemplos](#mark-call-site-as-platform-specific).</span><span class="sxs-lookup"><span data-stu-id="5a37c-177">[Examples](#mark-call-site-as-platform-specific).</span></span>

- <span data-ttu-id="5a37c-178">**Declare o site de chamada com verificação de plataforma**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-178">**Assert the call site with platform check**.</span></span> <span data-ttu-id="5a37c-179">Se você não quiser a sobrecarga de uma `if` instrução adicional em tempo de execução, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5a37c-179">If you don't want the overhead of an additional `if` statement at run time, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5a37c-180">[Exemplo](#assert-the-call-site-with-platform-check).</span><span class="sxs-lookup"><span data-stu-id="5a37c-180">[Example](#assert-the-call-site-with-platform-check).</span></span>

- <span data-ttu-id="5a37c-181">**Exclua o código**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-181">**Delete the code**.</span></span> <span data-ttu-id="5a37c-182">Geralmente, não é o que você deseja porque isso significa que você perde a fidelidade quando seu código é usado por usuários do Windows.</span><span class="sxs-lookup"><span data-stu-id="5a37c-182">Generally not what you want because it means you lose fidelity when your code is used by Windows users.</span></span> <span data-ttu-id="5a37c-183">Para casos em que existe uma alternativa de plataforma cruzada, você provavelmente é melhor usá-la em APIs específicas da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-183">For cases where a cross-platform alternative exists, you're likely better off using that over platform-specific APIs.</span></span>

- <span data-ttu-id="5a37c-184">**Suprimir o aviso**.</span><span class="sxs-lookup"><span data-stu-id="5a37c-184">**Suppress the warning**.</span></span> <span data-ttu-id="5a37c-185">Você também pode simplesmente suprimir o aviso, seja por meio de uma entrada EditorConfig ou `#pragma warning disable ca1416` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-185">You can also simply suppress the warning, either via an EditorConfig entry or `#pragma warning disable ca1416`.</span></span> <span data-ttu-id="5a37c-186">No entanto, essa opção deve ser um último recurso ao usar APIs específicas da plataforma.</span><span class="sxs-lookup"><span data-stu-id="5a37c-186">However, this option should be a last resort when using platform-specific APIs.</span></span>

### <a name="guard-platform-specific-apis-with-guard-methods"></a><span data-ttu-id="5a37c-187">Proteger APIs específicas da plataforma com métodos de proteção</span><span class="sxs-lookup"><span data-stu-id="5a37c-187">Guard platform-specific APIs with guard methods</span></span>

<span data-ttu-id="5a37c-188">O nome da plataforma do método de proteção deve corresponder ao nome da plataforma de API dependente de plataforma de chamada.</span><span class="sxs-lookup"><span data-stu-id="5a37c-188">The guard method's platform name should match with the calling platform-dependent API platform name.</span></span> <span data-ttu-id="5a37c-189">Se a cadeia de caracteres de plataforma da API de chamada incluir a versão:</span><span class="sxs-lookup"><span data-stu-id="5a37c-189">If the platform string of the calling API includes the version:</span></span>

- <span data-ttu-id="5a37c-190">Para o `[SupportedOSPlatform("platformVersion")]` atributo, a plataforma do método de proteção `version` deve ser maior ou igual às plataformas de chamada `Version` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-190">For the `[SupportedOSPlatform("platformVersion")]` attribute, the guard method platform `version` should be greater than or equal to the calling platform's `Version`.</span></span>
- <span data-ttu-id="5a37c-191">Para o `[UnsupportedOSPlatform("platformVersion")]` atributo, a plataforma do método de proteção `version` deve ser menor ou igual ao da plataforma de chamada `Version` .</span><span class="sxs-lookup"><span data-stu-id="5a37c-191">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the guard method's platform `version` should be less than or equal to the calling platform's `Version`.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- <span data-ttu-id="5a37c-192">Se você precisar proteger código direcionado `netstandard` ou `netcoreapp` onde novas <xref:System.OperatingSystem> APIs não estão disponíveis, a <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API poderá ser usada e será respeitada pelo analisador.</span><span class="sxs-lookup"><span data-stu-id="5a37c-192">If you need to guard code that targets `netstandard` or `netcoreapp` where new <xref:System.OperatingSystem> APIs are not available, the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API can be used and will be respected by the analyzer.</span></span> <span data-ttu-id="5a37c-193">Mas não é tão otimizado quanto as novas APIs adicionadas no <xref:System.OperatingSystem> .</span><span class="sxs-lookup"><span data-stu-id="5a37c-193">But it's not as optimized as the new APIs added in <xref:System.OperatingSystem>.</span></span> <span data-ttu-id="5a37c-194">Se a plataforma não tiver suporte na <xref:System.Runtime.InteropServices.OSPlatform> estrutura, você poderá chamar <xref:System.Runtime.InteropServices.OSPlatform.Create(System.String)?displayProperty=nameWithType> e passar o nome da plataforma, que o analisador também respeita.</span><span class="sxs-lookup"><span data-stu-id="5a37c-194">If the platform is not supported in the <xref:System.Runtime.InteropServices.OSPlatform> struct, you can call <xref:System.Runtime.InteropServices.OSPlatform.Create(System.String)?displayProperty=nameWithType> and pass in the platform name, which the analyzer also respects.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a><span data-ttu-id="5a37c-195">Marcar site de chamada como específico da plataforma</span><span class="sxs-lookup"><span data-stu-id="5a37c-195">Mark call site as platform-specific</span></span>

<span data-ttu-id="5a37c-196">Os nomes de plataforma devem corresponder à API dependente de plataforma de chamada.</span><span class="sxs-lookup"><span data-stu-id="5a37c-196">Platform names should match the calling platform-dependent API.</span></span> <span data-ttu-id="5a37c-197">Se a cadeia de caracteres da plataforma incluir uma versão:</span><span class="sxs-lookup"><span data-stu-id="5a37c-197">If the platform string includes a version:</span></span>

- <span data-ttu-id="5a37c-198">Para o `[SupportedOSPlatform("platformVersion")]` atributo, a plataforma do site de chamada `version` deve ser maior ou igual ao da plataforma de chamada `Version`</span><span class="sxs-lookup"><span data-stu-id="5a37c-198">For the `[SupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be greater than or equal to the calling platform's `Version`</span></span>
- <span data-ttu-id="5a37c-199">Para o `[UnsupportedOSPlatform("platformVersion")]` atributo, a plataforma do site de chamada `version` deve ser menor ou igual ao da plataforma de chamada `Version`</span><span class="sxs-lookup"><span data-stu-id="5a37c-199">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be less than or equal to the calling platform's `Version`</span></span>

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a><span data-ttu-id="5a37c-200">Declarar o site de chamada com verificação de plataforma</span><span class="sxs-lookup"><span data-stu-id="5a37c-200">Assert the call-site with platform check</span></span>

<span data-ttu-id="5a37c-201">Todas as verificações condicionais usadas nos [exemplos do Platform Guard](#guard-platform-specific-apis-with-guard-methods) também podem ser usadas como a condição para <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5a37c-201">All the conditional checks used in the [platform guard examples](#guard-platform-specific-apis-with-guard-methods) can also be used as the condition for <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span>

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a><span data-ttu-id="5a37c-202">Confira também</span><span class="sxs-lookup"><span data-stu-id="5a37c-202">See also</span></span>

- [<span data-ttu-id="5a37c-203">Nomes de estrutura de destino no .NET 5</span><span class="sxs-lookup"><span data-stu-id="5a37c-203">Target Framework Names in .NET 5</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [<span data-ttu-id="5a37c-204">Anotando APIs específicas da plataforma e detectando seu uso</span><span class="sxs-lookup"><span data-stu-id="5a37c-204">Annotating platform-specific APIs and detecting its use</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [<span data-ttu-id="5a37c-205">Anotando APIs como sem suporte em plataformas específicas</span><span class="sxs-lookup"><span data-stu-id="5a37c-205">Annotating APIs as unsupported on specific platforms</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [<span data-ttu-id="5a37c-206">Analisador de compatibilidade de plataforma CA1416</span><span class="sxs-lookup"><span data-stu-id="5a37c-206">CA1416 Platform compatibility analyzer</span></span>](../../fundamentals/code-analysis/quality-rules/ca1416.md)
- [<span data-ttu-id="5a37c-207">Analisador de API do .NET</span><span class="sxs-lookup"><span data-stu-id="5a37c-207">.NET API analyzer</span></span>](../../standard/analyzers/api-analyzer.md)
