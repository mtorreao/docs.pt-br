---
title: 'Alteração significativa: CA1417: OutAttribute no parâmetro de cadeia de caracteres para P/Invoke'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA1417.
ms.date: 09/29/2020
ms.openlocfilehash: 3316d07108ec7f9da985494413336cba6d560dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760306"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="ba472-103">Aviso CA1417: OutAttribute no parâmetro de cadeia de caracteres para P/Invoke</span><span class="sxs-lookup"><span data-stu-id="ba472-103">Warning CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="ba472-104">A regra do analisador de código .NET [CA1417](/visualstudio/code-quality/ca1417) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="ba472-104">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="ba472-105">Ele produz um aviso de compilação para qualquer definição de método de [invocação de plataforma (P/Invoke)](../../../../standard/native-interop/pinvoke.md) , em que um <xref:System.String> parâmetro é passado por valor e marcado com <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="ba472-105">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

## <a name="change-description"></a><span data-ttu-id="ba472-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="ba472-106">Change description</span></span>

<span data-ttu-id="ba472-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba472-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="ba472-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="ba472-108">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="ba472-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="ba472-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="ba472-110">Regra CA1417 flags [P/Invoke](../../../../standard/native-interop/pinvoke.md) definições de método em que um <xref:System.String> parâmetro é marcado com o <xref:System.Runtime.InteropServices.OutAttribute> atributo e é passado por valor.</span><span class="sxs-lookup"><span data-stu-id="ba472-110">Rule CA1417 flags [P/Invoke](../../../../standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="ba472-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ba472-111">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="ba472-112">O tempo de execução do .NET mantém uma tabela, chamada de pool do estagiário, que contém uma única referência a cada cadeia de caracteres literal exclusiva em um programa.</span><span class="sxs-lookup"><span data-stu-id="ba472-112">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="ba472-113">Se uma cadeia de caracteres do InterNIC marcada com <xref:System.Runtime.InteropServices.OutAttribute> for passada por valor para um método P/Invoke, o tempo de execução poderá ser desestabilizado.</span><span class="sxs-lookup"><span data-stu-id="ba472-113">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="ba472-114">Para obter mais informações sobre o InterNIC da cadeia de caracteres, consulte comentários para <xref:System.String.Intern(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ba472-114">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ba472-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ba472-115">Version introduced</span></span>

<span data-ttu-id="ba472-116">5.0</span><span class="sxs-lookup"><span data-stu-id="ba472-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ba472-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ba472-117">Recommended action</span></span>

- <span data-ttu-id="ba472-118">Se você precisar realizar o marshaling dos dados de cadeia de caracteres modificados de volta para o chamador, passe a cadeia de caracteres por referência.</span><span class="sxs-lookup"><span data-stu-id="ba472-118">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="ba472-119">Se você não precisar realizar o marshaling dos dados de cadeia de caracteres modificados de volta para o chamador, simplesmente remova o <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="ba472-119">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="ba472-120">Para obter mais informações, consulte [CA1417](/visualstudio/code-quality/ca1417).</span><span class="sxs-lookup"><span data-stu-id="ba472-120">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="ba472-121">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="ba472-121">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="ba472-122">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="ba472-122">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ba472-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ba472-123">Affected APIs</span></span>

<span data-ttu-id="ba472-124">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="ba472-124">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
