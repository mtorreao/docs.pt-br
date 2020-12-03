---
title: Instalar o .NET no Windows
description: Saiba mais sobre quais versões do Windows você pode instalar no .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 786814549724948fa69b18a05cee966e0940aaf4
ms.sourcegitcommit: c6de55556add9f92af17e0f8d1da8f356a19a03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96549339"
---
# <a name="install-net-on-windows"></a><span data-ttu-id="d6a62-103">Instalar o .NET no Windows</span><span class="sxs-lookup"><span data-stu-id="d6a62-103">Install .NET on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Instalar no Windows](windows.md)
> - [Instalar no macOS](macos.md)
> - [Instalar no Linux](linux.md)

<span data-ttu-id="d6a62-107">Neste artigo, você aprenderá a instalar o .NET no Windows.</span><span class="sxs-lookup"><span data-stu-id="d6a62-107">In this article, you'll learn how to install .NET on Windows.</span></span> <span data-ttu-id="d6a62-108">O .NET é constituído do tempo de execução e do SDK.</span><span class="sxs-lookup"><span data-stu-id="d6a62-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="d6a62-109">O tempo de execução é usado para executar um aplicativo .NET e pode ou não ser incluído com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6a62-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="d6a62-110">O SDK é usado para criar aplicativos e bibliotecas .NET.</span><span class="sxs-lookup"><span data-stu-id="d6a62-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="d6a62-111">O tempo de execução do .NET é sempre instalado com o SDK.</span><span class="sxs-lookup"><span data-stu-id="d6a62-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="d6a62-112">A versão mais recente do .NET é 5,0.</span><span class="sxs-lookup"><span data-stu-id="d6a62-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="d6a62-113">Baixar o .NET</span><span class="sxs-lookup"><span data-stu-id="d6a62-113">Download .NET</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="d6a62-114">Versões com suporte</span><span class="sxs-lookup"><span data-stu-id="d6a62-114">Supported releases</span></span>

