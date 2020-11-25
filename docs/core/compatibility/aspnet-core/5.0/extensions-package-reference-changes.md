---
title: 'Alteração significativa: extensões: alterações de referência de pacote que afetam alguns pacotes NuGet'
description: 'Saiba mais sobre a alteração significativa em extensões com título ASP.NET Core 5,0: alterações de referência de pacote que afetam alguns pacotes NuGet'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760375"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a><span data-ttu-id="a5c33-103">Extensões: alterações de referência de pacote que afetam alguns pacotes NuGet</span><span class="sxs-lookup"><span data-stu-id="a5c33-103">Extensions: Package reference changes affecting some NuGet packages</span></span>

<span data-ttu-id="a5c33-104">Com a migração de alguns `Microsoft.Extensions.*` pacotes NuGet do repositório [dotnet/extensões](https://github.com/dotnet/extensions) para [dotnet/tempo de execução](https://github.com/dotnet/runtime), conforme descrito em [ASPNET/comunicados # 411](https://github.com/aspnet/Announcements/issues/411), as alterações de empacotamento estão sendo aplicadas a alguns dos pacotes migrados.</span><span class="sxs-lookup"><span data-stu-id="a5c33-104">With the migration of some `Microsoft.Extensions.*` NuGet packages from the [dotnet/extensions](https://github.com/dotnet/extensions) repository to [dotnet/runtime](https://github.com/dotnet/runtime), as described in [aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411), packaging changes are being applied to some of the migrated packages.</span></span> <span data-ttu-id="a5c33-105">Para obter uma discussão sobre esse problema, consulte [dotnet/aspnetcore # 21033](https://github.com/dotnet/aspnetcore/issues/21033).</span><span class="sxs-lookup"><span data-stu-id="a5c33-105">For discussion on this issue, see [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a5c33-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="a5c33-106">Version introduced</span></span>

<span data-ttu-id="a5c33-107">5,0 versão prévia 4</span><span class="sxs-lookup"><span data-stu-id="a5c33-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a5c33-108">Comportamento antigo</span><span class="sxs-lookup"><span data-stu-id="a5c33-108">Old behavior</span></span>

<span data-ttu-id="a5c33-109">Alguns `Microsoft.Extensions.*` pacotes incluíram referências de pacote para APIs nas quais seu aplicativo dependa.</span><span class="sxs-lookup"><span data-stu-id="a5c33-109">Some `Microsoft.Extensions.*` packages included package references for APIs on which your app relied.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="a5c33-110">Novo comportamento</span><span class="sxs-lookup"><span data-stu-id="a5c33-110">New behavior</span></span>

<span data-ttu-id="a5c33-111">Seu aplicativo pode ter que adicionar `Microsoft.Extensions.*` dependências de pacote.</span><span class="sxs-lookup"><span data-stu-id="a5c33-111">Your app may have to add `Microsoft.Extensions.*` package dependencies.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a5c33-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="a5c33-112">Reason for change</span></span>

<span data-ttu-id="a5c33-113">As políticas de empacotamento foram atualizadas para se alinharem melhor ao repositório *dotnet/tempo de execução* .</span><span class="sxs-lookup"><span data-stu-id="a5c33-113">Packaging policies were updated to better align with the *dotnet/runtime* repository.</span></span> <span data-ttu-id="a5c33-114">Na nova política, as referências de pacote não utilizadas são removidas dos arquivos *. nupkg* durante o empacotamento.</span><span class="sxs-lookup"><span data-stu-id="a5c33-114">Under the new policy, unused package references are removed from *.nupkg* files during packaging.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a5c33-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="a5c33-115">Recommended action</span></span>

<span data-ttu-id="a5c33-116">Os consumidores dos pacotes afetados devem adicionar uma dependência direta da dependência do pacote removido em seu projeto se as APIs da dependência de pacote removido forem usadas.</span><span class="sxs-lookup"><span data-stu-id="a5c33-116">Consumers of the affected packages should add a direct dependency on the removed package dependency in their project if APIs from removed package dependency are used.</span></span> <span data-ttu-id="a5c33-117">A tabela a seguir lista os pacotes afetados e as alterações correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a5c33-117">The following table lists the affected packages and the corresponding changes.</span></span>

|<span data-ttu-id="a5c33-118">Nome do pacote</span><span class="sxs-lookup"><span data-stu-id="a5c33-118">Package name</span></span>|<span data-ttu-id="a5c33-119">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="a5c33-119">Change description</span></span>|
|------------|------------------|
|[<span data-ttu-id="a5c33-120">Microsoft.Extensions.Configuração. Associador</span><span class="sxs-lookup"><span data-stu-id="a5c33-120">Microsoft.Extensions.Configuration.Binder</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|<span data-ttu-id="a5c33-121">Referência removida para `Microsoft.Extensions.Configuration`</span><span class="sxs-lookup"><span data-stu-id="a5c33-121">Removed reference to `Microsoft.Extensions.Configuration`</span></span>|
|[<span data-ttu-id="a5c33-122">Microsoft.Extensions.Configuration.Jsem</span><span class="sxs-lookup"><span data-stu-id="a5c33-122">Microsoft.Extensions.Configuration.Json</span></span>](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |<span data-ttu-id="a5c33-123">Referência removida para `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="a5c33-123">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="a5c33-124">Microsoft. Extensions. Hosting. abstrações</span><span class="sxs-lookup"><span data-stu-id="a5c33-124">Microsoft.Extensions.Hosting.Abstractions</span></span>](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|<span data-ttu-id="a5c33-125">Referência removida para `Microsoft.Extensions.Logging.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="a5c33-125">Removed reference to `Microsoft.Extensions.Logging.Abstractions`</span></span>|
|[<span data-ttu-id="a5c33-126">Microsoft.Extensions.Logging</span><span class="sxs-lookup"><span data-stu-id="a5c33-126">Microsoft.Extensions.Logging</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |<span data-ttu-id="a5c33-127">Referência removida para `Microsoft.Extensions.Configuration.Binder`</span><span class="sxs-lookup"><span data-stu-id="a5c33-127">Removed reference to `Microsoft.Extensions.Configuration.Binder`</span></span>|
|[<span data-ttu-id="a5c33-128">Microsoft. Extensions. Logging. console</span><span class="sxs-lookup"><span data-stu-id="a5c33-128">Microsoft.Extensions.Logging.Console</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |<span data-ttu-id="a5c33-129">Referência removida para `Microsoft.Extensions.Configuration.Abstractions`</span><span class="sxs-lookup"><span data-stu-id="a5c33-129">Removed reference to `Microsoft.Extensions.Configuration.Abstractions`</span></span>|
|[<span data-ttu-id="a5c33-130">Microsoft. Extensions. Logging. EventLog</span><span class="sxs-lookup"><span data-stu-id="a5c33-130">Microsoft.Extensions.Logging.EventLog</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |<span data-ttu-id="a5c33-131">Referência removida para `System.Diagnostics.EventLog` para o .NET Framework moniker da estrutura de destino do 4.6.1</span><span class="sxs-lookup"><span data-stu-id="a5c33-131">Removed reference to `System.Diagnostics.EventLog` for the .NET Framework 4.6.1 target framework moniker</span></span>|
|[<span data-ttu-id="a5c33-132">Microsoft. Extensions. Logging. EventSource</span><span class="sxs-lookup"><span data-stu-id="a5c33-132">Microsoft.Extensions.Logging.EventSource</span></span>](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |<span data-ttu-id="a5c33-133">Referência removida para `System.Threading.Tasks.Extensions`</span><span class="sxs-lookup"><span data-stu-id="a5c33-133">Removed reference to `System.Threading.Tasks.Extensions`</span></span>|
|[<span data-ttu-id="a5c33-134">Microsoft. Extensions. opções</span><span class="sxs-lookup"><span data-stu-id="a5c33-134">Microsoft.Extensions.Options</span></span>](https://nuget.org/packages/Microsoft.Extensions.Options)                          |<span data-ttu-id="a5c33-135">Referência removida para `System.ComponentModel.Annotations`</span><span class="sxs-lookup"><span data-stu-id="a5c33-135">Removed reference to `System.ComponentModel.Annotations`</span></span>|

<span data-ttu-id="a5c33-136">Por exemplo, a referência de pacote a `Microsoft.Extensions.Configuration` foi removida do `Microsoft.Extensions.Configuration.Binder` .</span><span class="sxs-lookup"><span data-stu-id="a5c33-136">For example, the package reference to `Microsoft.Extensions.Configuration` was removed from `Microsoft.Extensions.Configuration.Binder`.</span></span> <span data-ttu-id="a5c33-137">Nenhuma API da dependência foi usada no pacote.</span><span class="sxs-lookup"><span data-stu-id="a5c33-137">No API from the dependency was used in the package.</span></span> <span data-ttu-id="a5c33-138">Os usuários de `Microsoft.Extensions.Configuration.Binder` quem dependem de APIs `Microsoft.Extensions.Configuration` devem adicionar uma referência direta a ele em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="a5c33-138">Users of `Microsoft.Extensions.Configuration.Binder` who depend on APIs from `Microsoft.Extensions.Configuration` should add a direct reference to it in their project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a5c33-139">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="a5c33-139">Affected APIs</span></span>

<span data-ttu-id="a5c33-140">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5c33-140">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
