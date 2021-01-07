---
title: Instalar o .NET no Alpine-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET na Alpine.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970844"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a><span data-ttu-id="7442f-103">Instalar o SDK do .NET ou o tempo de execução do .NET em Alpine Ski</span><span class="sxs-lookup"><span data-stu-id="7442f-103">Install the .NET SDK or the .NET Runtime on Alpine</span></span>

<span data-ttu-id="7442f-104">Este artigo descreve como instalar o .NET em Alpine Ski.</span><span class="sxs-lookup"><span data-stu-id="7442f-104">This article describes how to install .NET on Alpine.</span></span> <span data-ttu-id="7442f-105">Quando uma versão do Alpineio ficar sem suporte, o .NET não terá mais suporte com essa versão.</span><span class="sxs-lookup"><span data-stu-id="7442f-105">When an Alpine version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="7442f-106">No entanto, essas instruções podem ajudá-lo a obter o .NET em execução nessas versões, mesmo que não haja suporte.</span><span class="sxs-lookup"><span data-stu-id="7442f-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a><span data-ttu-id="7442f-107">Instalar</span><span class="sxs-lookup"><span data-stu-id="7442f-107">Install</span></span>

<span data-ttu-id="7442f-108">Instaladores não estão disponíveis para o Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="7442f-108">Installers aren't available for Alpine Linux.</span></span> <span data-ttu-id="7442f-109">Você deve instalar o .NET de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="7442f-109">You must install .NET in one of the following ways:</span></span>

