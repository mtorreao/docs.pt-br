---
title: 'Alteração significativa: as APIs do cache de assembly global estão obsoletas'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que as APIs que lidam com o GAC falham ou não executam nenhuma operação.
ms.date: 11/01/2020
ms.openlocfilehash: 2f74fccc68b7a925d909938d77578df8ebe8d60d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760416"
---
# <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="8f3e4-103">As APIs do cache de assembly global estão obsoletas</span><span class="sxs-lookup"><span data-stu-id="8f3e4-103">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="8f3e4-104">O .NET Core e o .NET 5,0 e versões posteriores eliminam o conceito do GAC (cache de assembly global) que estava presente no .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-104">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="8f3e4-105">Assim, todas as APIs .NET Core e .NET 5 + que lidam com o GAC falham ou não executam nenhuma operação.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-105">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="8f3e4-106">Para ajudar os desenvolvedores a se afastar dessas APIs, algumas APIs relacionadas ao GAC são marcadas como obsoletas e geram um `SYSLIB0005` aviso no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-106">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="8f3e4-107">Essas APIs podem ser removidas em uma versão futura do .NET.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-107">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="8f3e4-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="8f3e4-108">Change description</span></span>

<span data-ttu-id="8f3e4-109">As seguintes APIs estão marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-109">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="8f3e4-110">API</span><span class="sxs-lookup"><span data-stu-id="8f3e4-110">API</span></span> | <span data-ttu-id="8f3e4-111">Marcado como obsoleto em...</span><span class="sxs-lookup"><span data-stu-id="8f3e4-111">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="8f3e4-112">RC1 5,0</span><span class="sxs-lookup"><span data-stu-id="8f3e4-112">5.0 RC1</span></span> |

<span data-ttu-id="8f3e4-113">No .NET Framework 2. x-4. x, a <xref:System.Reflection.Assembly.GlobalAssemblyCache> propriedade retorna `true` se o assembly consultado foi carregado do GAC e `false` se foi carregado a partir de um local diferente no disco.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-113">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="8f3e4-114">No .NET Core 2. x-3. x, o <xref:System.Reflection.Assembly.GlobalAssemblyCache> sempre retorna `false` , refletindo que o GAC não existe no .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-114">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="8f3e4-115">No .NET 5,0 e versões posteriores, a <xref:System.Reflection.Assembly.GlobalAssemblyCache> Propriedade continua sempre retornando `false` .</span><span class="sxs-lookup"><span data-stu-id="8f3e4-115">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="8f3e4-116">No entanto, o getter da propriedade também é marcado como obsoleto para indicar aos chamadores que eles devem parar de acessar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-116">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="8f3e4-117">Bibliotecas e aplicativos não devem usar a <xref:System.Reflection.Assembly.GlobalAssemblyCache> API para fazer determinações sobre o comportamento de tempo de execução, como sempre retorna `false` no .NET Core e no .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-117">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="8f3e4-118">Essa é uma alteração somente em tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-118">This is a compile-time only change.</span></span> <span data-ttu-id="8f3e4-119">Não há nenhuma alteração de tempo de execução de versões anteriores do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-119">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8f3e4-120">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="8f3e4-120">Reason for change</span></span>

<span data-ttu-id="8f3e4-121">O GAC (cache de assembly global) não existe como um conceito no .NET Core e no .NET 5,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-121">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8f3e4-122">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="8f3e4-122">Version introduced</span></span>

<span data-ttu-id="8f3e4-123">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="8f3e4-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8f3e4-124">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="8f3e4-124">Recommended action</span></span>

- <span data-ttu-id="8f3e4-125">Se seu aplicativo consulta a <xref:System.Reflection.Assembly.GlobalAssemblyCache> propriedade, considere remover a chamada.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-125">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="8f3e4-126">Se você usar o <xref:System.Reflection.Assembly.GlobalAssemblyCache> valor para escolher entre um "assembly no GAC"-Flow versus um "assembly que não está no GAC"-Flow em tempo de execução, reconsidere se o fluxo ainda faz sentido para um aplicativo .NET Core ou .NET 5.0 +.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-126">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="8f3e4-127">Se você precisar continuar a usar as APIs obsoletas, poderá suprimir o `SYSLIB0005` aviso no código.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="8f3e4-128">Você também pode suprimir o aviso em seu arquivo de projeto, o que desabilita o aviso para todos os arquivos de origem no projeto.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="8f3e4-129">Suprimir `SYSLIB0005` desabilita apenas o <xref:System.Reflection.Assembly.GlobalAssemblyCache> aviso obsoletion.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-129">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="8f3e4-130">Ele não desabilita nenhum outro aviso.</span><span class="sxs-lookup"><span data-stu-id="8f3e4-130">It does not disable any other warnings.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8f3e4-131">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="8f3e4-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
