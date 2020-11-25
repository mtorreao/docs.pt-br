---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032247"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="67d1c-101">Identidade: sobrecarga do método AddDefaultUI removida</span><span class="sxs-lookup"><span data-stu-id="67d1c-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="67d1c-102">A partir do ASP.NET Core 3,0, a sobrecarga do método [IdentityBuilderUIExtensions. AddDefaultUI (IdentityBuilder, UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) não existe mais.</span><span class="sxs-lookup"><span data-stu-id="67d1c-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="67d1c-103">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="67d1c-103">Version introduced</span></span>

<span data-ttu-id="67d1c-104">3.0</span><span class="sxs-lookup"><span data-stu-id="67d1c-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="67d1c-105">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="67d1c-105">Reason for change</span></span>

<span data-ttu-id="67d1c-106">Essa alteração foi resultado da adoção do recurso de ativos da Web estáticos.</span><span class="sxs-lookup"><span data-stu-id="67d1c-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="67d1c-107">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="67d1c-107">Recommended action</span></span>

<span data-ttu-id="67d1c-108">Chame <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> em vez da sobrecarga que usa dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="67d1c-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="67d1c-109">Se você estiver usando a inicialização 3, adicione também a seguinte linha a um `<PropertyGroup>` elemento em seu arquivo de projeto:</span><span class="sxs-lookup"><span data-stu-id="67d1c-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="67d1c-110">Categoria</span><span class="sxs-lookup"><span data-stu-id="67d1c-110">Category</span></span>

<span data-ttu-id="67d1c-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="67d1c-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67d1c-112">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="67d1c-112">Affected APIs</span></span>

[<span data-ttu-id="67d1c-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="67d1c-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
