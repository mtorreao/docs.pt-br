---
title: 'Alteração significativa: Environment. OSVersion retorna a versão correta do sistema operacional'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que Environment. OSVersion retorna a versão real do sistema operacional em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009515"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="a5a7f-103">Environment. OSVersion retorna a versão correta do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="a5a7f-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="a5a7f-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> Retorna a versão real do sistema operacional (SO) em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="a5a7f-105">Descrição da alteração</span><span class="sxs-lookup"><span data-stu-id="a5a7f-105">Change description</span></span>

<span data-ttu-id="a5a7f-106">Nas versões anteriores do .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna uma versão do sistema operacional que pode estar incorreta quando um aplicativo é executado no modo de compatibilidade do Windows.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="a5a7f-107">Para obter mais informações, consulte [comentários da função GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="a5a7f-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span> <span data-ttu-id="a5a7f-108">No macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna a versão de kernel Darwin subjacente.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-108">On macOS, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the underlying Darwin kernel version.</span></span>

<span data-ttu-id="a5a7f-109">A partir do .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna a versão real do sistema operacional para Windows e MacOS.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-109">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system for Windows and macOS.</span></span>

<span data-ttu-id="a5a7f-110">A tabela a seguir mostra a diferença no comportamento.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-110">The following table shows the difference in behavior.</span></span>

|  | <span data-ttu-id="a5a7f-111">Versões anteriores do .NET</span><span class="sxs-lookup"><span data-stu-id="a5a7f-111">Previous .NET versions</span></span> | <span data-ttu-id="a5a7f-112">.NET 5 +</span><span class="sxs-lookup"><span data-stu-id="a5a7f-112">.NET 5+</span></span> |
|--|------------------------|---------|
| <span data-ttu-id="a5a7f-113">Windows</span><span class="sxs-lookup"><span data-stu-id="a5a7f-113">Windows</span></span> | <span data-ttu-id="a5a7f-114">6.2.9200.0</span><span class="sxs-lookup"><span data-stu-id="a5a7f-114">6.2.9200.0</span></span> | <span data-ttu-id="a5a7f-115">10.0.19042.0</span><span class="sxs-lookup"><span data-stu-id="a5a7f-115">10.0.19042.0</span></span> |
| <span data-ttu-id="a5a7f-116">macOS</span><span class="sxs-lookup"><span data-stu-id="a5a7f-116">macOS</span></span> | <span data-ttu-id="a5a7f-117">19.6.0.0</span><span class="sxs-lookup"><span data-stu-id="a5a7f-117">19.6.0.0</span></span> | <span data-ttu-id="a5a7f-118">10.15.7</span><span class="sxs-lookup"><span data-stu-id="a5a7f-118">10.15.7</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="a5a7f-119">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="a5a7f-119">Reason for change</span></span>

<span data-ttu-id="a5a7f-120">Os usuários dessa propriedade esperam que ele retorne a versão real do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-120">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="a5a7f-121">A maioria dos aplicativos .NET não especifica sua versão com suporte no manifesto do aplicativo e, portanto, obtém a versão padrão com suporte do host dotnet.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-121">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="a5a7f-122">Como resultado, o Shim de compatibilidade raramente é significativo para o aplicativo em execução.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-122">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="a5a7f-123">Quando o Windows libera uma nova versão e um host dotnet mais antigo ainda está em uso, esses aplicativos podem obter uma versão incorreta do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-123">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="a5a7f-124">Retornar a versão real é mais embutido com as expectativas dos desenvolvedores desta API.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-124">Returning the actual version is more inline with developers' expectations of this API.</span></span>

<span data-ttu-id="a5a7f-125">Com a introdução de <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType> , <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> e <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> no .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> foi alterada para ser consistente para Windows e MacOS.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-125">With the introduction of <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType>, and <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> was changed to be consistent for Windows and macOS.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a5a7f-126">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="a5a7f-126">Version introduced</span></span>

<span data-ttu-id="a5a7f-127">5.0</span><span class="sxs-lookup"><span data-stu-id="a5a7f-127">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a5a7f-128">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="a5a7f-128">Recommended action</span></span>

<span data-ttu-id="a5a7f-129">Revise e teste qualquer código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para garantir que ele se comporta conforme o desejado.</span><span class="sxs-lookup"><span data-stu-id="a5a7f-129">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a5a7f-130">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="a5a7f-130">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
