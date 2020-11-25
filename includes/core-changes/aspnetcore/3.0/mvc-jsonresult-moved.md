---
ms.openlocfilehash: 96c2a32dd7cca91e965601d715bbd4625bba439a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032298"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="d7456-101">MVC: JsonResult movido para Microsoft. AspNetCore. Mvc. Core</span><span class="sxs-lookup"><span data-stu-id="d7456-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="d7456-102">`JsonResult` foi movido para o `Microsoft.AspNetCore.Mvc.Core` assembly.</span><span class="sxs-lookup"><span data-stu-id="d7456-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="d7456-103">Esse tipo costumava ser definido no [Microsoft.AspNetCore.Mvc.Formatters.Jsem](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span><span class="sxs-lookup"><span data-stu-id="d7456-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="d7456-104">Um atributo de nível de assembly [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) foi adicionado ao `Microsoft.AspNetCore.Mvc.Formatters.Json` para resolver esse problema para a maioria dos usuários.</span><span class="sxs-lookup"><span data-stu-id="d7456-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="d7456-105">Aplicativos que usam bibliotecas de terceiros podem encontrar problemas.</span><span class="sxs-lookup"><span data-stu-id="d7456-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d7456-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="d7456-106">Version introduced</span></span>

<span data-ttu-id="d7456-107">3,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="d7456-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d7456-108">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="d7456-108">Old behavior</span></span>

<span data-ttu-id="d7456-109">Um aplicativo que usa uma biblioteca baseada em 2,2 é compilado com êxito.</span><span class="sxs-lookup"><span data-stu-id="d7456-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d7456-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="d7456-110">New behavior</span></span>

<span data-ttu-id="d7456-111">Um aplicativo que usa uma biblioteca com base em 2,2 falha na compilação.</span><span class="sxs-lookup"><span data-stu-id="d7456-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="d7456-112">Um erro contendo uma variação do texto a seguir é fornecido:</span><span class="sxs-lookup"><span data-stu-id="d7456-112">An error containing a variation of the following text is provided:</span></span>

```output
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="d7456-113">Para obter um exemplo desse problema, consulte [dotnet/aspnetcore # 7220](https://github.com/dotnet/aspnetcore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="d7456-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d7456-114">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="d7456-114">Reason for change</span></span>

<span data-ttu-id="d7456-115">Alterações no nível da plataforma para a composição de ASP.NET Core conforme descrito em [ASPNET/comunicados # 325](https://github.com/aspnet/Announcements/issues/325).</span><span class="sxs-lookup"><span data-stu-id="d7456-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d7456-116">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="d7456-116">Recommended action</span></span>

<span data-ttu-id="d7456-117">Bibliotecas compiladas com base na versão 2,2 do `Microsoft.AspNetCore.Mvc.Formatters.Json` talvez precisem ser recompiladas para resolver o problema de todos os consumidores.</span><span class="sxs-lookup"><span data-stu-id="d7456-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="d7456-118">Se for afetado, contate o autor da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="d7456-118">If affected, contact the library author.</span></span> <span data-ttu-id="d7456-119">Solicite a recompilação da biblioteca para o destino ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="d7456-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="d7456-120">Categoria</span><span class="sxs-lookup"><span data-stu-id="d7456-120">Category</span></span>

<span data-ttu-id="d7456-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d7456-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7456-122">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d7456-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
