---
title: 'Alteração significativa: Environment. OSVersion retorna a versão correta do sistema operacional'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que Environment. OSVersion retorna a versão real do sistema operacional em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760546"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a><span data-ttu-id="d7a92-103">Environment. OSVersion retorna a versão correta do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d7a92-103">Environment.OSVersion returns the correct operating system version</span></span>

<span data-ttu-id="d7a92-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> Retorna a versão real do sistema operacional (SO) em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d7a92-104"><xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system (OS) instead of, for example, the OS that's selected for application compatibility.</span></span>

## <a name="change-description"></a><span data-ttu-id="d7a92-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="d7a92-105">Change description</span></span>

<span data-ttu-id="d7a92-106">Nas versões anteriores do .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna uma versão do sistema operacional que pode estar incorreta quando um aplicativo é executado no modo de compatibilidade do Windows.</span><span class="sxs-lookup"><span data-stu-id="d7a92-106">In previous .NET versions, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns an OS version that may be incorrect when an application runs under Windows compatibility mode.</span></span> <span data-ttu-id="d7a92-107">Para obter mais informações, consulte [comentários da função GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span><span class="sxs-lookup"><span data-stu-id="d7a92-107">For more information, see [GetVersionExA function remarks](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).</span></span>

<span data-ttu-id="d7a92-108">A partir do .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna a versão real do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d7a92-108">Starting in .NET 5.0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> returns the actual version of the operating system.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d7a92-109">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="d7a92-109">Reason for change</span></span>

<span data-ttu-id="d7a92-110">Os usuários dessa propriedade esperam que ele retorne a versão real do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d7a92-110">Users of this property expect it to return the actual version of the operating system.</span></span> <span data-ttu-id="d7a92-111">A maioria dos aplicativos .NET não especifica sua versão com suporte no manifesto do aplicativo e, portanto, obtém a versão padrão com suporte do host dotnet.</span><span class="sxs-lookup"><span data-stu-id="d7a92-111">Most .NET apps don't specify their supported version in their application manifest, and thus get the default supported version from the dotnet host.</span></span> <span data-ttu-id="d7a92-112">Como resultado, o Shim de compatibilidade raramente é significativo para o aplicativo em execução.</span><span class="sxs-lookup"><span data-stu-id="d7a92-112">As a result, the compatibility shim is rarely meaningful for the app that's running.</span></span> <span data-ttu-id="d7a92-113">Quando o Windows libera uma nova versão e um host dotnet mais antigo ainda está em uso, esses aplicativos podem obter uma versão incorreta do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d7a92-113">When Windows releases a new version and an older dotnet host is still in use, these apps may get an incorrect OS version.</span></span> <span data-ttu-id="d7a92-114">Retornar a versão real é mais embutido com as expectativas dos desenvolvedores desta API.</span><span class="sxs-lookup"><span data-stu-id="d7a92-114">Returning the actual version is more inline with developers' expectations of this API.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d7a92-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="d7a92-115">Version introduced</span></span>

<span data-ttu-id="d7a92-116">5.0</span><span class="sxs-lookup"><span data-stu-id="d7a92-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d7a92-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="d7a92-117">Recommended action</span></span>

<span data-ttu-id="d7a92-118">Revise e teste qualquer código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para garantir que ele se comporta conforme o desejado.</span><span class="sxs-lookup"><span data-stu-id="d7a92-118">Review and test any code that uses <xref:System.Environment.OSVersion?displayProperty=nameWithType> to ensure it behaves as desired.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d7a92-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="d7a92-119">Affected APIs</span></span>

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
