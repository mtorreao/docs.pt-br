---
title: 'Alteração significativa: os arquivos Directory. Packages. props são importados por padrão'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que os arquivos. props do NuGet importam automaticamente um arquivo chamado Directory. Packages. props, caso ele seja encontrado na pasta do projeto.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760367"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="ca90e-103">Os arquivos Directory. Packages. props são importados por padrão</span><span class="sxs-lookup"><span data-stu-id="ca90e-103">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="ca90e-104">Os arquivos *. props* do NuGet importam automaticamente um arquivo chamado *Directory. Packages. props* , caso ele seja encontrado na pasta do projeto ou em qualquer um de seus ancestrais.</span><span class="sxs-lookup"><span data-stu-id="ca90e-104">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ca90e-105">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ca90e-105">Version introduced</span></span>

<span data-ttu-id="ca90e-106">5.0</span><span class="sxs-lookup"><span data-stu-id="ca90e-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="ca90e-107">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="ca90e-107">Change description</span></span>

<span data-ttu-id="ca90e-108">Nas versões anteriores do .NET, você poderia ter um arquivo chamado *Directory. Packages. props* no seu arquivo de projeto e ele não seria importado automaticamente pelo arquivo *. props* do NuGet no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="ca90e-108">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="ca90e-109">A partir do .NET 5,0, tal arquivo *é* importado automaticamente se ele existir na pasta do projeto ou em qualquer um de seus ancestrais.</span><span class="sxs-lookup"><span data-stu-id="ca90e-109">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="ca90e-110">Se você tiver um arquivo com esse nome na pasta do projeto, essa importação automática poderá alterar o comportamento da compilação.</span><span class="sxs-lookup"><span data-stu-id="ca90e-110">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="ca90e-111">Por exemplo, o arquivo será importado, mas não estava antes, ou a ordem de quando for importado poderá ser alterada se você a importar especificamente.</span><span class="sxs-lookup"><span data-stu-id="ca90e-111">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ca90e-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="ca90e-112">Reason for change</span></span>

<span data-ttu-id="ca90e-113">Essa alteração foi feita para dar suporte ao [controle de versão de pacote central](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) para NuGet.</span><span class="sxs-lookup"><span data-stu-id="ca90e-113">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ca90e-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ca90e-114">Recommended action</span></span>

<span data-ttu-id="ca90e-115">Renomeie o arquivo *Directory. Packages. props* existente se ele não deve ser importado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ca90e-115">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ca90e-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ca90e-116">Affected APIs</span></span>

<span data-ttu-id="ca90e-117">N/D</span><span class="sxs-lookup"><span data-stu-id="ca90e-117">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
