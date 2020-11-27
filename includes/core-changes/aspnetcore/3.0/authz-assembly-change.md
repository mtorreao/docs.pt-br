---
ms.openlocfilehash: 2819fb3857fa6d40a2b2e42eeaec2d9c6e50eef0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96299347"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="8069d-101">Autorização: sobrecarga de addautoria movida para um assembly diferente</span><span class="sxs-lookup"><span data-stu-id="8069d-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="8069d-102">Os `AddAuthorization` métodos principais que costumava residir em `Microsoft.AspNetCore.Authorization` foram renomeados para `AddAuthorizationCore` .</span><span class="sxs-lookup"><span data-stu-id="8069d-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="8069d-103">Os `AddAuthorization` métodos antigos ainda existem, mas estão no `Microsoft.AspNetCore.Authorization.Policy` assembly em vez disso.</span><span class="sxs-lookup"><span data-stu-id="8069d-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="8069d-104">Os aplicativos que usam os dois métodos não devem ter nenhum impacto.</span><span class="sxs-lookup"><span data-stu-id="8069d-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="8069d-105">Observe que `Microsoft.AspNetCore.Authorization.Policy` agora é fornecido na estrutura compartilhada, em vez de um pacote autônomo, conforme discutido em [estrutura compartilhada: assemblies removidos do Microsoft. AspNetCore. app](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="8069d-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8069d-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="8069d-106">Version introduced</span></span>

<span data-ttu-id="8069d-107">3.0</span><span class="sxs-lookup"><span data-stu-id="8069d-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8069d-108">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="8069d-108">Old behavior</span></span>

<span data-ttu-id="8069d-109">`AddAuthorization` os métodos existiam no `Microsoft.AspNetCore.Authorization` .</span><span class="sxs-lookup"><span data-stu-id="8069d-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8069d-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="8069d-110">New behavior</span></span>

<span data-ttu-id="8069d-111">`AddAuthorization` Existem métodos no `Microsoft.AspNetCore.Authorization.Policy` .</span><span class="sxs-lookup"><span data-stu-id="8069d-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="8069d-112">`AddAuthorizationCore` é o novo nome para os métodos antigos.</span><span class="sxs-lookup"><span data-stu-id="8069d-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8069d-113">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="8069d-113">Reason for change</span></span>

<span data-ttu-id="8069d-114">`AddAuthorization` é um nome de método melhor para adicionar todos os serviços comuns necessários para autorização.</span><span class="sxs-lookup"><span data-stu-id="8069d-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8069d-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="8069d-115">Recommended action</span></span>

<span data-ttu-id="8069d-116">`Microsoft.AspNetCore.Authorization.Policy`Em vez disso, adicione uma referência a ou use `AddAuthorizationCore` .</span><span class="sxs-lookup"><span data-stu-id="8069d-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="8069d-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="8069d-117">Category</span></span>

<span data-ttu-id="8069d-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8069d-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8069d-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="8069d-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
