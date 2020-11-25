---
title: 'Alteração significativa: alteração de comportamento de PublishDepsFilePath'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que a Propriedade MSBuild do PublishDepsFilePath está vazia para aplicativos de arquivo único.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760550"
---
# <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="5eb40-103">Alteração de comportamento de PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="5eb40-103">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="5eb40-104">A `PublishDepsFilePath` Propriedade MSBuild está vazia para aplicativos de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="5eb40-104">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="5eb40-105">Além disso, para aplicativos que não são de arquivo único, o *deps.jsno* arquivo pode não ser copiado para o diretório de saída até mais tarde na compilação.</span><span class="sxs-lookup"><span data-stu-id="5eb40-105">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5eb40-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="5eb40-106">Version introduced</span></span>

<span data-ttu-id="5eb40-107">5.0</span><span class="sxs-lookup"><span data-stu-id="5eb40-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="5eb40-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="5eb40-108">Change description</span></span>

<span data-ttu-id="5eb40-109">Nas versões anteriores do .NET, a `PublishDepsFilePath` Propriedade MSBuild é o caminho para a *deps.js* do aplicativo no arquivo no diretório de saída para aplicativos que não são de arquivo único e um caminho no diretório intermediário para aplicativos de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="5eb40-109">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="5eb40-110">A partir do .NET 5,0, `PublishDepsFilePath` está vazio para aplicativos de arquivo único e uma nova `IntermediateDepsFilePath` propriedade especifica o *deps.jsno* local no diretório intermediário.</span><span class="sxs-lookup"><span data-stu-id="5eb40-110">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="5eb40-111">Além disso, para aplicativos que não são de arquivo único, o *deps.jsno* arquivo pode não ser copiado para o diretório de saída (ou seja, o caminho especificado por `PublishDepsFilePath` ) até mais tarde na compilação.</span><span class="sxs-lookup"><span data-stu-id="5eb40-111">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5eb40-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="5eb40-112">Reason for change</span></span>

<span data-ttu-id="5eb40-113">Essa alteração foi feita por alguns motivos:</span><span class="sxs-lookup"><span data-stu-id="5eb40-113">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="5eb40-114">Devido a uma refatoração da lógica de publicação a fim de dar suporte a [aplicativos de arquivo único aprimorados](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) no .NET 5.</span><span class="sxs-lookup"><span data-stu-id="5eb40-114">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="5eb40-115">Em aplicativos de arquivo único, para ajudar a proteger contra destinos que tentam regravar o *deps.jsno* arquivo depois que *deps.jsno* já foi agrupado, portanto, sem afetar o aplicativo silenciosamente.</span><span class="sxs-lookup"><span data-stu-id="5eb40-115">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="5eb40-116">Por esse motivo, o `PublishDepsFilePath` está vazio para aplicativos de arquivo único.</span><span class="sxs-lookup"><span data-stu-id="5eb40-116">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5eb40-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="5eb40-117">Recommended action</span></span>

<span data-ttu-id="5eb40-118">Os destinos que reescrevem o *deps.jsno* arquivo geralmente devem fazer isso usando a `IntermediateDepsFilePath` propriedade.</span><span class="sxs-lookup"><span data-stu-id="5eb40-118">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5eb40-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="5eb40-119">Affected APIs</span></span>

<span data-ttu-id="5eb40-120">N/D</span><span class="sxs-lookup"><span data-stu-id="5eb40-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
