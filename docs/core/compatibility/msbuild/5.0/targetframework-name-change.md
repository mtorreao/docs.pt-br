---
title: 'Alteração significativa: TargetFramework alterar de netcoreapp para net'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que o valor da propriedade TargetFramework do MSBuild mudou de netcoreapp 3.1 para NET 5.0.
ms.date: 10/17/2020
ms.openlocfilehash: c3b39a36548d58d6ed75fd8b1c84b0cccfc738f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760363"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="6f95b-103">TargetFramework alterar de netcoreapp para net</span><span class="sxs-lookup"><span data-stu-id="6f95b-103">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="6f95b-104">O valor da Propriedade MSBuild `TargetFramework` foi alterado de `netcoreapp3.1` para `net5.0` .</span><span class="sxs-lookup"><span data-stu-id="6f95b-104">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="6f95b-105">Isso pode interromper o código que depende da análise do valor de `TargetFramework` .</span><span class="sxs-lookup"><span data-stu-id="6f95b-105">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6f95b-106">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="6f95b-106">Version introduced</span></span>

<span data-ttu-id="6f95b-107">5.0</span><span class="sxs-lookup"><span data-stu-id="6f95b-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="6f95b-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="6f95b-108">Change description</span></span>

<span data-ttu-id="6f95b-109">No .NET Core 1,0-3,1, o valor da Propriedade MSBuild `TargetFramework` começa com `netcoreapp` , por exemplo, `netcoreapp3.1` para aplicativos direcionados ao .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="6f95b-109">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="6f95b-110">A partir do .NET 5,0, esse valor é simplificado apenas para começar `net` , por exemplo, `net5.0` para o .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="6f95b-110">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="6f95b-111">Para obter mais informações, consulte [o futuro de .net Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) e [nomes de estrutura de destino no .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="6f95b-111">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6f95b-112">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="6f95b-112">Reason for change</span></span>

- <span data-ttu-id="6f95b-113">Simplifica o `TargetFramework` valor.</span><span class="sxs-lookup"><span data-stu-id="6f95b-113">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="6f95b-114">Permite que os projetos incluam um `TargetPlatform` na `TargetFramework` propriedade.</span><span class="sxs-lookup"><span data-stu-id="6f95b-114">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6f95b-115">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="6f95b-115">Recommended action</span></span>

<span data-ttu-id="6f95b-116">Se você tiver uma lógica que analise o valor de `TargetFramework` , você precisará atualizá-la.</span><span class="sxs-lookup"><span data-stu-id="6f95b-116">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="6f95b-117">Por exemplo, a seguinte condição do MSBuild depende do valor de `TargetFramework` .</span><span class="sxs-lookup"><span data-stu-id="6f95b-117">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="6f95b-118">Para esse requisito, você pode atualizar o código para comparar o identificador de estrutura de destino.</span><span class="sxs-lookup"><span data-stu-id="6f95b-118">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a><span data-ttu-id="6f95b-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="6f95b-119">Affected APIs</span></span>

<span data-ttu-id="6f95b-120">N/D</span><span class="sxs-lookup"><span data-stu-id="6f95b-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
