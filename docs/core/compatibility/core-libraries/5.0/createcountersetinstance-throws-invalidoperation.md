---
title: 'Alteração significativa: CreateCounterSetInstance gera InvalidOperationException se a instância já existe'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que CounterSet. CreateCounterSetInstance gera uma exceção diferente se o contador já existir.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760419"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="b4d13-103">CounterSet. CreateCounterSetInstance agora lança InvalidOperationException se a instância já existe</span><span class="sxs-lookup"><span data-stu-id="b4d13-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="b4d13-104">A partir do .NET 5,0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> o lançará um <xref:System.InvalidOperationException> em vez de um <xref:System.ArgumentException> se o conjunto de contadores já existir.</span><span class="sxs-lookup"><span data-stu-id="b4d13-104">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="b4d13-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="b4d13-105">Change description</span></span>

<span data-ttu-id="b4d13-106">No .NET Framework e no .NET Core 1,0 a 3,1, você pode criar uma instância do conjunto de contadores chamando <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> .</span><span class="sxs-lookup"><span data-stu-id="b4d13-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="b4d13-107">No entanto, se o conjunto de contadores já existir, o método lançará uma <xref:System.ArgumentException> exceção.</span><span class="sxs-lookup"><span data-stu-id="b4d13-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="b4d13-108">No .NET 5,0 e versões posteriores, quando você chama <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> e o conjunto de contadores existe, uma <xref:System.InvalidOperationException> exceção é lançada.</span><span class="sxs-lookup"><span data-stu-id="b4d13-108">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b4d13-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="b4d13-109">Version introduced</span></span>

<span data-ttu-id="b4d13-110">5.0</span><span class="sxs-lookup"><span data-stu-id="b4d13-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b4d13-111">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="b4d13-111">Recommended action</span></span>

<span data-ttu-id="b4d13-112">Se você capturar <xref:System.ArgumentException> exceções em seu aplicativo ao chamar <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> , considere também capturar <xref:System.InvalidOperationException> exceções.</span><span class="sxs-lookup"><span data-stu-id="b4d13-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="b4d13-113"><xref:System.ArgumentException>Não é recomendável capturar exceções.</span><span class="sxs-lookup"><span data-stu-id="b4d13-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b4d13-114">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b4d13-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
