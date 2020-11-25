---
title: 'Alteração significativa: CA2013: não use ReferenceEquals com tipos de valor'
description: Saiba mais sobre a alteração significativa no .NET 5,0 causada pela habilitação da regra de análise de código CA2013.
ms.date: 09/03/2020
ms.openlocfilehash: ca2b845427eff547b996b577394c6859e30f50bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760302"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="6bb9d-103">Aviso CA2013: não use ReferenceEquals com tipos de valor</span><span class="sxs-lookup"><span data-stu-id="6bb9d-103">Warning CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="6bb9d-104">A regra do analisador de código .NET [CA2013](/visualstudio/code-quality/ca2013) está habilitada, por padrão, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-104">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="6bb9d-105">Ele produz um aviso de compilação para qualquer código em que <xref:System.Object.ReferenceEquals(System.Object,System.Object)> é usado para comparar um ou mais tipos de valor para igualdade.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-105">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

## <a name="change-description"></a><span data-ttu-id="6bb9d-106">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="6bb9d-106">Change description</span></span>

<span data-ttu-id="6bb9d-107">A partir do .NET 5,0, o SDK do .NET inclui [analisadores de código-fonte .net](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="6bb9d-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="6bb9d-108">Várias dessas regras estão habilitadas, por padrão, incluindo [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="6bb9d-108">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="6bb9d-109">Se o seu projeto contiver código que viole essa regra e estiver configurado para tratar avisos como erros, essa alteração poderá interromper sua compilação.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="6bb9d-110">A regra CA2013 localiza instâncias em que <xref:System.Object.ReferenceEquals(System.Object,System.Object)> é usada para comparar um ou mais tipos de valor para igualdade.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-110">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="6bb9d-111">Comparar tipos de valor para igualdade dessa maneira pode levar a resultados incorretos, porque os valores estão em caixa antes que eles sejam comparados.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-111">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="6bb9d-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> retornará `false` mesmo se os valores comparados representarem a mesma instância de um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6bb9d-113">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="6bb9d-113">Version introduced</span></span>

<span data-ttu-id="6bb9d-114">5.0</span><span class="sxs-lookup"><span data-stu-id="6bb9d-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6bb9d-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="6bb9d-115">Recommended action</span></span>

- <span data-ttu-id="6bb9d-116">Altere o código para usar um operador de igualdade apropriado, como `==` .</span><span class="sxs-lookup"><span data-stu-id="6bb9d-116">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="6bb9d-117">Você não deve suprimir este aviso.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-117">You should not suppress this warning.</span></span>

- <span data-ttu-id="6bb9d-118">Para desabilitar completamente a análise de código, defina `EnableNETAnalyzers` como `false` em seu arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="6bb9d-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="6bb9d-119">Para obter mais informações, consulte [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="6bb9d-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6bb9d-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="6bb9d-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
