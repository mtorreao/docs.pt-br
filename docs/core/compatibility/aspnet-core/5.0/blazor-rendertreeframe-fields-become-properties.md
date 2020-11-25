---
title: 'Alteração significativa: mais incrivelmente: RenderTreeFrame campos públicos ReadOnly se tornaram Propriedades'
description: 'Saiba mais sobre as alterações significativas no ASP.NET Core 5,0 intitulados mais recentes: os campos públicos RenderTreeFrame ReadOnly se tornaram Propriedades'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760315"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="2053e-103">Mais do que: RenderTreeFrame campos públicos ReadOnly se tornaram Propriedades</span><span class="sxs-lookup"><span data-stu-id="2053e-103">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="2053e-104">No ASP.NET Core 3,0 e 3,1, a <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> estrutura expôs vários `readonly public` campos, incluindo <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType> , <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> e outros.</span><span class="sxs-lookup"><span data-stu-id="2053e-104">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="2053e-105">No ASP.NET Core 5,0 RC1 e versões posteriores, todos os `readonly public` campos foram alterados para `readonly public` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2053e-105">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="2053e-106">Essa alteração não afetará muitos desenvolvedores porque:</span><span class="sxs-lookup"><span data-stu-id="2053e-106">This change won't affect many developers because:</span></span>

