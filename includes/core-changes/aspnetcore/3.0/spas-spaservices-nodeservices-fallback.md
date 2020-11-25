---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032314"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="f53e4-101">SPAs: SpaServices e Nodeservices não retornam mais para o agente do console</span><span class="sxs-lookup"><span data-stu-id="f53e4-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="f53e4-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> e <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> não exibirá os logs do console, a menos que o log esteja configurado.</span><span class="sxs-lookup"><span data-stu-id="f53e4-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f53e4-103">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="f53e4-103">Version introduced</span></span>

<span data-ttu-id="f53e4-104">3.0</span><span class="sxs-lookup"><span data-stu-id="f53e4-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f53e4-105">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="f53e4-105">Old behavior</span></span>

<span data-ttu-id="f53e4-106">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` usado para criar automaticamente um agente de log do console quando o registro não estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="f53e4-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f53e4-107">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="f53e4-107">New behavior</span></span>

<span data-ttu-id="f53e4-108">`Microsoft.AspNetCore.SpaServices` e `Microsoft.AspNetCore.NodeServices` não exibirá os logs do console, a menos que o log esteja configurado.</span><span class="sxs-lookup"><span data-stu-id="f53e4-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f53e4-109">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="f53e4-109">Reason for change</span></span>

<span data-ttu-id="f53e4-110">Há a necessidade de se alinhar com o modo como outros pacotes de ASP.NET Core implementam o registro em log.</span><span class="sxs-lookup"><span data-stu-id="f53e4-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f53e4-111">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="f53e4-111">Recommended action</span></span>

<span data-ttu-id="f53e4-112">Se o comportamento antigo for necessário, para configurar o log do console, adicione `services.AddLogging(builder => builder.AddConsole())` ao seu `Setup.ConfigureServices` método.</span><span class="sxs-lookup"><span data-stu-id="f53e4-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="f53e4-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="f53e4-113">Category</span></span>

<span data-ttu-id="f53e4-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f53e4-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f53e4-115">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="f53e4-115">Affected APIs</span></span>

<span data-ttu-id="f53e4-116">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f53e4-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
