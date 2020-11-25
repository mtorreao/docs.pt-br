---
title: 'Alteração significativa: CA1416: compatibilidade de plataforma'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA1416.
ms.date: 09/29/2020
ms.openlocfilehash: ec3fc809b8de382a2093fc9f2d33c2f96b91613d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760309"
---
# <a name="warning-ca1416-platform-compatibility"></a><span data-ttu-id="58e11-103">Aviso CA1416: compatibilidade de plataforma</span><span class="sxs-lookup"><span data-stu-id="58e11-103">Warning CA1416: Platform compatibility</span></span>

<span data-ttu-id="58e11-104">A regra do analisador de código .NET [CA1416](/visualstudio/code-quality/ca1416) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="58e11-104">.NET code analyzer rule [CA1416](/visualstudio/code-quality/ca1416) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="58e11-105">Ele produz um aviso de compilação para chamadas a APIs específicas da plataforma de sites de chamada que não verificam o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="58e11-105">It produces a build warning for calls to platform-specific APIs from call sites that don't verify the operating system.</span></span>

## <a name="change-description"></a><span data-ttu-id="58e11-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="58e11-106">Change description</span></span>

<span data-ttu-id="58e11-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="58e11-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="58e11-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA1416](/visualstudio/code-quality/ca1416).</span><span class="sxs-lookup"><span data-stu-id="58e11-108">Several of these rules are enabled, by default, including [CA1416](/visualstudio/code-quality/ca1416).</span></span> <span data-ttu-id="58e11-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="58e11-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span> <span data-ttu-id="58e11-110">A regra CA1416 informa quando você está usando APIs específicas da plataforma de locais onde o contexto da plataforma não é verificado.</span><span class="sxs-lookup"><span data-stu-id="58e11-110">Rule CA1416 informs you when you're using platform-specific APIs from places where the platform context isn't verified.</span></span>

<span data-ttu-id="58e11-111">A regra [CA1416](/visualstudio/code-quality/ca1416), o analisador de compatibilidade de plataforma, trabalha em conjunto com alguns outros recursos que são novos no .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="58e11-111">Rule [CA1416](/visualstudio/code-quality/ca1416), the platform compatibility analyzer, works hand-in-hand with some other features that are new in .NET 5.0.</span></span> <span data-ttu-id="58e11-112">O .NET 5,0 apresenta o <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> e o <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> , que permitem especificar as plataformas nas quais uma API *é* ou *não* tem suporte.</span><span class="sxs-lookup"><span data-stu-id="58e11-112">.NET 5.0 introduces the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, which let you specify the platforms that an API *is* or *isn't* supported on.</span></span> <span data-ttu-id="58e11-113">Na ausência desses atributos, pressupõe-se que uma API tenha suporte em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="58e11-113">In the absence of these attributes, an API is assumed to be supported on all platforms.</span></span> <span data-ttu-id="58e11-114">Esses atributos foram aplicados a APIs específicas da plataforma nas principais bibliotecas do .NET.</span><span class="sxs-lookup"><span data-stu-id="58e11-114">These attributes have been applied to platform-specific APIs in the core .NET libraries.</span></span>

<span data-ttu-id="58e11-115">Em projetos que visam plataformas para as quais as APIs que eles usam não estão disponíveis, a regra [CA1416](/visualstudio/code-quality/ca1416) sinaliza qualquer chamada de API específica da plataforma onde o contexto da plataforma não é verificado.</span><span class="sxs-lookup"><span data-stu-id="58e11-115">In projects that target platforms for which APIs that they use aren't available, rule [CA1416](/visualstudio/code-quality/ca1416) flags any platform-specific API call where the platform context isn't verified.</span></span> <span data-ttu-id="58e11-116">A maioria das APIs que agora estão decoradas com <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> os <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> atributos e gera <xref:System.PlatformNotSupportedException> exceções quando elas são invocadas em um sistema operacional sem suporte.</span><span class="sxs-lookup"><span data-stu-id="58e11-116">Most of the APIs that are now decorated with the <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> attributes throw <xref:System.PlatformNotSupportedException> exceptions when they're invoked on an unsupported operating system.</span></span> <span data-ttu-id="58e11-117">Agora que essas APIs estão marcadas como específicas da plataforma, a regra [CA1416](/visualstudio/code-quality/ca1416) ajuda você a evitar exceções em tempo de execução <xref:System.PlatformNotSupportedException> adicionando verificações do sistema operacional aos seus sites de chamada.</span><span class="sxs-lookup"><span data-stu-id="58e11-117">Now that these APIs are marked as platform-specific, rule [CA1416](/visualstudio/code-quality/ca1416) helps you prevent run-time <xref:System.PlatformNotSupportedException> exceptions by adding OS checks to your call sites.</span></span>

