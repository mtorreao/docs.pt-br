---
title: 'Alteração significativa: CA2200: relançar para preservar detalhes da pilha'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA2200.
ms.date: 09/03/2020
ms.openlocfilehash: 74e169906a8b826328de8d4c5f69c32234c2ce95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760404"
---
# <a name="warning-ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="d4aac-103">Aviso CA2200: relançar para preservar detalhes da pilha</span><span class="sxs-lookup"><span data-stu-id="d4aac-103">Warning CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="d4aac-104">A regra do analisador de código .NET [CA2200](/visualstudio/code-quality/ca2200) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="d4aac-104">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="d4aac-105">Ele produz um aviso de compilação para quaisquer `catch` blocos que relançam uma exceção e a exceção é explicitamente especificada na `throw` instrução.</span><span class="sxs-lookup"><span data-stu-id="d4aac-105">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

## <a name="change-description"></a><span data-ttu-id="d4aac-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="d4aac-106">Change description</span></span>

<span data-ttu-id="d4aac-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4aac-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="d4aac-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="d4aac-108">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="d4aac-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="d4aac-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="d4aac-110">O código de sinalizadores CA2200 de regra em que as exceções são relançadas e a variável de exceção é especificada na `throw` instrução.</span><span class="sxs-lookup"><span data-stu-id="d4aac-110">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="d4aac-111">Quando uma exceção é lançada, parte das informações que ela transporta é o rastreamento de pilha.</span><span class="sxs-lookup"><span data-stu-id="d4aac-111">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="d4aac-112">O rastreamento de pilha é uma lista da hierarquia de chamada de método que começa com o método que gera a exceção e termina com o método que captura a exceção.</span><span class="sxs-lookup"><span data-stu-id="d4aac-112">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="d4aac-113">Se uma exceção for relançada especificando a exceção na `throw` instrução, o rastreamento de pilha reiniciará no método atual e a lista de chamadas de método entre o método original que gerou a exceção e o método atual será perdido.</span><span class="sxs-lookup"><span data-stu-id="d4aac-113">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="d4aac-114">Para manter as informações de rastreamento da pilha original com a exceção, use a `throw` instrução sem especificar a exceção.</span><span class="sxs-lookup"><span data-stu-id="d4aac-114">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="d4aac-115">O trecho de código a seguir não produz um aviso para a regra CA2200.</span><span class="sxs-lookup"><span data-stu-id="d4aac-115">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="d4aac-116">No entanto, *a linha* comentada dispararia uma violação.</span><span class="sxs-lookup"><span data-stu-id="d4aac-116">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

## <a name="version-introduced"></a><span data-ttu-id="d4aac-117">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="d4aac-117">Version introduced</span></span>

<span data-ttu-id="d4aac-118">5.0</span><span class="sxs-lookup"><span data-stu-id="d4aac-118">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d4aac-119">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="d4aac-119">Recommended action</span></span>

- <span data-ttu-id="d4aac-120">Relançar exceções sem especificar a exceção explicitamente.</span><span class="sxs-lookup"><span data-stu-id="d4aac-120">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="d4aac-121">Para obter mais informações, consulte [CA2200](/visualstudio/code-quality/ca2200).</span><span class="sxs-lookup"><span data-stu-id="d4aac-121">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="d4aac-122">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="d4aac-122">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="d4aac-123">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="d4aac-123">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d4aac-124">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d4aac-124">Affected APIs</span></span>

<span data-ttu-id="d4aac-125">Não detectável via análise de API.</span><span class="sxs-lookup"><span data-stu-id="d4aac-125">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
