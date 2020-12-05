---
title: 'Alteração significativa: atributos OSPlatform renomeados ou removidos'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que os atributos da plataforma do sistema operacional que foram introduzidos em uma versão de visualização foram removidos ou renomeados.
ms.date: 11/01/2020
ms.openlocfilehash: be2ddd4909bef70f531ca48246f091923d6435ec
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739484"
---
# <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="20d46-103">Atributos OSPlatform renomeados ou removidos</span><span class="sxs-lookup"><span data-stu-id="20d46-103">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="20d46-104">Os seguintes atributos apresentados no .NET 5,0 Preview 8 foram removidos ou renomeados: `MinimumOSPlatformAttribute` , `RemovedInOSPlatformAttribute` e `ObsoletedInOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="20d46-104">The following attributes that were introduced in .NET 5.0 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

## <a name="change-description"></a><span data-ttu-id="20d46-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="20d46-105">Change description</span></span>

<span data-ttu-id="20d46-106">O .NET 5,0 Preview 8 introduziu os seguintes atributos no <xref:System.Runtime.Versioning> namespace:</span><span class="sxs-lookup"><span data-stu-id="20d46-106">.NET 5.0 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="20d46-107">No .NET 5,0 Preview 8, quando um projeto tem como alvo um tipo específico de sistema operacional do .NET 5 usando um [moniker de estrutura de destino](../../../../standard/frameworks.md) como `net5.0-windows` , o Build adiciona um atributo de nível de assembly `System.Runtime.Versioning.MinimumOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="20d46-107">In .NET 5.0 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="20d46-108">No .NET 5,0 RC1, o `ObsoletedInOSPlatformAttribute` foi removido e `MinimumOSPlatformAttribute` e `RemovedInOSPlatformAttribute` foi renomeado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="20d46-108">In .NET 5.0 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="20d46-109">Nome da visualização 8</span><span class="sxs-lookup"><span data-stu-id="20d46-109">Preview 8 name</span></span> | <span data-ttu-id="20d46-110">RC1 e nome posterior</span><span class="sxs-lookup"><span data-stu-id="20d46-110">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="20d46-111">No .NET 5,0 RC1 e posterior, quando um projeto tem como alvo um tipo específico de sistema operacional do .NET 5 usando um [moniker de estrutura de destino](../../../../standard/frameworks.md) como `net5.0-windows` , o Build adiciona um atributo de nível de assembly <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="20d46-111">In .NET 5.0 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="20d46-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="20d46-112">Reason for change</span></span>

<span data-ttu-id="20d46-113">O .NET 5,0 Preview 8 introduziu atributos no <xref:System.Runtime.Versioning> para especificar plataformas com suporte para APIs.</span><span class="sxs-lookup"><span data-stu-id="20d46-113">.NET 5.0 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="20d46-114">Os atributos são consumidos pelo [analisador de compatibilidade de plataforma](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) para produzir avisos de compilação quando APIs específicas da plataforma são consumidas em plataformas que não dão suporte a essas APIs.</span><span class="sxs-lookup"><span data-stu-id="20d46-114">The attributes are consumed by the [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) to produce build warnings when platform-specific APIs are consumed on platforms that don't support those APIs.</span></span>

<span data-ttu-id="20d46-115">Para o .NET 5,0 RC1, um recurso adicional foi adicionado ao analisador de compatibilidade de plataforma para exclusão de plataforma.</span><span class="sxs-lookup"><span data-stu-id="20d46-115">For .NET 5.0 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="20d46-116">O recurso permite que as APIs sejam marcadas como totalmente sem suporte em plataformas de sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="20d46-116">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="20d46-117">Esse recurso solicitou alterações nos atributos, incluindo o uso de nomes mais adequados.</span><span class="sxs-lookup"><span data-stu-id="20d46-117">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="20d46-118">O `ObsoletedInOSPlatformAttribute` foi removido porque não era mais necessário.</span><span class="sxs-lookup"><span data-stu-id="20d46-118">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="20d46-119">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="20d46-119">Version introduced</span></span>

<span data-ttu-id="20d46-120">RC1 5,0</span><span class="sxs-lookup"><span data-stu-id="20d46-120">5.0 RC1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="20d46-121">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="20d46-121">Recommended action</span></span>

<span data-ttu-id="20d46-122">Ao redirecionar seu projeto do .NET 5,0 Preview 8 para o .NET 5,0 RC1, você poderá encontrar erros de compilação ou tempo de execução devido a essas alterações.</span><span class="sxs-lookup"><span data-stu-id="20d46-122">When you retarget your project from .NET 5.0 Preview 8 to .NET 5.0 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="20d46-123">Por exemplo, a renomeação do `MinimumOSPlatformAttribute` provavelmente produzirá erros, porque o atributo é aplicado a assemblies específicos da plataforma no momento da compilação, e os artefatos de Build antigos ainda referenciarão o antigo nome da API.</span><span class="sxs-lookup"><span data-stu-id="20d46-123">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="20d46-124">Exemplos de erros de tempo de compilação:</span><span class="sxs-lookup"><span data-stu-id="20d46-124">Example build-time errors:</span></span>

- <span data-ttu-id="20d46-125">**erro CS0246: não foi possível encontrar o nome do namespace ou tipo ' MinimumOSPlatformAttribute ' (está faltando uma diretiva using ou uma referência de assembly?)**</span><span class="sxs-lookup"><span data-stu-id="20d46-125">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="20d46-126">**erro CS0246: não foi possível encontrar o nome do namespace ou tipo ' RemovedInOSPlatformAttribute ' (está faltando uma diretiva using ou uma referência de assembly?)**</span><span class="sxs-lookup"><span data-stu-id="20d46-126">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="20d46-127">**erro CS0246: não foi possível encontrar o nome do namespace ou tipo ' ObsoletedInOSPlatformAttribute ' (está faltando uma diretiva using ou uma referência de assembly?)**</span><span class="sxs-lookup"><span data-stu-id="20d46-127">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="20d46-128">Erro de tempo de execução de exemplo:</span><span class="sxs-lookup"><span data-stu-id="20d46-128">Example run-time error:</span></span>

<span data-ttu-id="20d46-129">**Exceção sem tratamento. System. TypeLoadException: não foi possível carregar o tipo ' System. Runtime. Versioning. MinimumOSPlatformAttribute ' do assembly ' System. Runtime, versão = 5.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a '.**</span><span class="sxs-lookup"><span data-stu-id="20d46-129">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="20d46-130">Para resolver esses erros:</span><span class="sxs-lookup"><span data-stu-id="20d46-130">To resolve these errors:</span></span>

- <span data-ttu-id="20d46-131">Atualize todas as referências de `MinimumOSPlatformAttribute` para <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="20d46-131">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="20d46-132">Atualize todas as referências de `RemovedInOSPlatformAttribute` para <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> .</span><span class="sxs-lookup"><span data-stu-id="20d46-132">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="20d46-133">Remova todas as referências a `ObsoletedInOSPlatformAttribute` .</span><span class="sxs-lookup"><span data-stu-id="20d46-133">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="20d46-134">Recompile o projeto (ou execute limpar + Build) para excluir os artefatos de Build antigos.</span><span class="sxs-lookup"><span data-stu-id="20d46-134">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="20d46-135">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="20d46-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