## <a name="examples"></a><span data-ttu-id="58e11-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="58e11-118">Examples</span></span>

- <span data-ttu-id="58e11-119">O <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> método só tem suporte no Windows e é decorado com `[SupportedOSPlatform("windows")]` .</span><span class="sxs-lookup"><span data-stu-id="58e11-119">The <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> method is only supported on Windows and is decorated with `[SupportedOSPlatform("windows")]`.</span></span> <span data-ttu-id="58e11-120">O código a seguir produzirá um aviso de CA1416 no momento da compilação se o projeto tiver como [destino](../../../../standard/frameworks.md) `net5.0` (mas não `net5.0-windows` ).</span><span class="sxs-lookup"><span data-stu-id="58e11-120">The following code will produce a CA1416 warning at build time if the project [targets](../../../../standard/frameworks.md) `net5.0` (but not `net5.0-windows`).</span></span> <span data-ttu-id="58e11-121">Para ações que você pode executar para evitar o aviso, consulte a [ação recomendada](#recommended-action).</span><span class="sxs-lookup"><span data-stu-id="58e11-121">For actions you can take to avoid the warning, see [Recommended action](#recommended-action).</span></span>

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <span data-ttu-id="58e11-122">O <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> método não tem suporte no navegador e é decorado com `[UnsupportedOSPlatform("browser")]` .</span><span class="sxs-lookup"><span data-stu-id="58e11-122">The <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> method is not supported in the browser and is decorated with `[UnsupportedOSPlatform("browser")]`.</span></span> <span data-ttu-id="58e11-123">O código a seguir produzirá um aviso de CA1416 no momento da compilação se o projeto der suporte à plataforma do navegador.</span><span class="sxs-lookup"><span data-stu-id="58e11-123">The following code will produce a CA1416 warning at build time if the project supports the browser platform.</span></span>

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - <span data-ttu-id="58e11-124">Os projetos de Webassembly mais incrivelmente e projetos de biblioteca de classes Razor incluem suporte de navegador automaticamente.</span><span class="sxs-lookup"><span data-stu-id="58e11-124">Blazor WebAssembly projects and Razor class library projects include browser support automatically.</span></span>
  > - <span data-ttu-id="58e11-125">Para adicionar manualmente o navegador como uma plataforma com suporte para seu projeto, adicione a seguinte entrada ao arquivo de projeto:</span><span class="sxs-lookup"><span data-stu-id="58e11-125">To manually add the browser as a supported platform for your project, add the following entry to your project file:</span></span>
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

## <a name="version-introduced"></a><span data-ttu-id="58e11-126">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="58e11-126">Version introduced</span></span>

<span data-ttu-id="58e11-127">5.0</span><span class="sxs-lookup"><span data-stu-id="58e11-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="58e11-128">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="58e11-128">Recommended action</span></span>

<span data-ttu-id="58e11-129">Verifique se as APIs específicas da plataforma são chamadas apenas quando o código está sendo executado em uma plataforma apropriada.</span><span class="sxs-lookup"><span data-stu-id="58e11-129">Ensure that platform-specific APIs are only called when the code is running on an appropriate platform.</span></span> <span data-ttu-id="58e11-130">Você pode verificar o sistema operacional atual usando um dos `Is<Platform>` métodos na classe, <xref:System.OperatingSystem?displayProperty=nameWithType> por exemplo,, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> antes de chamar uma API específica da plataforma.</span><span class="sxs-lookup"><span data-stu-id="58e11-130">You can check the current operating system using one of the `Is<Platform>` methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class, for example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>, before calling a platform-specific API.</span></span>

<span data-ttu-id="58e11-131">Você pode usar um dos `Is<Platform>` métodos na condição de uma `if` instrução:</span><span class="sxs-lookup"><span data-stu-id="58e11-131">You can use one of the `Is<Platform>` methods in the condition of an `if` statement:</span></span>

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

<span data-ttu-id="58e11-132">Ou, se você não quiser a sobrecarga de uma `if` instrução adicional em tempo de execução, chame <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> :</span><span class="sxs-lookup"><span data-stu-id="58e11-132">Or, if you don't want the overhead of an additional `if` statement at run time, call <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> instead:</span></span>

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="58e11-133">Se você estiver criando uma biblioteca, poderá marcar sua API como específica da plataforma.</span><span class="sxs-lookup"><span data-stu-id="58e11-133">If you're authoring a library, you can mark your API as platform-specific.</span></span> <span data-ttu-id="58e11-134">Nesse caso, a carga dos requisitos de verificação cai nos seus chamadores.</span><span class="sxs-lookup"><span data-stu-id="58e11-134">In this case, the burden of checking requirements falls on your callers.</span></span> <span data-ttu-id="58e11-135">Você pode marcar métodos ou tipos específicos ou um assembly inteiro.</span><span class="sxs-lookup"><span data-stu-id="58e11-135">You can mark specific methods or types or an entire assembly.</span></span>

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

<span data-ttu-id="58e11-136">Se você não quiser corrigir todos os seus sites de chamada, poderá escolher uma das seguintes opções para suprimir o aviso:</span><span class="sxs-lookup"><span data-stu-id="58e11-136">If you don't want to fix all your call sites, you can choose one of the following options to suppress the warning:</span></span>

- <span data-ttu-id="58e11-137">Para suprimir a regra CA1416, você pode fazer isso usando `#pragma` o ou o sinalizador do compilador [-nowarn](../../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) ou [definindo a severidade da regra](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) como `none` em um arquivo. editorconfig.</span><span class="sxs-lookup"><span data-stu-id="58e11-137">To suppress rule CA1416, you can do so using `#pragma` or the [-nowarn](../../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) compiler flag, or by [setting the rule's severity](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) to `none` in an .editorconfig file.</span></span>

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- <span data-ttu-id="58e11-138">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="58e11-138">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="58e11-139">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="58e11-139">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="58e11-140">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="58e11-140">Affected APIs</span></span>

<span data-ttu-id="58e11-141">Para a plataforma Windows:</span><span class="sxs-lookup"><span data-stu-id="58e11-141">For Windows platform:</span></span>

- <span data-ttu-id="58e11-142">Todas as APIs listadas em <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md> .</span><span class="sxs-lookup"><span data-stu-id="58e11-142">All APIs listed at <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.</span></span>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

<span data-ttu-id="58e11-143">Para a plataforma Webassembly mais incrivelmente:</span><span class="sxs-lookup"><span data-stu-id="58e11-143">For Blazor WebAssembly platform:</span></span>

- <span data-ttu-id="58e11-144">Todas as APIs listadas em <https://github.com/dotnet/runtime/issues/41087> .</span><span class="sxs-lookup"><span data-stu-id="58e11-144">All APIs listed at <https://github.com/dotnet/runtime/issues/41087>.</span></span>

<!--

### Affected APIs

- ``

### Category

- Code analysis
- Core .NET libraries

-->

## <a name="see-also"></a><span data-ttu-id="58e11-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="58e11-145">See also</span></span>

- [<span data-ttu-id="58e11-146">CA1416: validar a compatibilidade da plataforma</span><span class="sxs-lookup"><span data-stu-id="58e11-146">CA1416: Validate platform compatibility</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="58e11-147">Analisador de API do .NET</span><span class="sxs-lookup"><span data-stu-id="58e11-147">.NET API analyzer</span></span>](../../../../standard/analyzers/api-analyzer.md)
