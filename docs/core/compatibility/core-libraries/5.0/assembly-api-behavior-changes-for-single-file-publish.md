---
title: 'Alteração significativa: alterações de comportamento da API relacionadas ao assembly para o formato de publicação de arquivo único'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que várias APIs relacionadas ao local do arquivo de um assembly têm alterações de comportamento quando são invocadas em um formato de publicação de arquivo único.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760402"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="51f01-103">Alterações de comportamento da API relacionadas ao assembly para o formato de publicação de arquivo único</span><span class="sxs-lookup"><span data-stu-id="51f01-103">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="51f01-104">Várias APIs relacionadas ao local do arquivo de um assembly têm alterações de comportamento quando são invocadas em um formato de publicação de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="51f01-104">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

## <a name="change-description"></a><span data-ttu-id="51f01-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="51f01-105">Change description</span></span>

<span data-ttu-id="51f01-106">Na publicação de arquivo único para .NET 5,0 e versões posteriores, os assemblies agrupados são carregados da memória, em vez de serem extraídos em disco.</span><span class="sxs-lookup"><span data-stu-id="51f01-106">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="51f01-107">Para aplicativos publicados de arquivo único, isso significa que determinadas APIs relacionadas ao local retornam valores diferentes no .NET 5,0 e posteriores do que nas versões anteriores do .NET.</span><span class="sxs-lookup"><span data-stu-id="51f01-107">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="51f01-108">As alterações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="51f01-108">The changes are as follows:</span></span>

| <span data-ttu-id="51f01-109">API</span><span class="sxs-lookup"><span data-stu-id="51f01-109">API</span></span> | <span data-ttu-id="51f01-110">Versões anteriores</span><span class="sxs-lookup"><span data-stu-id="51f01-110">Previous versions</span></span> | <span data-ttu-id="51f01-111">.NET 5,0 e posterior</span><span class="sxs-lookup"><span data-stu-id="51f01-111">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="51f01-112">Retorna o caminho do arquivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="51f01-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="51f01-113">Retorna uma cadeia de caracteres vazia para assemblies agrupados</span><span class="sxs-lookup"><span data-stu-id="51f01-113">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="51f01-114">Retorna o caminho do arquivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="51f01-114">Returns extracted DLL file path</span></span> | <span data-ttu-id="51f01-115">Gera uma exceção para assemblies agrupados</span><span class="sxs-lookup"><span data-stu-id="51f01-115">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="51f01-116">Retorna `null` para assemblies agrupados</span><span class="sxs-lookup"><span data-stu-id="51f01-116">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="51f01-117">Gera uma exceção para assemblies agrupados</span><span class="sxs-lookup"><span data-stu-id="51f01-117">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="51f01-118">Valor é o nome da DLL do ponto de entrada</span><span class="sxs-lookup"><span data-stu-id="51f01-118">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="51f01-119">Value é o nome do executável do host</span><span class="sxs-lookup"><span data-stu-id="51f01-119">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="51f01-120">O valor é o diretório de extração temporário</span><span class="sxs-lookup"><span data-stu-id="51f01-120">Value is the temporary extraction directory</span></span> | <span data-ttu-id="51f01-121">O valor é o diretório recipiente do executável do host</span><span class="sxs-lookup"><span data-stu-id="51f01-121">Value is the containing directory of the host executable</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="51f01-122">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="51f01-122">Version introduced</span></span>

<span data-ttu-id="51f01-123">5.0</span><span class="sxs-lookup"><span data-stu-id="51f01-123">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="51f01-124">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="51f01-124">Recommended action</span></span>

<span data-ttu-id="51f01-125">Evite dependências no local do arquivo de assemblies ao publicar como um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="51f01-125">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="51f01-126">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="51f01-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