- [<span data-ttu-id="7442f-110">Ajustar pacote</span><span class="sxs-lookup"><span data-stu-id="7442f-110">Snap package</span></span>](linux-snap.md)
- [<span data-ttu-id="7442f-111">Instalação com script com _install-dotnet.sh_</span><span class="sxs-lookup"><span data-stu-id="7442f-111">Scripted install with _install-dotnet.sh_</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="7442f-112">Extração binária manual</span><span class="sxs-lookup"><span data-stu-id="7442f-112">Manual binary extraction</span></span>](linux-scripted-manual.md#manual-install)

## <a name="supported-distributions"></a><span data-ttu-id="7442f-113">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="7442f-113">Supported distributions</span></span>

<span data-ttu-id="7442f-114">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do Alpine para as quais têm suporte.</span><span class="sxs-lookup"><span data-stu-id="7442f-114">The following table is a list of currently supported .NET releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="7442f-115">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do [Alpine alcance o fim da vida útil](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span><span class="sxs-lookup"><span data-stu-id="7442f-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="7442f-116">Um ✔️ indica que a versão do Alpine ou .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="7442f-116">A ✔️ indicates that the version of Alpine or .NET is still supported.</span></span>
- <span data-ttu-id="7442f-117">Um ❌ indica que a versão do Alpine ou do .net não tem suporte nessa versão do Alpine.</span><span class="sxs-lookup"><span data-stu-id="7442f-117">A ❌ indicates that the version of Alpine or .NET isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="7442f-118">Quando uma versão do Alpine e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="7442f-118">When both a version of Alpine and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="7442f-119">Alpine</span><span class="sxs-lookup"><span data-stu-id="7442f-119">Alpine</span></span>  | <span data-ttu-id="7442f-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7442f-120">.NET Core 2.1</span></span> | <span data-ttu-id="7442f-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7442f-121">.NET Core 3.1</span></span> | <span data-ttu-id="7442f-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7442f-122">.NET 5.0</span></span> |
|-------- |---------------|---------------|----------------|
| <span data-ttu-id="7442f-123">✔️ 3,12</span><span class="sxs-lookup"><span data-stu-id="7442f-123">✔️ 3.12</span></span> | <span data-ttu-id="7442f-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="7442f-124">✔️ 2.1</span></span>        | <span data-ttu-id="7442f-125">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="7442f-125">✔️ 3.1</span></span>        | <span data-ttu-id="7442f-126">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="7442f-126">✔️ 5.0</span></span> |
| <span data-ttu-id="7442f-127">✔️ 3,11</span><span class="sxs-lookup"><span data-stu-id="7442f-127">✔️ 3.11</span></span> | <span data-ttu-id="7442f-128">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="7442f-128">✔️ 2.1</span></span>        | <span data-ttu-id="7442f-129">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="7442f-129">✔️ 3.1</span></span>        | <span data-ttu-id="7442f-130">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="7442f-130">✔️ 5.0</span></span> |
| <span data-ttu-id="7442f-131">✔️ 3,10</span><span class="sxs-lookup"><span data-stu-id="7442f-131">✔️ 3.10</span></span> | <span data-ttu-id="7442f-132">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="7442f-132">✔️ 2.1</span></span>        | <span data-ttu-id="7442f-133">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="7442f-133">✔️ 3.1</span></span>        | <span data-ttu-id="7442f-134">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="7442f-134">❌ 5.0</span></span> |
| <span data-ttu-id="7442f-135">❌ 3,9</span><span class="sxs-lookup"><span data-stu-id="7442f-135">❌ 3.9</span></span>  | <span data-ttu-id="7442f-136">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="7442f-136">✔️ 2.1</span></span>        | <span data-ttu-id="7442f-137">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="7442f-137">✔️ 3.1</span></span>        | <span data-ttu-id="7442f-138">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="7442f-138">❌ 5.0</span></span> |
| <span data-ttu-id="7442f-139">❌ 3,8</span><span class="sxs-lookup"><span data-stu-id="7442f-139">❌ 3.8</span></span>  | <span data-ttu-id="7442f-140">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="7442f-140">✔️ 2.1</span></span>        | <span data-ttu-id="7442f-141">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="7442f-141">✔️ 3.1</span></span>        | <span data-ttu-id="7442f-142">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="7442f-142">❌ 5.0</span></span> |

<span data-ttu-id="7442f-143">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="7442f-143">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="7442f-144">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="7442f-144">The downloads for these still remain published:</span></span>

- <span data-ttu-id="7442f-145">3.0</span><span class="sxs-lookup"><span data-stu-id="7442f-145">3.0</span></span>
- <span data-ttu-id="7442f-146">2.2</span><span class="sxs-lookup"><span data-stu-id="7442f-146">2.2</span></span>
- <span data-ttu-id="7442f-147">2,0</span><span class="sxs-lookup"><span data-stu-id="7442f-147">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="7442f-148">Dependências</span><span class="sxs-lookup"><span data-stu-id="7442f-148">Dependencies</span></span>

<span data-ttu-id="7442f-149">O .NET no Alpineum Linux requer as seguintes dependências instaladas:</span><span class="sxs-lookup"><span data-stu-id="7442f-149">.NET on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="7442f-150">ICU-bibliotecas</span><span class="sxs-lookup"><span data-stu-id="7442f-150">icu-libs</span></span>
- <span data-ttu-id="7442f-151">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="7442f-151">krb5-libs</span></span>
- <span data-ttu-id="7442f-152">libgcc</span><span class="sxs-lookup"><span data-stu-id="7442f-152">libgcc</span></span>
- <span data-ttu-id="7442f-153">libintl</span><span class="sxs-lookup"><span data-stu-id="7442f-153">libintl</span></span>
- <span data-ttu-id="7442f-154">libssl 1.1 (Alpine v 3.9 ou superior)</span><span class="sxs-lookup"><span data-stu-id="7442f-154">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="7442f-155">libssl 1.0 (Alpine v 3.8 ou inferior)</span><span class="sxs-lookup"><span data-stu-id="7442f-155">libssl1.0 (Alpine v3.8 or lower)</span></span>
- <span data-ttu-id="7442f-156">libstdc++</span><span class="sxs-lookup"><span data-stu-id="7442f-156">libstdc++</span></span>
- <span data-ttu-id="7442f-157">zlib</span><span class="sxs-lookup"><span data-stu-id="7442f-157">zlib</span></span>

## <a name="next-steps"></a><span data-ttu-id="7442f-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7442f-158">Next steps</span></span>

- [<span data-ttu-id="7442f-159">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="7442f-159">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="7442f-160">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7442f-160">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
