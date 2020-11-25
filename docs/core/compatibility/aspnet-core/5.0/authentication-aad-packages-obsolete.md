---
title: 'Alteração significativa: autenticação: AzureAD. UI e AzureADB2C. UI APIs e pacotes marcados como obsoletos'
description: 'Saiba mais sobre a alteração significativa no ASP.NET Core 5,0 de autenticação: AzureAD. UI e AzureADB2C. UI APIs e pacotes marcados como obsoletos'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c977ba4d6e34fc5f11133bdd1446a94d54efcb63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760519"
---
# <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a><span data-ttu-id="d1306-103">Autenticação: AzureAD. UI e AzureADB2C. UI APIs e pacotes marcados como obsoletos</span><span class="sxs-lookup"><span data-stu-id="d1306-103">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>

<span data-ttu-id="d1306-104">No ASP.NET Core 2,1, a integração com o Azure Active Directory (Azure AD) e a autenticação Azure Active Directory B2C (Azure AD B2C) são fornecidas pelos pacotes [Microsoft. AspNetCore. Authentication. AzureAD. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) e [Microsoft. AspNetCore. Authentication. AzureADB2C. UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) .</span><span class="sxs-lookup"><span data-stu-id="d1306-104">In ASP.NET Core 2.1, integration with Azure Active Directory (Azure AD) and Azure Active Directory B2C (Azure AD B2C) authentication is provided by the [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) and [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI) packages.</span></span> <span data-ttu-id="d1306-105">A funcionalidade fornecida por esses pacotes é baseada no ponto de extremidade v 1.0 do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1306-105">The functionality provided by these packages is based on the Azure AD v1.0 endpoint.</span></span>

<span data-ttu-id="d1306-106">No ASP.NET Core 5,0 e posterior, a integração com o Azure AD e a autenticação Azure AD B2C é fornecida pelo pacote [Microsoft. Identity. Web](https://www.nuget.org/packages/Microsoft.Identity.Web) .</span><span class="sxs-lookup"><span data-stu-id="d1306-106">In ASP.NET Core 5.0 and later, integration with Azure AD and Azure AD B2C authentication is provided by the [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web) package.</span></span> <span data-ttu-id="d1306-107">Este pacote é baseado na plataforma de identidade da Microsoft, que é conhecida anteriormente como ponto de extremidade v 2.0 do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1306-107">This package is based on the Microsoft Identity Platform, which is formerly known as the Azure AD v2.0 endpoint.</span></span> <span data-ttu-id="d1306-108">Consequentemente, as APIs antigas nos `Microsoft.AspNetCore.Authentication.AzureAD.UI` `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` pacotes e foram preteridas.</span><span class="sxs-lookup"><span data-stu-id="d1306-108">Consequently, the old APIs in the `Microsoft.AspNetCore.Authentication.AzureAD.UI` and `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` packages were deprecated.</span></span>

<span data-ttu-id="d1306-109">Para obter uma discussão, consulte o problema do GitHub [dotnet/aspnetcore # 25807](https://github.com/dotnet/aspnetcore/issues/25807).</span><span class="sxs-lookup"><span data-stu-id="d1306-109">For discussion, see GitHub issue [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d1306-110">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="d1306-110">Version introduced</span></span>

<span data-ttu-id="d1306-111">5,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="d1306-111">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d1306-112">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="d1306-112">Old behavior</span></span>

<span data-ttu-id="d1306-113">As APIs não estavam marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="d1306-113">The APIs weren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d1306-114">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="d1306-114">New behavior</span></span>

<span data-ttu-id="d1306-115">As APIs são marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="d1306-115">The APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d1306-116">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="d1306-116">Reason for change</span></span>

<span data-ttu-id="d1306-117">A funcionalidade de autenticação do Azure AD e Azure AD B2C foi migrada para as APIs da MSAL (biblioteca de autenticação da Microsoft) fornecidas pelo `Microsoft.Identity.Web` .</span><span class="sxs-lookup"><span data-stu-id="d1306-117">The Azure AD and Azure AD B2C authentication functionality was migrated to Microsoft Authentication Library (MSAL) APIs that are provided by `Microsoft.Identity.Web`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d1306-118">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="d1306-118">Recommended action</span></span>

<span data-ttu-id="d1306-119">Siga as `Microsoft.Identity.Web` diretrizes de API para [aplicativos Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) e [APIs Web](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span><span class="sxs-lookup"><span data-stu-id="d1306-119">Follow the `Microsoft.Identity.Web` API guidance for [web apps](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) and [web APIs](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d1306-120">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d1306-120">Affected APIs</span></span>

* [<span data-ttu-id="d1306-121">Microsoft. AspNetCore. Authentication. AzureADAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="d1306-121">Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="d1306-122">Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADDefaults</span><span class="sxs-lookup"><span data-stu-id="d1306-122">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="d1306-123">Microsoft. AspNetCore. Authentication. AzureAD. UI. AzureADOptions</span><span class="sxs-lookup"><span data-stu-id="d1306-123">Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [<span data-ttu-id="d1306-124">Microsoft. AspNetCore. Authentication. AzureADB2CAuthenticationBuilderExtensions</span><span class="sxs-lookup"><span data-stu-id="d1306-124">Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [<span data-ttu-id="d1306-125">Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2CDefaults</span><span class="sxs-lookup"><span data-stu-id="d1306-125">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [<span data-ttu-id="d1306-126">Microsoft. AspNetCore. Authentication. AzureADB2C. UI. AzureADB2COptions</span><span class="sxs-lookup"><span data-stu-id="d1306-126">Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions</span></span>](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
