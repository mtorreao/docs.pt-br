---
title: 'Alteração significativa: IIS: as cadeias de consulta de middleware UrlRewrite são preservadas'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 intitulado IIS: cadeias de consulta de middleware UrlRewrite são preservadas'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760312"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="6017e-103">IIS: cadeias de consulta de middleware UrlRewrite são preservadas</span><span class="sxs-lookup"><span data-stu-id="6017e-103">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="6017e-104">Um defeito de middleware UrlRewrite do IIS impediu que a cadeia de caracteres de consulta fosse preservada nas regras de regravação.</span><span class="sxs-lookup"><span data-stu-id="6017e-104">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="6017e-105">Esse defeito foi corrigido para manter a consistência com o comportamento do módulo UrlRewrite do IIS.</span><span class="sxs-lookup"><span data-stu-id="6017e-105">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="6017e-106">Para obter uma discussão, veja Issue [dotnet/aspnetcore # 22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="6017e-106">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6017e-107">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="6017e-107">Version introduced</span></span>

<span data-ttu-id="6017e-108">ASP.NET Core 5,0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="6017e-108">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6017e-109">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="6017e-109">Old behavior</span></span>

<span data-ttu-id="6017e-110">Considere a seguinte regra de reescrita:</span><span class="sxs-lookup"><span data-stu-id="6017e-110">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="6017e-111">A regra anterior não acrescenta a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="6017e-111">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="6017e-112">Um URI como `/about?id=1` redireciona para `/contact` em vez de `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="6017e-112">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="6017e-113">O `appendQueryString` atributo `true` também usa como padrão.</span><span class="sxs-lookup"><span data-stu-id="6017e-113">The `appendQueryString` attribute defaults to `true` as well.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6017e-114">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="6017e-114">New behavior</span></span>

<span data-ttu-id="6017e-115">A cadeia de caracteres de consulta é preservada.</span><span class="sxs-lookup"><span data-stu-id="6017e-115">The query string is preserved.</span></span> <span data-ttu-id="6017e-116">O URI do exemplo no [comportamento antigo](#old-behavior) seria `/contact?id=1` .</span><span class="sxs-lookup"><span data-stu-id="6017e-116">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6017e-117">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="6017e-117">Reason for change</span></span>

<span data-ttu-id="6017e-118">O comportamento antigo não correspondia ao comportamento do módulo UrlRewrite do IIS.</span><span class="sxs-lookup"><span data-stu-id="6017e-118">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="6017e-119">Para dar suporte à portabilidade entre o middleware e o módulo, o objetivo é manter comportamentos consistentes.</span><span class="sxs-lookup"><span data-stu-id="6017e-119">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6017e-120">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="6017e-120">Recommended action</span></span>

<span data-ttu-id="6017e-121">Se o comportamento de remover a cadeia de caracteres de consulta for preferencial, defina o `action` elemento como `appendQueryString="false"` .</span><span class="sxs-lookup"><span data-stu-id="6017e-121">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6017e-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="6017e-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
