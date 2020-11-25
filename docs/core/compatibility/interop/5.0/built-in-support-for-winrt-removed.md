---
title: 'Alteração significativa: o suporte interno para o WinRT é removido do .NET'
description: Saiba mais sobre a alteração significativa de interoperabilidade no .NET 5,0, em que o suporte interno para o WinRT é removido do .NET.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760414"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="f7494-103">O suporte interno para o WinRT é removido do .NET</span><span class="sxs-lookup"><span data-stu-id="f7494-103">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="f7494-104">O suporte interno para consumo de APIs do [tempo de execução do Windows (WinRT)](/uwp/winrt-cref/winrt-type-system) no .net foi removido.</span><span class="sxs-lookup"><span data-stu-id="f7494-104">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f7494-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="f7494-105">Version introduced</span></span>

<span data-ttu-id="f7494-106">5.0</span><span class="sxs-lookup"><span data-stu-id="f7494-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="f7494-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="f7494-107">Change description</span></span>

<span data-ttu-id="f7494-108">Anteriormente, o CoreCLR poderia consumir [arquivos de metadados do Windows (WinMD)](/uwp/winrt-cref/winmd-files) para ativar e consumir tipos de WinRT.</span><span class="sxs-lookup"><span data-stu-id="f7494-108">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="f7494-109">A partir do .NET 5,0, o CoreCLR não pode mais consumir arquivos WinMD diretamente.</span><span class="sxs-lookup"><span data-stu-id="f7494-109">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="f7494-110">Se você tentar fazer referência a um assembly sem suporte, obterá um <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="f7494-110">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="f7494-111">Se você ativar uma classe do WinRT, obterá um <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="f7494-111">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="f7494-112">Essa alteração significativa foi feita pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="f7494-112">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="f7494-113">Portanto, o WinRT pode ser desenvolvido e aprimorado separadamente do tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="f7494-113">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="f7494-114">Para simetria com sistemas de interoperabilidade fornecidos para outros sistemas operacionais, como iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="f7494-114">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="f7494-115">Para tirar proveito de outros recursos do .NET, como recursos C#, vinculação de IL (linguagem intermediária) e compilação de AOT (antecipadamente de tempo).</span><span class="sxs-lookup"><span data-stu-id="f7494-115">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="f7494-116">Para simplificar a base de código .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="f7494-116">To simplify the .NET runtime codebase.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f7494-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="f7494-117">Recommended action</span></span>

- <span data-ttu-id="f7494-118">Remova as referências ao [pacote Microsoft. Windows. Sdk. Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span><span class="sxs-lookup"><span data-stu-id="f7494-118">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="f7494-119">Em vez disso, especifique a versão das APIs do Windows que você deseja acessar por meio da `TargetFramework` Propriedade do projeto.</span><span class="sxs-lookup"><span data-stu-id="f7494-119">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="f7494-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f7494-120">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="f7494-121">Use a cadeia de ferramentas [/WinRT do C#](/windows/uwp/csharp-winrt/) para gerar ou personalizar APIs e tipos do WinRT para .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7494-121">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5.0 and later versions.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f7494-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="f7494-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
