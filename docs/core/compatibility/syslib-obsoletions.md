---
title: Recursos obsoletos no .NET 5 +
description: Saiba mais sobre as APIs que estão marcadas como obsoletas no .NET 5,0 e versões posteriores que produzem avisos do compilador SYSLIB.
ms.date: 10/20/2020
ms.openlocfilehash: 336958c93e3db8f66cfbec89476a666e5e103b70
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593299"
---
# <a name="obsolete-features-in-net-5"></a><span data-ttu-id="272d3-103">Recursos obsoletos no .NET 5</span><span class="sxs-lookup"><span data-stu-id="272d3-103">Obsolete features in .NET 5</span></span>

<span data-ttu-id="272d3-104">A partir do .NET 5,0, algumas APIs que são marcadas recentemente como obsoletas fazem uso de duas novas propriedades no <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="272d3-104">Starting in .NET 5.0, some APIs that are newly marked as obsolete make use of two new properties on <xref:System.ObsoleteAttribute>.</span></span>

- <span data-ttu-id="272d3-105">A <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> propriedade informa ao compilador para gerar avisos de compilação usando uma ID de diagnóstico Personalizada.</span><span class="sxs-lookup"><span data-stu-id="272d3-105">The <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> property tells the compiler to generate build warnings using a custom diagnostic ID.</span></span> <span data-ttu-id="272d3-106">A ID personalizada permite que o aviso obsoletion seja suprimido especificamente e separadamente um do outro.</span><span class="sxs-lookup"><span data-stu-id="272d3-106">The custom ID allows for obsoletion warning to be suppressed specifically and separately from one another.</span></span> <span data-ttu-id="272d3-107">No caso do .NET 5 + obsoletions, o formato da ID de diagnóstico personalizado é `SYSLIBxxxx` .</span><span class="sxs-lookup"><span data-stu-id="272d3-107">In the case of the .NET 5+ obsoletions, the format for the custom diagnostic ID is `SYSLIBxxxx`.</span></span>

- <span data-ttu-id="272d3-108">A <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> propriedade informa ao compilador para incluir um link de URL para saber mais sobre o obsoletion.</span><span class="sxs-lookup"><span data-stu-id="272d3-108">The <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> property tells the compiler to include a URL link to learn more about the obsoletion.</span></span>

