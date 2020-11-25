---
title: 'Alteração significativa: nomes de parâmetros alterados no RC2'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET, em que alguns nomes de parâmetro do assembly de referência foram alterados nas versões Preview e Release-Candidate do .NET 5,0.
ms.date: 11/01/2020
ms.openlocfilehash: 554a4fa9e08fdb504f380465496d7e7e9df85814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760389"
---
# <a name="parameter-names-changed-in-rc2"></a><span data-ttu-id="0bf83-103">Nomes de parâmetros alterados no RC2</span><span class="sxs-lookup"><span data-stu-id="0bf83-103">Parameter names changed in RC2</span></span>

<span data-ttu-id="0bf83-104">Alguns nomes de parâmetro de assembly de referência foram alterados para corresponder nomes de parâmetro nos assemblies de implementação.</span><span class="sxs-lookup"><span data-stu-id="0bf83-104">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

## <a name="change-description"></a><span data-ttu-id="0bf83-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="0bf83-105">Change description</span></span>

<span data-ttu-id="0bf83-106">Nas versões anteriores do .NET 5,0 Preview e RC, alguns nomes de parâmetros de [assembly de referência](../../../../standard/assembly/reference-assemblies.md) são diferentes para seus parâmetros correspondentes no assembly de implementação.</span><span class="sxs-lookup"><span data-stu-id="0bf83-106">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="0bf83-107">Isso pode causar problemas ao usar argumentos nomeados e reflexão.</span><span class="sxs-lookup"><span data-stu-id="0bf83-107">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="0bf83-108">No .NET 5,0 RC2, esses nomes de parâmetro incompatíveis foram atualizados nos assemblies de referência para corresponder exatamente aos nomes de parâmetro correspondentes nos assemblies de implementação.</span><span class="sxs-lookup"><span data-stu-id="0bf83-108">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="0bf83-109">A tabela a seguir mostra as APIs e os nomes de parâmetro que foram alterados.</span><span class="sxs-lookup"><span data-stu-id="0bf83-109">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="0bf83-110">API</span><span class="sxs-lookup"><span data-stu-id="0bf83-110">API</span></span> | <span data-ttu-id="0bf83-111">Nome do parâmetro antigo</span><span class="sxs-lookup"><span data-stu-id="0bf83-111">Old parameter name</span></span> | <span data-ttu-id="0bf83-112">Nome do novo parâmetro</span><span class="sxs-lookup"><span data-stu-id="0bf83-112">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

## <a name="reason-for-change"></a><span data-ttu-id="0bf83-113">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="0bf83-113">Reason for change</span></span>

<span data-ttu-id="0bf83-114">Os nomes de parâmetro foram alterados quanto à consistência e para evitar falhas ao usar argumentos nomeados e reflexão.</span><span class="sxs-lookup"><span data-stu-id="0bf83-114">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0bf83-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="0bf83-115">Version introduced</span></span>

<span data-ttu-id="0bf83-116">5,0 RC2</span><span class="sxs-lookup"><span data-stu-id="0bf83-116">5.0 RC2</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0bf83-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="0bf83-117">Recommended action</span></span>

<span data-ttu-id="0bf83-118">Se você encontrar um erro de compilador devido a uma alteração de nome de parâmetro, atualize o nome do parâmetro de acordo.</span><span class="sxs-lookup"><span data-stu-id="0bf83-118">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0bf83-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="0bf83-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
