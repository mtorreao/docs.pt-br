---
title: 'Alteração significativa: o símbolo de pré-processador de NETCOREAPP3_1 não é definido ao direcionar o .NET 5'
description: Saiba mais sobre a alteração significativa no .NET 5,0, em que os projetos não definem mais os símbolos de pré-processador para versões anteriores.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760364"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="61c9e-103">NETCOREAPP3_1 símbolo de pré-processador não está definido ao direcionar para o .NET 5</span><span class="sxs-lookup"><span data-stu-id="61c9e-103">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="61c9e-104">No .NET 5,0 RC2 e versões posteriores, os projetos não definem mais os símbolos de pré-processador para versões anteriores, mas apenas para a versão que eles visam.</span><span class="sxs-lookup"><span data-stu-id="61c9e-104">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="61c9e-105">Esse é o mesmo comportamento do .NET Core 1,0-3,1.</span><span class="sxs-lookup"><span data-stu-id="61c9e-105">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="61c9e-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="61c9e-106">Version introduced</span></span>

<span data-ttu-id="61c9e-107">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="61c9e-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="61c9e-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="61c9e-108">Change description</span></span>

<span data-ttu-id="61c9e-109">No .NET 5,0 Preview 7 até RC1, projetos que visam `net5.0` definir tanto os símbolos como os `NETCOREAPP3_1` de `NET5_0` pré-processador.</span><span class="sxs-lookup"><span data-stu-id="61c9e-109">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="61c9e-110">A intenção por trás dessa mudança de comportamento era que, a partir do .NET 5,0, os símbolos de compilação condicional [seriam cumulativos](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="61c9e-110">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="61c9e-111">No .NET 5,0 RC2 e posterior, os projetos definem apenas símbolos para os monikers do Framework de destino (TFM) que ele tem como destino e não para versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="61c9e-111">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="61c9e-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="61c9e-112">Reason for change</span></span>

<span data-ttu-id="61c9e-113">A alteração da visualização 7 foi revertida devido aos comentários do cliente.</span><span class="sxs-lookup"><span data-stu-id="61c9e-113">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="61c9e-114">A definição de símbolos para versões anteriores surpreendeu e confundiu clientes, e algumas assumiu que era um bug no compilador C#.</span><span class="sxs-lookup"><span data-stu-id="61c9e-114">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="61c9e-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="61c9e-115">Recommended action</span></span>

<span data-ttu-id="61c9e-116">Certifique-se de que sua `#if` lógica não assuma que `NETCOREAPP3_1` é definida quando o projeto é direcionado `net5.0` ou superior.</span><span class="sxs-lookup"><span data-stu-id="61c9e-116">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="61c9e-117">Em vez disso, suponha que `NETCOREAPP3_1` seja definido apenas quando o projeto se destina explicitamente `netcoreapp3.1` .</span><span class="sxs-lookup"><span data-stu-id="61c9e-117">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="61c9e-118">Por exemplo, se o seu projeto tem vários destinos para .NET Core 2,1 e .NET Core 3,1 e você chama as APIs que foram introduzidas no .NET Core 3,1, sua `#if` lógica deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="61c9e-118">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a><span data-ttu-id="61c9e-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="61c9e-119">Affected APIs</span></span>

<span data-ttu-id="61c9e-120">N/D</span><span class="sxs-lookup"><span data-stu-id="61c9e-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