<span data-ttu-id="d6a62-115">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do Windows nas quais elas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="d6a62-115">The following table is a list of currently supported .NET releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="d6a62-116">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do [Windows alcance o fim da vida útil](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="d6a62-116">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="d6a62-117">As datas de fim de serviço das versões do Windows 10 são segmentadas por edição.</span><span class="sxs-lookup"><span data-stu-id="d6a62-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="d6a62-118">Somente as edições **Home**, **pro**, **pro Education** e **Pro for Workstations** são consideradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6a62-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="d6a62-119">Verifique a [folha de fatos do ciclo de vida do Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) para obter detalhes específicos.</span><span class="sxs-lookup"><span data-stu-id="d6a62-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

> [!TIP]
> <span data-ttu-id="d6a62-120">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-120">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-121">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="d6a62-121">Operating System</span></span>            | <span data-ttu-id="d6a62-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-122">.NET Core 2.1</span></span> | <span data-ttu-id="d6a62-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-123">.NET Core 3.1</span></span> | <span data-ttu-id="d6a62-124">.NET 5</span><span class="sxs-lookup"><span data-stu-id="d6a62-124">.NET 5</span></span> |
|-----------------------------|---------------|---------------|--------|
| <span data-ttu-id="d6a62-125">Windows 10, versão 2004</span><span class="sxs-lookup"><span data-stu-id="d6a62-125">Windows 10, Version 2004</span></span>    | <span data-ttu-id="d6a62-126">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-126">✔️</span></span>           | <span data-ttu-id="d6a62-127">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-127">✔️</span></span>            | <span data-ttu-id="d6a62-128">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-128">✔️</span></span>    |
| <span data-ttu-id="d6a62-129">Windows 10, versão 1909</span><span class="sxs-lookup"><span data-stu-id="d6a62-129">Windows 10, Version 1909</span></span>    | <span data-ttu-id="d6a62-130">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-130">✔️</span></span>           | <span data-ttu-id="d6a62-131">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-131">✔️</span></span>            | <span data-ttu-id="d6a62-132">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-132">✔️</span></span>    |
| <span data-ttu-id="d6a62-133">Windows 10, versão 1903</span><span class="sxs-lookup"><span data-stu-id="d6a62-133">Windows 10, Version 1903</span></span>    | <span data-ttu-id="d6a62-134">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-134">✔️</span></span>           | <span data-ttu-id="d6a62-135">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-135">✔️</span></span>            | <span data-ttu-id="d6a62-136">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-136">✔️</span></span>    |
| <span data-ttu-id="d6a62-137">Windows 10, versão 1809</span><span class="sxs-lookup"><span data-stu-id="d6a62-137">Windows 10, Version 1809</span></span>    | <span data-ttu-id="d6a62-138">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-138">✔️</span></span>           | <span data-ttu-id="d6a62-139">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-139">✔️</span></span>            | <span data-ttu-id="d6a62-140">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-140">✔️</span></span>    |
| <span data-ttu-id="d6a62-141">Windows 10, versão 1803</span><span class="sxs-lookup"><span data-stu-id="d6a62-141">Windows 10, Version 1803</span></span>    | <span data-ttu-id="d6a62-142">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-142">✔️</span></span>           | <span data-ttu-id="d6a62-143">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-143">✔️</span></span>            | <span data-ttu-id="d6a62-144">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-144">✔️</span></span>    |
| <span data-ttu-id="d6a62-145">Windows 10, versão 1709</span><span class="sxs-lookup"><span data-stu-id="d6a62-145">Windows 10, Version 1709</span></span>    | <span data-ttu-id="d6a62-146">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-146">✔️</span></span>           | <span data-ttu-id="d6a62-147">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-147">✔️</span></span>            | <span data-ttu-id="d6a62-148">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-148">✔️</span></span>    |
| <span data-ttu-id="d6a62-149">Windows 10, versão 1607</span><span class="sxs-lookup"><span data-stu-id="d6a62-149">Windows 10, Version 1607</span></span>    | <span data-ttu-id="d6a62-150">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-150">✔️</span></span>           | <span data-ttu-id="d6a62-151">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-151">✔️</span></span>            | <span data-ttu-id="d6a62-152">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-152">✔️</span></span>    |
| <span data-ttu-id="d6a62-153">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-153">Windows 8.1</span></span>                 | <span data-ttu-id="d6a62-154">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-154">✔️</span></span>           | <span data-ttu-id="d6a62-155">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-155">✔️</span></span>            | <span data-ttu-id="d6a62-156">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-156">✔️</span></span>    |
| <span data-ttu-id="d6a62-157">[ESU][esu] do Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="d6a62-157">Windows 7 SP1 [ESU][esu]</span></span>    | <span data-ttu-id="d6a62-158">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-158">✔️</span></span>           | <span data-ttu-id="d6a62-159">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-159">✔️</span></span>            | <span data-ttu-id="d6a62-160">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-160">✔️</span></span>    |
| <span data-ttu-id="d6a62-161">Windows 10, versão 1607</span><span class="sxs-lookup"><span data-stu-id="d6a62-161">Windows 10, Version 1607</span></span>    | <span data-ttu-id="d6a62-162">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-162">✔️</span></span>           | <span data-ttu-id="d6a62-163">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-163">✔️</span></span>            | <span data-ttu-id="d6a62-164">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-164">✔️</span></span>    |
| <span data-ttu-id="d6a62-165">Windows 10, versão 1607</span><span class="sxs-lookup"><span data-stu-id="d6a62-165">Windows 10, Version 1607</span></span>    | <span data-ttu-id="d6a62-166">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-166">✔️</span></span>           | <span data-ttu-id="d6a62-167">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-167">✔️</span></span>            | <span data-ttu-id="d6a62-168">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-168">✔️</span></span>    |
| <span data-ttu-id="d6a62-169">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6a62-169">Windows Server 2012 R2</span></span>      | <span data-ttu-id="d6a62-170">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-170">✔️</span></span>           | <span data-ttu-id="d6a62-171">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-171">✔️</span></span>            | <span data-ttu-id="d6a62-172">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-172">✔️</span></span>    |
| <span data-ttu-id="d6a62-173">Windows Server Core 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6a62-173">Windows Server Core 2012 R2</span></span> | <span data-ttu-id="d6a62-174">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-174">✔️</span></span>           | <span data-ttu-id="d6a62-175">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-175">✔️</span></span>            | <span data-ttu-id="d6a62-176">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-176">✔️</span></span>    |
| <span data-ttu-id="d6a62-177">Nano Server, versão 1809 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-177">Nano Server, Version 1809+</span></span>  | <span data-ttu-id="d6a62-178">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-178">✔️</span></span>           | <span data-ttu-id="d6a62-179">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-179">✔️</span></span>            | <span data-ttu-id="d6a62-180">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-180">✔️</span></span>    |
| <span data-ttu-id="d6a62-181">Nano Server, versão 1803</span><span class="sxs-lookup"><span data-stu-id="d6a62-181">Nano Server, Version 1803</span></span>   | <span data-ttu-id="d6a62-182">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-182">✔️</span></span>           | <span data-ttu-id="d6a62-183">✔️</span><span class="sxs-lookup"><span data-stu-id="d6a62-183">✔️</span></span>            | ❌    |

## <a name="unsupported-releases"></a><span data-ttu-id="d6a62-184">Versões sem suporte</span><span class="sxs-lookup"><span data-stu-id="d6a62-184">Unsupported releases</span></span>

<span data-ttu-id="d6a62-185">Não há mais suporte para as seguintes versões do .NET ❌ .</span><span class="sxs-lookup"><span data-stu-id="d6a62-185">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="d6a62-186">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="d6a62-186">The downloads for these still remain published:</span></span>

- <span data-ttu-id="d6a62-187">3.0</span><span class="sxs-lookup"><span data-stu-id="d6a62-187">3.0</span></span>
- <span data-ttu-id="d6a62-188">2.2</span><span class="sxs-lookup"><span data-stu-id="d6a62-188">2.2</span></span>
- <span data-ttu-id="d6a62-189">2,0</span><span class="sxs-lookup"><span data-stu-id="d6a62-189">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="d6a62-190">Informações de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="d6a62-190">Runtime information</span></span>

<span data-ttu-id="d6a62-191">O tempo de execução é usado para executar aplicativos criados com o .NET.</span><span class="sxs-lookup"><span data-stu-id="d6a62-191">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="d6a62-192">Quando um autor de aplicativo publica um aplicativo, ele pode incluir o tempo de execução com seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6a62-192">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="d6a62-193">Se eles não incluírem o tempo de execução, cabe ao usuário instalar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d6a62-193">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="d6a62-194">Há três tempos de execução diferentes que você pode instalar no Windows:</span><span class="sxs-lookup"><span data-stu-id="d6a62-194">There are three different runtimes you can install on Windows:</span></span>

<span data-ttu-id="d6a62-195">*Tempo de execução ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="d6a62-195">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="d6a62-196">Executa ASP.NET Core aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d6a62-196">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="d6a62-197">Inclui o tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="d6a62-197">Includes the .NET runtime.</span></span>

<span data-ttu-id="d6a62-198">*Tempo de execução do desktop*</span><span class="sxs-lookup"><span data-stu-id="d6a62-198">*Desktop runtime*</span></span>\
<span data-ttu-id="d6a62-199">Executa o .NET WPF e Windows Forms aplicativos de área de trabalho para Windows.</span><span class="sxs-lookup"><span data-stu-id="d6a62-199">Runs .NET WPF and Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="d6a62-200">Inclui o tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="d6a62-200">Includes the .NET runtime.</span></span>

<span data-ttu-id="d6a62-201">*Tempo de execução do .NET*</span><span class="sxs-lookup"><span data-stu-id="d6a62-201">*.NET runtime*</span></span>\
<span data-ttu-id="d6a62-202">Esse tempo de execução é o tempo de execução mais simples e não inclui nenhum outro tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d6a62-202">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="d6a62-203">É altamente recomendável que você instale o *tempo de execução do ASP.NET Core* e o *tempo de execução da área de trabalho* para obter a melhor compatibilidade com aplicativos .net.</span><span class="sxs-lookup"><span data-stu-id="d6a62-203">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="d6a62-204">Baixar o tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="d6a62-204">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="d6a62-205">Informações do SDK</span><span class="sxs-lookup"><span data-stu-id="d6a62-205">SDK information</span></span>

<span data-ttu-id="d6a62-206">O SDK é usado para compilar e publicar aplicativos e bibliotecas .NET.</span><span class="sxs-lookup"><span data-stu-id="d6a62-206">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="d6a62-207">A instalação do SDK inclui todos os três [tempos de execução](#runtime-information): ASP.NET Core, desktop e .net.</span><span class="sxs-lookup"><span data-stu-id="d6a62-207">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="d6a62-208">Dependências</span><span class="sxs-lookup"><span data-stu-id="d6a62-208">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[<span data-ttu-id="d6a62-209">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d6a62-209">.NET 5.0</span></span>](#tab/net50)

<span data-ttu-id="d6a62-210">As seguintes versões do Windows têm suporte com o .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="d6a62-210">The following Windows versions are supported with .NET 5.0:</span></span>

> [!NOTE]
> <span data-ttu-id="d6a62-211">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-211">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-212">SO</span><span class="sxs-lookup"><span data-stu-id="d6a62-212">OS</span></span>                  | <span data-ttu-id="d6a62-213">Versão</span><span class="sxs-lookup"><span data-stu-id="d6a62-213">Version</span></span>       | <span data-ttu-id="d6a62-214">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="d6a62-214">Architectures</span></span>   |
|---------------------|---------------|-----------------|
| <span data-ttu-id="d6a62-215">Cliente do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6a62-215">Windows 10 Client</span></span>   | <span data-ttu-id="d6a62-216">Versão 1607 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-216">Version 1607+</span></span> | <span data-ttu-id="d6a62-217">x64, x86, ARM64</span><span class="sxs-lookup"><span data-stu-id="d6a62-217">x64, x86, ARM64</span></span> |
| <span data-ttu-id="d6a62-218">Windows Client</span><span class="sxs-lookup"><span data-stu-id="d6a62-218">Windows Client</span></span>      | <span data-ttu-id="d6a62-219">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-219">7 SP1+, 8.1</span></span>   | <span data-ttu-id="d6a62-220">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-220">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-221">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-221">Windows Server</span></span>      | <span data-ttu-id="d6a62-222">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-222">2012 R2+</span></span>      | <span data-ttu-id="d6a62-223">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-223">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-224">Núcleo do Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-224">Windows Server Core</span></span> | <span data-ttu-id="d6a62-225">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-225">2012 R2+</span></span>      | <span data-ttu-id="d6a62-226">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-226">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-227">Nano Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-227">Nano Server</span></span>         | <span data-ttu-id="d6a62-228">Versão 1809 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-228">Version 1809+</span></span> | <span data-ttu-id="d6a62-229">x64</span><span class="sxs-lookup"><span data-stu-id="d6a62-229">x64</span></span>             |

<span data-ttu-id="d6a62-230">Para obter mais informações sobre OS sistemas operacionais, as distribuições e a política de ciclo de vida com suporte do .NET 5,0, consulte [versões do sistema operacional .net 5,0 com suporte](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-230">For more information about .NET 5.0 supported operating systems, distributions, and lifecycle policy, see [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).</span></span>

# <a name="net-core-31"></a>[<span data-ttu-id="d6a62-231">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-231">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="d6a62-232">As seguintes versões do Windows têm suporte com o .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="d6a62-232">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="d6a62-233">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-233">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-234">SO</span><span class="sxs-lookup"><span data-stu-id="d6a62-234">OS</span></span>                            | <span data-ttu-id="d6a62-235">Versão</span><span class="sxs-lookup"><span data-stu-id="d6a62-235">Version</span></span>                        | <span data-ttu-id="d6a62-236">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="d6a62-236">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d6a62-237">Windows Client</span><span class="sxs-lookup"><span data-stu-id="d6a62-237">Windows Client</span></span>                | <span data-ttu-id="d6a62-238">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-238">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d6a62-239">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-239">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-240">Cliente do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6a62-240">Windows 10 Client</span></span>             | <span data-ttu-id="d6a62-241">Versão 1607 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-241">Version 1607+</span></span>                  | <span data-ttu-id="d6a62-242">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-242">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-243">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-243">Windows Server</span></span>                | <span data-ttu-id="d6a62-244">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-244">2012 R2+</span></span>                       | <span data-ttu-id="d6a62-245">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-245">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-246">Nano Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-246">Nano Server</span></span>                   | <span data-ttu-id="d6a62-247">Versão 1803 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-247">Version 1803+</span></span>                  | <span data-ttu-id="d6a62-248">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d6a62-248">x64, ARM32</span></span>      |

<span data-ttu-id="d6a62-249">Para obter mais informações sobre OS sistemas operacionais, as distribuições e a política de ciclo de vida com suporte do .NET Core 3,1, consulte [versões do sistema operacional .net core 3,1 com suporte](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-249">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="d6a62-250">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d6a62-250">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="d6a62-251">*O .NET Core 3,0 está atualmente ❌ sem suporte. Para obter mais informações, consulte a [política de suporte do .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="d6a62-251">*.NET Core 3.0 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d6a62-252">As seguintes versões do Windows têm suporte com o .NET Core 3,0:</span><span class="sxs-lookup"><span data-stu-id="d6a62-252">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="d6a62-253">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-253">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-254">SO</span><span class="sxs-lookup"><span data-stu-id="d6a62-254">OS</span></span>                            | <span data-ttu-id="d6a62-255">Versão</span><span class="sxs-lookup"><span data-stu-id="d6a62-255">Version</span></span>                        | <span data-ttu-id="d6a62-256">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="d6a62-256">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d6a62-257">Windows Client</span><span class="sxs-lookup"><span data-stu-id="d6a62-257">Windows Client</span></span>                | <span data-ttu-id="d6a62-258">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-258">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d6a62-259">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-259">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-260">Cliente do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6a62-260">Windows 10 Client</span></span>             | <span data-ttu-id="d6a62-261">Versão 1607 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-261">Version 1607+</span></span>                  | <span data-ttu-id="d6a62-262">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-262">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-263">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-263">Windows Server</span></span>                | <span data-ttu-id="d6a62-264">2012 R2 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-264">2012 R2+</span></span>                       | <span data-ttu-id="d6a62-265">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-265">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-266">Nano Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-266">Nano Server</span></span>                   | <span data-ttu-id="d6a62-267">Versão 1803 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-267">Version 1803+</span></span>                  | <span data-ttu-id="d6a62-268">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d6a62-268">x64, ARM32</span></span>      |

<span data-ttu-id="d6a62-269">Para obter mais informações sobre OS sistemas operacionais, as distribuições e a política de ciclo de vida com suporte do .NET Core 3,0, consulte [versões do sistema operacional .net core 3,0 com suporte](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-269">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="d6a62-270">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="d6a62-270">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="d6a62-271">*O .NET Core 2,2 está atualmente ❌ sem suporte. Para obter mais informações, consulte a [política de suporte do .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="d6a62-271">*.NET Core 2.2 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="d6a62-272">As seguintes versões do Windows têm suporte com o .NET Core 2,2:</span><span class="sxs-lookup"><span data-stu-id="d6a62-272">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="d6a62-273">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-273">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-274">SO</span><span class="sxs-lookup"><span data-stu-id="d6a62-274">OS</span></span>                            | <span data-ttu-id="d6a62-275">Versão</span><span class="sxs-lookup"><span data-stu-id="d6a62-275">Version</span></span>                        | <span data-ttu-id="d6a62-276">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="d6a62-276">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d6a62-277">Windows Client</span><span class="sxs-lookup"><span data-stu-id="d6a62-277">Windows Client</span></span>                | <span data-ttu-id="d6a62-278">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-278">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d6a62-279">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-279">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-280">Cliente do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6a62-280">Windows 10 Client</span></span>             | <span data-ttu-id="d6a62-281">Versão 1607 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-281">Version 1607+</span></span>                  | <span data-ttu-id="d6a62-282">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-282">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-283">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-283">Windows Server</span></span>                | <span data-ttu-id="d6a62-284">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-284">2008 R2 SP1+</span></span>                   | <span data-ttu-id="d6a62-285">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-285">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-286">Nano Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-286">Nano Server</span></span>                   | <span data-ttu-id="d6a62-287">Versão 1803 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-287">Version 1803+</span></span>                   | <span data-ttu-id="d6a62-288">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="d6a62-288">x64, ARM32</span></span>      |

<span data-ttu-id="d6a62-289">Para obter mais informações sobre OS sistemas operacionais, as distribuições e a política de ciclo de vida com suporte do .NET Core 2,2, consulte [versões do sistema operacional .net core 2,2 com suporte](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-289">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="d6a62-290">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-290">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d6a62-291">As seguintes versões do Windows têm suporte com o .NET Core 2,1:</span><span class="sxs-lookup"><span data-stu-id="d6a62-291">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="d6a62-292">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="d6a62-292">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="d6a62-293">SO</span><span class="sxs-lookup"><span data-stu-id="d6a62-293">OS</span></span>                            | <span data-ttu-id="d6a62-294">Versão</span><span class="sxs-lookup"><span data-stu-id="d6a62-294">Version</span></span>                        | <span data-ttu-id="d6a62-295">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="d6a62-295">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="d6a62-296">Windows Client</span><span class="sxs-lookup"><span data-stu-id="d6a62-296">Windows Client</span></span>                | <span data-ttu-id="d6a62-297">7 SP1 +, 8,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-297">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="d6a62-298">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-298">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-299">Cliente do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6a62-299">Windows 10 Client</span></span>             | <span data-ttu-id="d6a62-300">Versão 1607 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-300">Version 1607+</span></span>                  | <span data-ttu-id="d6a62-301">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-301">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-302">Windows Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-302">Windows Server</span></span>                | <span data-ttu-id="d6a62-303">2008 R2 SP1 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-303">2008 R2 SP1+</span></span>                   | <span data-ttu-id="d6a62-304">x64, x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-304">x64, x86</span></span>        |
| <span data-ttu-id="d6a62-305">Nano Server</span><span class="sxs-lookup"><span data-stu-id="d6a62-305">Nano Server</span></span>                   | <span data-ttu-id="d6a62-306">Versão 1803 +</span><span class="sxs-lookup"><span data-stu-id="d6a62-306">Version 1803+</span></span>                  | <span data-ttu-id="d6a62-307">x86</span><span class="sxs-lookup"><span data-stu-id="d6a62-307">x64,</span></span>            |

<span data-ttu-id="d6a62-308">Para obter mais informações sobre OS sistemas operacionais, as distribuições e a política de ciclo de vida com suporte do .NET Core 2,1, consulte [versões do sistema operacional .net core 2,1 com suporte](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-308">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="d6a62-309">Windows 7/Vista/8,1/servidor 2008 R2/Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6a62-309">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="d6a62-310">Dependências adicionais serão necessárias se você estiver instalando o SDK do .NET ou o tempo de execução nas seguintes versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="d6a62-310">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="d6a62-311">[ESU][esu] do Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="d6a62-311">Windows 7 SP1 [ESU][esu]</span></span>
- <span data-ttu-id="d6a62-312">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="d6a62-312">Windows Vista SP 2</span></span>
- <span data-ttu-id="d6a62-313">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-313">Windows 8.1</span></span>
- <span data-ttu-id="d6a62-314">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d6a62-314">Windows Server 2008 R2</span></span>
- <span data-ttu-id="d6a62-315">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6a62-315">Windows Server 2012 R2</span></span>

<span data-ttu-id="d6a62-316">Instale o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6a62-316">Install the following:</span></span>

- <span data-ttu-id="d6a62-317">[Microsoft Visual C++ 2015 redistribuível atualização 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="d6a62-317">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="d6a62-318">KB2533623</span><span class="sxs-lookup"><span data-stu-id="d6a62-318">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="d6a62-319">Os requisitos anteriores também serão necessários se você vir entre um dos seguintes erros:</span><span class="sxs-lookup"><span data-stu-id="d6a62-319">The previous requirements are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="d6a62-320">O programa não pode ser iniciado porque *api-ms-win-crt-runtime-l1-1-0.dll* está ausente do seu computador.</span><span class="sxs-lookup"><span data-stu-id="d6a62-320">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="d6a62-321">Tente reinstalar o programa para corrigir esse problema.</span><span class="sxs-lookup"><span data-stu-id="d6a62-321">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="d6a62-322">\- ou –</span><span class="sxs-lookup"><span data-stu-id="d6a62-322">\- or -</span></span>
>
> <span data-ttu-id="d6a62-323">O programa não pode ser iniciado porque *api-ms-win-cor-timezone-l1-1-0.dll* está ausente do seu computador.</span><span class="sxs-lookup"><span data-stu-id="d6a62-323">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="d6a62-324">Tente reinstalar o programa para corrigir esse problema.</span><span class="sxs-lookup"><span data-stu-id="d6a62-324">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="d6a62-325">\- ou –</span><span class="sxs-lookup"><span data-stu-id="d6a62-325">\- or -</span></span>
>
> <span data-ttu-id="d6a62-326">A biblioteca *hostfxr.dll* foi encontrada, mas o carregamento de *C: \\ \<path_to_app> \\hostfxr.dll* falhou.</span><span class="sxs-lookup"><span data-stu-id="d6a62-326">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="d6a62-327">Instalar com a automação do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6a62-327">Install with PowerShell automation</span></span>

<span data-ttu-id="d6a62-328">Os [scripts dotnet-install](../tools/dotnet-install-script.md) são usados para a automação CI e para instalações não administrativas do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d6a62-328">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="d6a62-329">Você pode baixar o script na [página de referência de script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-329">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="d6a62-330">O script assume como padrão a instalação da versão mais recente do [LTS (suporte a longo prazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , que é o .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="d6a62-330">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d6a62-331">Você pode escolher uma versão específica especificando a `Channel` opção.</span><span class="sxs-lookup"><span data-stu-id="d6a62-331">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="d6a62-332">Inclua a `Runtime` opção para instalar um tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d6a62-332">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="d6a62-333">Caso contrário, o script instalará o SDK.</span><span class="sxs-lookup"><span data-stu-id="d6a62-333">Otherwise, the script installs the SDK.</span></span>

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

<span data-ttu-id="d6a62-334">Instale o SDK omitindo a `-Runtime` opção.</span><span class="sxs-lookup"><span data-stu-id="d6a62-334">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="d6a62-335">A `-Channel` opção é definida neste exemplo como `Current` , que instala a versão mais recente com suporte.</span><span class="sxs-lookup"><span data-stu-id="d6a62-335">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="d6a62-336">Instalar com o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d6a62-336">Install with Visual Studio</span></span>

<span data-ttu-id="d6a62-337">Se você estiver usando o Visual Studio para desenvolver aplicativos .NET, a tabela a seguir descreve a versão mínima necessária do Visual Studio com base na versão do SDK do .NET de destino.</span><span class="sxs-lookup"><span data-stu-id="d6a62-337">If you're using Visual Studio to develop .NET apps, the following table describes the minimum required version of Visual Studio based on the target .NET SDK version.</span></span>

| <span data-ttu-id="d6a62-338">Versão do SDK do .NET</span><span class="sxs-lookup"><span data-stu-id="d6a62-338">.NET SDK version</span></span>      | <span data-ttu-id="d6a62-339">Versão do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d6a62-339">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="d6a62-340">5.0</span><span class="sxs-lookup"><span data-stu-id="d6a62-340">5.0</span></span>                   | <span data-ttu-id="d6a62-341">Visual Studio 2019 versão 16,8 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d6a62-341">Visual Studio 2019 version 16.8 or higher.</span></span> |
| <span data-ttu-id="d6a62-342">3.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-342">3.1</span></span>                   | <span data-ttu-id="d6a62-343">Visual Studio 2019 versão 16,4 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d6a62-343">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="d6a62-344">3.0</span><span class="sxs-lookup"><span data-stu-id="d6a62-344">3.0</span></span>                   | <span data-ttu-id="d6a62-345">Visual Studio 2019 versão 16,3 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d6a62-345">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="d6a62-346">2.2</span><span class="sxs-lookup"><span data-stu-id="d6a62-346">2.2</span></span>                   | <span data-ttu-id="d6a62-347">Visual Studio 2017 versão 15,9 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d6a62-347">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="d6a62-348">2.1</span><span class="sxs-lookup"><span data-stu-id="d6a62-348">2.1</span></span>                   | <span data-ttu-id="d6a62-349">Visual Studio 2017 versão 15,7 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d6a62-349">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="d6a62-350">Se você já tiver o Visual Studio instalado, poderá verificar sua versão com as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6a62-350">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="d6a62-351">Abra o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6a62-351">Open Visual Studio.</span></span>
01. <span data-ttu-id="d6a62-352">Selecione **ajuda**  >  **sobre Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="d6a62-352">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="d6a62-353">Leia o número de versão na caixa de diálogo **sobre** .</span><span class="sxs-lookup"><span data-stu-id="d6a62-353">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="d6a62-354">O Visual Studio pode instalar o SDK e o tempo de execução do .NET mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d6a62-354">Visual Studio can install the latest .NET SDK and runtime.</span></span>

> [!div class="button"]
> <span data-ttu-id="d6a62-355">[Baixe o Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="d6a62-355">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="d6a62-356">Selecionar uma carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="d6a62-356">Select a workload</span></span>

<span data-ttu-id="d6a62-357">Ao instalar ou modificar o Visual Studio, selecione uma ou mais das cargas de trabalho a seguir, dependendo do tipo de aplicativo que você está criando:</span><span class="sxs-lookup"><span data-stu-id="d6a62-357">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="d6a62-358">A carga de trabalho de **desenvolvimento de plataforma cruzada do .NET Core** na seção **outros conjuntos de ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="d6a62-358">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="d6a62-359">A carga de trabalho de **desenvolvimento da Web e ASP.net** na seção **Web & nuvem** .</span><span class="sxs-lookup"><span data-stu-id="d6a62-359">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="d6a62-360">A carga de trabalho de **desenvolvimento do Azure** na seção **Web & nuvem** .</span><span class="sxs-lookup"><span data-stu-id="d6a62-360">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="d6a62-361">A carga de trabalho **.net desktop Development** na seção **Desktop & Mobile** .</span><span class="sxs-lookup"><span data-stu-id="d6a62-361">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="d6a62-362">[![Carga de trabalho do Windows Visual Studio 2019 com .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d6a62-362">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="d6a62-363">Instalar junto com Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d6a62-363">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="d6a62-364">Visual Studio Code é um editor de código-fonte leve e avançado que é executado em sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d6a62-364">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="d6a62-365">Visual Studio Code está disponível para Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="d6a62-365">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="d6a62-366">Embora Visual Studio Code não venha com um instalador .NET Core automatizado como o Visual Studio, adicionar o suporte ao .NET Core é simples.</span><span class="sxs-lookup"><span data-stu-id="d6a62-366">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="d6a62-367">[Baixe e instale o Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="d6a62-367">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="d6a62-368">[Baixe e instale o SDK do .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="d6a62-368">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="d6a62-369">[Instale a extensão C# do Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="d6a62-369">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="d6a62-370">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="d6a62-370">Windows Installer</span></span>

<span data-ttu-id="d6a62-371">A [página de download](https://dotnet.microsoft.com/download/dotnet-core) do .net fornece Windows Installer executáveis.</span><span class="sxs-lookup"><span data-stu-id="d6a62-371">The [download page](https://dotnet.microsoft.com/download/dotnet-core) for .NET provides Windows Installer executables.</span></span>

<span data-ttu-id="d6a62-372">Ao usar os arquivos MSI para instalar o .NET< você pode personalizar o caminho de instalação definindo os `DOTNETHOME_X64` `DOTNETHOME_X86` parâmetros e:</span><span class="sxs-lookup"><span data-stu-id="d6a62-372">When you use the MSI files to install .NET< you can customize the installation path by setting the `DOTNETHOME_X64` and `DOTNETHOME_X86` parameters:</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe DOTNETHOME_X64="F:\dotnet\x64" DOTNETHOME_X86="F:\dotnet\x86"
```

## <a name="download-and-manually-install"></a><span data-ttu-id="d6a62-373">Baixar e instalar manualmente</span><span class="sxs-lookup"><span data-stu-id="d6a62-373">Download and manually install</span></span>

<span data-ttu-id="d6a62-374">Como alternativa para os instaladores do Windows para .NET, você pode baixar e instalar manualmente o SDK ou o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d6a62-374">As an alternative to the Windows installers for .NET, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="d6a62-375">A instalação manual geralmente é executada como parte do teste de integração contínua.</span><span class="sxs-lookup"><span data-stu-id="d6a62-375">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="d6a62-376">Para um desenvolvedor ou usuário, geralmente é melhor usar um [instalador](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="d6a62-376">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="d6a62-377">Tanto o SDK do .NET quanto o tempo de execução do .NET podem ser instalados manualmente após terem sido baixados.</span><span class="sxs-lookup"><span data-stu-id="d6a62-377">Both .NET SDK and .NET Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="d6a62-378">Se você instalar o SDK do .NET, não precisará instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="d6a62-378">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="d6a62-379">Primeiro, Baixe uma versão binária para o SDK ou o tempo de execução de um dos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="d6a62-379">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- [<span data-ttu-id="d6a62-380">Downloads do .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="d6a62-380">.NET 5.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- [<span data-ttu-id="d6a62-381">Downloads do .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-381">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="d6a62-382">Downloads do .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="d6a62-382">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [<span data-ttu-id="d6a62-383">Todos os downloads do .NET Core</span><span class="sxs-lookup"><span data-stu-id="d6a62-383">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="d6a62-384">Crie um diretório para extrair o .NET, por exemplo `%USERPROFILE%\dotnet` .</span><span class="sxs-lookup"><span data-stu-id="d6a62-384">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="d6a62-385">Em seguida, extraia o arquivo zip baixado para esse diretório.</span><span class="sxs-lookup"><span data-stu-id="d6a62-385">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="d6a62-386">Por padrão, os comandos e aplicativos da CLI do .NET não usarão o .NET instalado dessa forma e você deverá optar por usá-lo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="d6a62-386">By default, .NET CLI commands and apps won't use .NET installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="d6a62-387">Para fazer isso, altere as variáveis de ambiente com as quais um aplicativo é iniciado:</span><span class="sxs-lookup"><span data-stu-id="d6a62-387">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="d6a62-388">Essa abordagem permite que você instale várias versões em locais separados e escolha explicitamente qual local de instalação um aplicativo deve usar executando o aplicativo com variáveis de ambiente apontando para esse local.</span><span class="sxs-lookup"><span data-stu-id="d6a62-388">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="d6a62-389">Quando `DOTNET_MULTILEVEL_LOOKUP` é definido como `0` , o .net ignora qualquer versão do .net instalada globalmente.</span><span class="sxs-lookup"><span data-stu-id="d6a62-389">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET ignores any globally installed .NET version.</span></span> <span data-ttu-id="d6a62-390">Remova essa configuração de ambiente para permitir que o .NET considere o local de instalação global padrão ao selecionar a melhor estrutura para executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6a62-390">Remove that environment setting to let .NET consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="d6a62-391">O padrão é normalmente `C:\Program Files\dotnet` , que é onde os instaladores instalam o .net.</span><span class="sxs-lookup"><span data-stu-id="d6a62-391">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET.</span></span>

## <a name="docker"></a><span data-ttu-id="d6a62-392">Docker</span><span class="sxs-lookup"><span data-stu-id="d6a62-392">Docker</span></span>

<span data-ttu-id="d6a62-393">Os contêineres fornecem uma maneira leve de isolar seu aplicativo do restante do sistema host.</span><span class="sxs-lookup"><span data-stu-id="d6a62-393">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="d6a62-394">Os contêineres no mesmo computador compartilham apenas o kernel e usam os recursos fornecidos ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6a62-394">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="d6a62-395">O .NET pode ser executado em um contêiner do Docker.</span><span class="sxs-lookup"><span data-stu-id="d6a62-395">.NET can run in a Docker container.</span></span> <span data-ttu-id="d6a62-396">As imagens oficiais do Docker do .NET são publicadas no MCR (registro de contêiner da Microsoft) e podem ser descobertas no [repositório do Microsoft .net Docker Hub](https://hub.docker.com/_/microsoft-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d6a62-396">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet).</span></span> <span data-ttu-id="d6a62-397">Cada repositório contém imagens para diferentes combinações do .NET (SDK ou Runtime) e do sistema operacional que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="d6a62-397">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="d6a62-398">A Microsoft fornece imagens personalizadas para cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="d6a62-398">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="d6a62-399">Por exemplo, o [repositório do ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) fornece imagens que são criadas para a execução de aplicativos ASP.NET Core na produção.</span><span class="sxs-lookup"><span data-stu-id="d6a62-399">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="d6a62-400">Para obter mais informações sobre como usar o .NET em um contêiner do Docker, consulte [introdução ao .net e ao Docker](../docker/introduction.md) e [amostras](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-400">For more information about using .NET in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6a62-401">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d6a62-401">Next steps</span></span>

- <span data-ttu-id="d6a62-402">[Como verificar se o .net já está instalado](how-to-detect-installed-versions.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d6a62-402">[How to check if .NET is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="d6a62-403">[Tutorial: tutorial de Olá, mundo](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-403">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="d6a62-404">[Tutorial: criar um novo aplicativo com Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-404">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="d6a62-405">[Tutorial: colocar em contêiner um aplicativo .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="d6a62-405">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[esu]: /troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq
