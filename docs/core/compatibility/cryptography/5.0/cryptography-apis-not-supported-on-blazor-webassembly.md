---
title: 'Alteração significativa: APIs de System. Security. Cryptography não têm suporte no Webassembly mais grande'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que as APIs de criptografia lançam uma exceção quando executadas em um navegador.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760337"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="4769a-103">APIs de System. Security. Cryptography não têm suporte no Webassembly de mais incrivelmente</span><span class="sxs-lookup"><span data-stu-id="4769a-103">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="4769a-104"><xref:System.Security.Cryptography> As APIs lançam a <xref:System.PlatformNotSupportedException> em tempo de execução quando executadas em um navegador.</span><span class="sxs-lookup"><span data-stu-id="4769a-104"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

## <a name="change-description"></a><span data-ttu-id="4769a-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="4769a-105">Change description</span></span>

<span data-ttu-id="4769a-106">Nas versões anteriores do .NET, a maioria das <xref:System.Security.Cryptography> APIs não está disponível para aplicativos Webassembly mais incrivelmente.</span><span class="sxs-lookup"><span data-stu-id="4769a-106">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="4769a-107">A partir do .NET 5,0, os aplicativos Webassembly mais completos têm como destino a área completa da superfície da API do .NET 5, no entanto, nem todas as APIs do .NET 5 têm suporte devido a restrições de área restrita do navegador.</span><span class="sxs-lookup"><span data-stu-id="4769a-107">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="4769a-108">No .NET 5,0 e versões posteriores, as APIs sem suporte <xref:System.Security.Cryptography> lançam um <xref:System.PlatformNotSupportedException> quando executado no Webassembly.</span><span class="sxs-lookup"><span data-stu-id="4769a-108">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="4769a-109">O [analisador de compatibilidade de plataforma](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) sinalizará todas as chamadas para as APIs afetadas quando você criar um projeto que dê suporte à plataforma do navegador.</span><span class="sxs-lookup"><span data-stu-id="4769a-109">The [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="4769a-110">Esse analisador é executado por padrão no .NET 5,0 e em aplicativos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4769a-110">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4769a-111">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="4769a-111">Reason for change</span></span>

<span data-ttu-id="4769a-112">A Microsoft não pode enviar o OpenSSL como uma dependência na configuração de Webassembly mais incrivelmente.</span><span class="sxs-lookup"><span data-stu-id="4769a-112">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="4769a-113">Tentamos solucionar isso tentando integrar com a API do navegador `SubtleCrypto` .</span><span class="sxs-lookup"><span data-stu-id="4769a-113">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="4769a-114">Infelizmente, isso exigiu alterações significativas na API que tornaram muito difícil a integração.</span><span class="sxs-lookup"><span data-stu-id="4769a-114">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4769a-115">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="4769a-115">Version introduced</span></span>

<span data-ttu-id="4769a-116">5.0</span><span class="sxs-lookup"><span data-stu-id="4769a-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4769a-117">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="4769a-117">Recommended action</span></span>

<span data-ttu-id="4769a-118">Não há boas soluções alternativas a serem sugeridas no momento.</span><span class="sxs-lookup"><span data-stu-id="4769a-118">There are no good workarounds to suggest at this time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4769a-119">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="4769a-119">Affected APIs</span></span>

<span data-ttu-id="4769a-120">Todas as <xref:System.Security.Cryptography?displayProperty=fullName> APIs, exceto as seguintes:</span><span class="sxs-lookup"><span data-stu-id="4769a-120">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
