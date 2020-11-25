---
title: 'Alteração significativa: CA2247: o argumento para o Construtor TaskCompletionSource deve ser um valor TaskCreationOptions'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA2247.
ms.date: 09/03/2020
ms.openlocfilehash: 323fd5a05da4dfeb68ef75d88d5d293ba01c8ade
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760405"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="cdf55-103">Aviso CA2247: o argumento para o Construtor TaskCompletionSource deve ser um valor TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="cdf55-103">Warning CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="cdf55-104">A regra do analisador de código .NET [CA2247](/visualstudio/code-quality/ca2247) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="cdf55-104">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="cdf55-105">Ele produz um aviso de compilação para chamadas para o <xref:System.Threading.Tasks.TaskCompletionSource%601> Construtor que passa um argumento do tipo <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="cdf55-105">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

## <a name="change-description"></a><span data-ttu-id="cdf55-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="cdf55-106">Change description</span></span>

<span data-ttu-id="cdf55-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="cdf55-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="cdf55-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="cdf55-108">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="cdf55-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="cdf55-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="cdf55-110">A regra CA2247 localiza chamadas para o <xref:System.Threading.Tasks.TaskCompletionSource%601> Construtor que passa um argumento do tipo <xref:System.Threading.Tasks.TaskContinuationOptions> .</span><span class="sxs-lookup"><span data-stu-id="cdf55-110">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="cdf55-111">O <xref:System.Threading.Tasks.TaskCompletionSource%601> tipo tem um construtor que aceita um <xref:System.Threading.Tasks.TaskCreationOptions> valor e outro construtor que aceita um <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="cdf55-111">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="cdf55-112">Se você passar acidentalmente um <xref:System.Threading.Tasks.TaskContinuationOptions> valor em vez de um <xref:System.Threading.Tasks.TaskCreationOptions> valor, o construtor com o <xref:System.Object> parâmetro será chamado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="cdf55-112">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="cdf55-113">Seu código será compilado e executado, mas não terá o comportamento pretendido.</span><span class="sxs-lookup"><span data-stu-id="cdf55-113">Your code will compile and run but won't have the intended behavior.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cdf55-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="cdf55-114">Version introduced</span></span>

<span data-ttu-id="cdf55-115">5.0</span><span class="sxs-lookup"><span data-stu-id="cdf55-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cdf55-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="cdf55-116">Recommended action</span></span>

- <span data-ttu-id="cdf55-117">Substitua o <xref:System.Threading.Tasks.TaskContinuationOptions> argumento pelo valor correspondente <xref:System.Threading.Tasks.TaskCreationOptions> .</span><span class="sxs-lookup"><span data-stu-id="cdf55-117">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="cdf55-118">Não suprimir este aviso, pois quase sempre realça um bug em seu código.</span><span class="sxs-lookup"><span data-stu-id="cdf55-118">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="cdf55-119">Para obter mais informações, consulte [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="cdf55-119">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="cdf55-120">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="cdf55-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="cdf55-121">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="cdf55-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="cdf55-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="cdf55-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
