---
title: 'Alteração significativa: o ActivityIdFormat padrão é W3C'
description: Saiba mais sobre a alteração significativa do .NET 5,0 nas principais bibliotecas do .NET em que o ActivityIdFormat padrão agora é W3C.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760418"
---
# <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="ddad2-103">O ActivityIdFormat padrão é W3C</span><span class="sxs-lookup"><span data-stu-id="ddad2-103">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="ddad2-104">O formato de identificador padrão para atividade ( <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> ) agora é <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ddad2-104">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="change-description"></a><span data-ttu-id="ddad2-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="ddad2-105">Change description</span></span>

<span data-ttu-id="ddad2-106">O formato da ID da atividade W3C foi introduzido no .NET Core 3,0 como uma alternativa ao formato de ID hierárquica.</span><span class="sxs-lookup"><span data-stu-id="ddad2-106">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="ddad2-107">No entanto, para preservar a compatibilidade, o formato W3C não foi tornado o padrão até o .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="ddad2-107">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="ddad2-108">O padrão foi alterado no .NET 5,0 porque o [formato W3C foi ratificado](https://www.w3.org/TR/trace-context/) e ganhou força em várias implementações de idioma.</span><span class="sxs-lookup"><span data-stu-id="ddad2-108">The default was changed in .NET 5.0 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="ddad2-109">Se seu aplicativo for destinado a uma plataforma diferente do .NET 5,0 ou posterior, ele passará pelo comportamento antigo, em que <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> é o formato padrão.</span><span class="sxs-lookup"><span data-stu-id="ddad2-109">If your app targets a platform other than .NET 5.0 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="ddad2-110">Esse padrão se aplica às plataformas Net45 +, netstandard 1.1 + e netcoreapp (1. x, 2. x e 3. x).</span><span class="sxs-lookup"><span data-stu-id="ddad2-110">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="ddad2-111">No .NET 5,0 e posterior, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> é definido como <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ddad2-111">In .NET 5.0 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ddad2-112">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="ddad2-112">Version introduced</span></span>

<span data-ttu-id="ddad2-113">5.0</span><span class="sxs-lookup"><span data-stu-id="ddad2-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ddad2-114">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="ddad2-114">Recommended action</span></span>

<span data-ttu-id="ddad2-115">Se seu aplicativo for independente do identificador usado para o rastreamento distribuído, nenhuma ação será necessária.</span><span class="sxs-lookup"><span data-stu-id="ddad2-115">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="ddad2-116">Bibliotecas como ASP.NET Core e <xref:System.Net.Http.HttpClient> podem consumir ou propagar ambas as versões do <xref:System.Diagnostics.ActivityIdFormat> .</span><span class="sxs-lookup"><span data-stu-id="ddad2-116">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="ddad2-117">Se você precisar de interoperabilidade com sistemas existentes ou se os sistemas atuais dependem do formato do identificador, você pode preservar o comportamento antigo definindo <xref:System.Diagnostics.Activity.DefaultIdFormat> como <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ddad2-117">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ddad2-118">Como alternativa, você pode definir uma opção AppContext de uma das três maneiras:</span><span class="sxs-lookup"><span data-stu-id="ddad2-118">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="ddad2-119">No arquivo de projeto.</span><span class="sxs-lookup"><span data-stu-id="ddad2-119">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="ddad2-120">Na *runtimeconfig.jsno* arquivo.</span><span class="sxs-lookup"><span data-stu-id="ddad2-120">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="ddad2-121">Por meio de uma variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="ddad2-121">Through an environment variable.</span></span>

  <span data-ttu-id="ddad2-122">Defina `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` como `true` ou 1.</span><span class="sxs-lookup"><span data-stu-id="ddad2-122">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ddad2-123">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="ddad2-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