* <span data-ttu-id="2053e-107">Qualquer aplicativo ou biblioteca que simplesmente usa `.razor` arquivos (ou até mesmo <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> chamadas manuais) para definir seus componentes não referenciaria esse tipo diretamente.</span><span class="sxs-lookup"><span data-stu-id="2053e-107">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="2053e-108">O `RenderTreeFrame` próprio tipo é considerado um detalhe de implementação, não destinado ao uso fora da estrutura.</span><span class="sxs-lookup"><span data-stu-id="2053e-108">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="2053e-109">ASP.NET Core 3,0 e posterior inclui um analisador que emite avisos do compilador se o tipo estiver sendo usado diretamente.</span><span class="sxs-lookup"><span data-stu-id="2053e-109">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="2053e-110">Mesmo se você fizer referência `RenderTreeFrame` diretamente, essa alteração será de quebra de binário, mas não de quebra de fonte.</span><span class="sxs-lookup"><span data-stu-id="2053e-110">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="2053e-111">Ou seja, o código-fonte existente será compilado e se comportará corretamente.</span><span class="sxs-lookup"><span data-stu-id="2053e-111">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="2053e-112">Você encontrará um problema apenas se estiver compilando em uma estrutura do .NET Core 3. x e, em seguida, executando esses binários no .NET 5,0 RC1 e no Framework posterior.</span><span class="sxs-lookup"><span data-stu-id="2053e-112">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="2053e-113">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 25727](https://github.com/dotnet/aspnetcore/issues/25727).</span><span class="sxs-lookup"><span data-stu-id="2053e-113">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2053e-114">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="2053e-114">Version introduced</span></span>

<span data-ttu-id="2053e-115">RC1 5,0</span><span class="sxs-lookup"><span data-stu-id="2053e-115">5.0 RC1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="2053e-116">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="2053e-116">Old behavior</span></span>

<span data-ttu-id="2053e-117">Os membros públicos em `RenderTreeFrame` são definidos como campos.</span><span class="sxs-lookup"><span data-stu-id="2053e-117">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="2053e-118">Por exemplo, `renderTreeFrame.Sequence` e `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="2053e-118">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="2053e-119">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="2053e-119">New behavior</span></span>

<span data-ttu-id="2053e-120">Os membros públicos em `RenderTreeFrame` são definidos como propriedades com os mesmos nomes de antes.</span><span class="sxs-lookup"><span data-stu-id="2053e-120">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="2053e-121">Por exemplo, `renderTreeFrame.Sequence` e `renderTreeFrame.ElementName`.</span><span class="sxs-lookup"><span data-stu-id="2053e-121">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="2053e-122">Se o código pré-compilado mais antigo não tiver sido recompilado desde essa alteração, ele poderá lançar uma exceção semelhante a *MissingFieldException: campo não encontrado: ' Microsoft. AspNetCore. Components. RenderTree. RenderTreeFrame. FrameType '*.</span><span class="sxs-lookup"><span data-stu-id="2053e-122">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2053e-123">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="2053e-123">Reason for change</span></span>

<span data-ttu-id="2053e-124">Essa alteração foi necessária para implementar melhorias de desempenho de alto impacto na renderização de componente mais incrivelmente no ASP.NET Core 5,0.</span><span class="sxs-lookup"><span data-stu-id="2053e-124">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="2053e-125">Os mesmos níveis de segurança e encapsulamento são mantidos.</span><span class="sxs-lookup"><span data-stu-id="2053e-125">The same levels of safety and encapsulation are maintained.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2053e-126">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="2053e-126">Recommended action</span></span>

<span data-ttu-id="2053e-127">A maioria dos desenvolvedores não é afetada por essa mudança.</span><span class="sxs-lookup"><span data-stu-id="2053e-127">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="2053e-128">É mais provável que a alteração afete os autores de biblioteca e pacote, mas apenas em casos raros.</span><span class="sxs-lookup"><span data-stu-id="2053e-128">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="2053e-129">Especificamente, se você estiver desenvolvendo:</span><span class="sxs-lookup"><span data-stu-id="2053e-129">Specifically, if you're developing:</span></span>

* <span data-ttu-id="2053e-130">Um aplicativo e usar ASP.NET Core 3. x ou atualizar para o 5,0 RC1 ou posterior, você não precisa alterar seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="2053e-130">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="2053e-131">No entanto, se você depender de uma biblioteca atualizada para considerar essa alteração, precisará atualizar para uma versão mais recente dessa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2053e-131">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="2053e-132">Uma biblioteca e deseja dar suporte apenas ao ASP.NET Core 5,0 RC1 ou posterior, nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="2053e-132">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="2053e-133">Apenas verifique se o arquivo de projeto declara um `<TargetFramework>` valor de `net5.0` ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="2053e-133">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="2053e-134">Uma biblioteca e deseja dar suporte às ASP.NET Core 3. x *e* 5,0, determinar se o código lê os `RenderTreeFrame` Membros.</span><span class="sxs-lookup"><span data-stu-id="2053e-134">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="2053e-135">Por exemplo, avaliar `someRenderTreeFrame.FrameType` .</span><span class="sxs-lookup"><span data-stu-id="2053e-135">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="2053e-136">A maioria das bibliotecas não lê `RenderTreeFrame` Membros, incluindo bibliotecas que contêm `.razor` componentes.</span><span class="sxs-lookup"><span data-stu-id="2053e-136">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="2053e-137">Nesse caso, nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="2053e-137">In this case, no action is needed.</span></span>
  * <span data-ttu-id="2053e-138">No entanto, se sua biblioteca faz isso, você precisará de vários destinos para dar suporte a `netstandard2.1` e ao `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="2053e-138">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="2053e-139">Aplique as seguintes alterações no arquivo de projeto:</span><span class="sxs-lookup"><span data-stu-id="2053e-139">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="2053e-140">Substitua o `<TargetFramework>` elemento existente por `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>` .</span><span class="sxs-lookup"><span data-stu-id="2053e-140">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="2053e-141">Use uma `Microsoft.AspNetCore.Components` referência de pacote condicional para considerar as duas versões às quais você deseja dar suporte.</span><span class="sxs-lookup"><span data-stu-id="2053e-141">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="2053e-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2053e-142">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="2053e-143">Para obter mais esclarecimentos, consulte esta [diferença mostrando como @jsakamoto o já atualizou a `Toolbelt.Blazor.HeadElement` biblioteca](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span><span class="sxs-lookup"><span data-stu-id="2053e-143">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2053e-144">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="2053e-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