<span data-ttu-id="272d3-109">Se você encontrar avisos de compilação ou erros devido ao uso de uma API obsoleta, siga as diretrizes específicas fornecidas para a ID de diagnóstico listada na seção de [referência](#reference) .</span><span class="sxs-lookup"><span data-stu-id="272d3-109">If you encounter build warnings or errors due to usage of an obsolete API, follow the specific guidance provided for the diagnostic ID listed in the [Reference](#reference) section.</span></span> <span data-ttu-id="272d3-110">Avisos ou erros para essas obsoletions *não podem* ser suprimidos usando a [CS0618 (ID de diagnóstico padrão)](../../csharp/language-reference/compiler-messages/cs0618.md) para tipos ou membros obsoletos; `SYSLIBxxxx` em vez disso, use os valores de ID de diagnóstico personalizados.</span><span class="sxs-lookup"><span data-stu-id="272d3-110">Warnings or errors for these obsoletions *can't* be suppressed using the [standard diagnostic ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID values instead.</span></span> <span data-ttu-id="272d3-111">Para obter mais informações, consulte [suprimir avisos](#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="272d3-111">For more information, see [Suppress warnings](#suppress-warnings).</span></span>

## <a name="reference"></a><span data-ttu-id="272d3-112">Referência</span><span class="sxs-lookup"><span data-stu-id="272d3-112">Reference</span></span>

<span data-ttu-id="272d3-113">A tabela a seguir fornece um índice para o `SYSLIBxxxx` obsoletions no .NET 5 +.</span><span class="sxs-lookup"><span data-stu-id="272d3-113">The following table provides an index to the `SYSLIBxxxx` obsoletions in .NET 5+.</span></span>

| <span data-ttu-id="272d3-114">ID do diagnóstico</span><span class="sxs-lookup"><span data-stu-id="272d3-114">Diagnostic ID</span></span> | <span data-ttu-id="272d3-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="272d3-115">Description</span></span> |
| - | - |
| [<span data-ttu-id="272d3-116">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="272d3-116">SYSLIB0001</span></span>](syslib-warnings/syslib0001.md) | <span data-ttu-id="272d3-117">A codificação UTF-7 é insegura e não deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="272d3-117">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="272d3-118">Considere usar UTF-8 em vez disso.</span><span class="sxs-lookup"><span data-stu-id="272d3-118">Consider using UTF-8 instead.</span></span> |
| [<span data-ttu-id="272d3-119">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="272d3-119">SYSLIB0002</span></span>](syslib-warnings/syslib0002.md) | <span data-ttu-id="272d3-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> Não é respeitado pelo tempo de execução e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="272d3-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> |
| [<span data-ttu-id="272d3-121">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="272d3-121">SYSLIB0003</span></span>](syslib-warnings/syslib0003.md) | <span data-ttu-id="272d3-122">A CAS (segurança de acesso ao código) não tem suporte nem é respeitada pelo tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="272d3-122">Code access security (CAS) is not supported or honored by the runtime.</span></span> |
| [<span data-ttu-id="272d3-123">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="272d3-123">SYSLIB0004</span></span>](syslib-warnings/syslib0004.md) | <span data-ttu-id="272d3-124">Não há suporte para o recurso CER (região de execução restrita).</span><span class="sxs-lookup"><span data-stu-id="272d3-124">The constrained execution region (CER) feature is not supported.</span></span> |
| [<span data-ttu-id="272d3-125">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="272d3-125">SYSLIB0005</span></span>](syslib-warnings/syslib0005.md) | <span data-ttu-id="272d3-126">Não há suporte para o GAC (cache de assembly global).</span><span class="sxs-lookup"><span data-stu-id="272d3-126">The global assembly cache (GAC) is not supported.</span></span> |
| [<span data-ttu-id="272d3-127">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="272d3-127">SYSLIB0006</span></span>](syslib-warnings/syslib0006.md) | <span data-ttu-id="272d3-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> Não é suportado e gera <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="272d3-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="272d3-129">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="272d3-129">SYSLIB0007</span></span>](syslib-warnings/syslib0007.md) | <span data-ttu-id="272d3-130">Não há suporte para a implementação padrão desse algoritmo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="272d3-130">The default implementation of this cryptography algorithm is not supported.</span></span> |
| [<span data-ttu-id="272d3-131">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="272d3-131">SYSLIB0008</span></span>](syslib-warnings/syslib0008.md) | <span data-ttu-id="272d3-132">A <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API não é suportada e gera <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="272d3-132">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="272d3-133">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="272d3-133">SYSLIB0009</span></span>](syslib-warnings/syslib0009.md) | <span data-ttu-id="272d3-134">Os <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> métodos e não têm suporte e geram <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="272d3-134">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="272d3-135">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="272d3-135">SYSLIB0010</span></span>](syslib-warnings/syslib0010.md) | <span data-ttu-id="272d3-136">Algumas APIs de comunicação remota não têm suporte e geram <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="272d3-136">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="272d3-137">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="272d3-137">SYSLIB0011</span></span>](syslib-warnings/syslib0011.md) | <span data-ttu-id="272d3-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> a serialização está obsoleta e não deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="272d3-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> |
| [<span data-ttu-id="272d3-139">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="272d3-139">SYSLIB0012</span></span>](syslib-warnings/syslib0012.md) | <span data-ttu-id="272d3-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> e <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> são incluídos apenas para .NET Framework compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="272d3-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="272d3-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="272d3-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> |

## <a name="suppress-warnings"></a><span data-ttu-id="272d3-142">Suprimir avisos</span><span class="sxs-lookup"><span data-stu-id="272d3-142">Suppress warnings</span></span>

<span data-ttu-id="272d3-143">Se você precisar usar as APIs obsoletas e o diagnóstico não for exibido `SYSLIBxxxx` como um erro, poderá suprimir o aviso no código ou no arquivo do projeto.</span><span class="sxs-lookup"><span data-stu-id="272d3-143">If you must use the obsolete APIs and the `SYSLIBxxxx` diagnostic does not surface as an error, you can suppress the warning in code or in your project file.</span></span>

<span data-ttu-id="272d3-144">No código:</span><span class="sxs-lookup"><span data-stu-id="272d3-144">In code:</span></span>

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

<span data-ttu-id="272d3-145">Arquivo de projeto:</span><span class="sxs-lookup"><span data-stu-id="272d3-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="272d3-146">Suprimir avisos dessa forma apenas desabilita os avisos obsoletion que você especificar.</span><span class="sxs-lookup"><span data-stu-id="272d3-146">Suppressing warnings in this way only disables the obsoletion warnings you specify.</span></span> <span data-ttu-id="272d3-147">Ele não desabilita nenhum outro aviso, incluindo avisos de obsoletion com diferentes IDs de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="272d3-147">It doesn't disable any other warnings, including obsoletion warnings with different diagnostic IDs.</span></span>
