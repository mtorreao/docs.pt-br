---
title: 'Alteração significativa: CA2014: não use stackalloc em loops'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA2014.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760301"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="2f972-103">Aviso CA2014: não use stackalloc em loops</span><span class="sxs-lookup"><span data-stu-id="2f972-103">Warning CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="2f972-104">A regra do analisador de código .NET [CA2014](/visualstudio/code-quality/ca2014) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="2f972-104">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="2f972-105">Ele produz um aviso de compilação para qualquer código C# em que uma expressão [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) é usada dentro de um loop.</span><span class="sxs-lookup"><span data-stu-id="2f972-105">It produces a build warning for any C# code where a [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

## <a name="change-description"></a><span data-ttu-id="2f972-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="2f972-106">Change description</span></span>

<span data-ttu-id="2f972-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f972-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="2f972-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="2f972-108">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="2f972-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="2f972-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="2f972-110">A regra CA2014 procura código C# em que uma [expressão stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) é usada dentro de um loop.</span><span class="sxs-lookup"><span data-stu-id="2f972-110">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="2f972-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) aloca memória a partir do quadro de pilhas atual.</span><span class="sxs-lookup"><span data-stu-id="2f972-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="2f972-112">A memória não é liberada até que a chamada de método atual seja retornada, o que pode levar a estouros de pilha.</span><span class="sxs-lookup"><span data-stu-id="2f972-112">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="2f972-113">Como não é possível capturar exceções de estouro de pilha, o aplicativo será encerrado em caso de estouro de pilha.</span><span class="sxs-lookup"><span data-stu-id="2f972-113">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2f972-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="2f972-114">Version introduced</span></span>

<span data-ttu-id="2f972-115">5.0</span><span class="sxs-lookup"><span data-stu-id="2f972-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2f972-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="2f972-116">Recommended action</span></span>

- <span data-ttu-id="2f972-117">Evite usar loops [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) .</span><span class="sxs-lookup"><span data-stu-id="2f972-117">Avoid using [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="2f972-118">Aloque o bloco de memória fora do loop e reutilize-o dentro do loop.</span><span class="sxs-lookup"><span data-stu-id="2f972-118">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="2f972-119">Para obter mais informações, consulte [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="2f972-119">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="2f972-120">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="2f972-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="2f972-121">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="2f972-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2f972-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="2f972-122">Affected APIs</span></span>

<span data-ttu-id="2f972-123">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="2f972-123">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
