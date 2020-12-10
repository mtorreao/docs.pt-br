---
title: Instalar o .NET no macOS
description: Saiba mais sobre quais versões do macOS você pode instalar o .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b1434938a8e8e81da81e495a6b99e6c99467aae1
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009352"
---
# <a name="install-net-on-macos"></a><span data-ttu-id="95342-103">Instalar o .NET no macOS</span><span class="sxs-lookup"><span data-stu-id="95342-103">Install .NET on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Instalar no Windows](windows.md)
> - [Instalar no macOS](macos.md)
> - [Instalar no Linux](linux.md)

<span data-ttu-id="95342-107">Neste artigo, você aprenderá a instalar o .NET no macOS.</span><span class="sxs-lookup"><span data-stu-id="95342-107">In this article, you'll learn how to install .NET on macOS.</span></span> <span data-ttu-id="95342-108">O .NET é constituído do tempo de execução e do SDK.</span><span class="sxs-lookup"><span data-stu-id="95342-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="95342-109">O tempo de execução é usado para executar um aplicativo .NET e pode ou não ser incluído com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95342-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="95342-110">O SDK é usado para criar aplicativos e bibliotecas .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="95342-111">O tempo de execução do .NET é sempre instalado com o SDK.</span><span class="sxs-lookup"><span data-stu-id="95342-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="95342-112">A versão mais recente do .NET é 5,0.</span><span class="sxs-lookup"><span data-stu-id="95342-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="95342-113">Baixe o .NET Core</span><span class="sxs-lookup"><span data-stu-id="95342-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="95342-114">Versões com suporte</span><span class="sxs-lookup"><span data-stu-id="95342-114">Supported releases</span></span>

<span data-ttu-id="95342-115">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do macOS nas quais elas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="95342-115">The following table is a list of currently supported .NET releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="95342-116">Essas versões permanecem com suporte, ou seja, a versão do [.net atinge o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="95342-116">These versions remain supported either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="95342-117">Um ✔️ indica que a versão do .NET Core ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="95342-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="95342-118">Um ❌ indica que a versão do .NET Core não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="95342-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="95342-119">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="95342-119">Operating System</span></span>          | <span data-ttu-id="95342-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="95342-120">.NET Core 2.1</span></span> | <span data-ttu-id="95342-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="95342-121">.NET Core 3.1</span></span> | <span data-ttu-id="95342-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="95342-122">.NET 5.0</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="95342-123">macOS 11,0 "Big Sur"</span><span class="sxs-lookup"><span data-stu-id="95342-123">macOS 11.0 "Big Sur"</span></span>        | <span data-ttu-id="95342-124">✔️ 2,1 ([notas de versão][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="95342-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="95342-125">✔️ 3,1 ([notas de versão][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="95342-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="95342-126">✔️ 5,0 ([notas de versão][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="95342-126">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="95342-127">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="95342-127">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="95342-128">✔️ 2,1 ([notas de versão][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="95342-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="95342-129">✔️ 3,1 ([notas de versão][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="95342-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="95342-130">✔️ 5,0 ([notas de versão][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="95342-130">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="95342-131">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="95342-131">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="95342-132">✔️ 2,1 ([notas de versão][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="95342-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="95342-133">✔️ 3,1 ([notas de versão][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="95342-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="95342-134">✔️ 5,0 ([notas de versão][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="95342-134">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="95342-135">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="95342-135">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="95342-136">✔️ 2,1 ([notas de versão][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="95342-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="95342-137">✔️ 3,1 ([notas de versão][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="95342-137">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="95342-138">✔️ 5,0 ([notas de versão][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="95342-138">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="95342-139">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="95342-139">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="95342-140">✔️ 2,1 ([notas de versão][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="95342-140">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="95342-141">❌ 3,1 ([notas de versão][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="95342-141">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="95342-142">❌ 5,0 ([notas de versão][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="95342-142">❌ 5.0 ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="95342-143">Versões sem suporte</span><span class="sxs-lookup"><span data-stu-id="95342-143">Unsupported releases</span></span>

<span data-ttu-id="95342-144">Não há mais suporte para as seguintes versões do .NET ❌ .</span><span class="sxs-lookup"><span data-stu-id="95342-144">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="95342-145">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="95342-145">The downloads for these still remain published:</span></span>

- <span data-ttu-id="95342-146">3,0 ([notas de versão][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="95342-146">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="95342-147">2,2 ([notas de versão][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="95342-147">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="95342-148">2,0 ([notas de versão][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="95342-148">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="95342-149">Informações de tempo de execução</span><span class="sxs-lookup"><span data-stu-id="95342-149">Runtime information</span></span>

<span data-ttu-id="95342-150">O tempo de execução é usado para executar aplicativos criados com o .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-150">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="95342-151">Quando um autor de aplicativo publica um aplicativo, ele pode incluir o tempo de execução com seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95342-151">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="95342-152">Se eles não incluírem o tempo de execução, cabe ao usuário instalar o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="95342-152">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="95342-153">Há três tempos de execução diferentes que você pode instalar no macOS:</span><span class="sxs-lookup"><span data-stu-id="95342-153">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="95342-154">*Tempo de execução ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="95342-154">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="95342-155">Executa ASP.NET Core aplicativos.</span><span class="sxs-lookup"><span data-stu-id="95342-155">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="95342-156">Inclui o tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-156">Includes the .NET runtime.</span></span>

<span data-ttu-id="95342-157">*Tempo de execução do .NET*</span><span class="sxs-lookup"><span data-stu-id="95342-157">*.NET runtime*</span></span>\
<span data-ttu-id="95342-158">Esse tempo de execução é o tempo de execução mais simples e não inclui nenhum outro tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="95342-158">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="95342-159">É altamente recomendável que você instale *ASP.NET Core tempo de execução* para obter a melhor compatibilidade com aplicativos .net.</span><span class="sxs-lookup"><span data-stu-id="95342-159">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="95342-160">Baixar o tempo de execução do .NET</span><span class="sxs-lookup"><span data-stu-id="95342-160">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="95342-161">Informações do SDK</span><span class="sxs-lookup"><span data-stu-id="95342-161">SDK information</span></span>

<span data-ttu-id="95342-162">O SDK é usado para compilar e publicar aplicativos e bibliotecas .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-162">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="95342-163">A instalação do SDK inclui ambos os [tempos de execução](#runtime-information): ASP.NET Core e .net.</span><span class="sxs-lookup"><span data-stu-id="95342-163">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="95342-164">Dependências</span><span class="sxs-lookup"><span data-stu-id="95342-164">Dependencies</span></span>

<span data-ttu-id="95342-165">O .NET tem suporte nas seguintes versões do macOS:</span><span class="sxs-lookup"><span data-stu-id="95342-165">.NET is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="95342-166">Um `+` símbolo representa a versão mínima.</span><span class="sxs-lookup"><span data-stu-id="95342-166">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="95342-167">Versão do .NET Core</span><span class="sxs-lookup"><span data-stu-id="95342-167">.NET Core Version</span></span> | <span data-ttu-id="95342-168">macOS</span><span class="sxs-lookup"><span data-stu-id="95342-168">macOS</span></span>                 | <span data-ttu-id="95342-169">Arquiteturas</span><span class="sxs-lookup"><span data-stu-id="95342-169">Architectures</span></span> | <span data-ttu-id="95342-170">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-170">More information</span></span>    |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="95342-171">5.0</span><span class="sxs-lookup"><span data-stu-id="95342-171">5.0</span></span>               | <span data-ttu-id="95342-172">Alta serra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="95342-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="95342-173">x64</span><span class="sxs-lookup"><span data-stu-id="95342-173">x64</span></span> | [<span data-ttu-id="95342-174">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) |
| <span data-ttu-id="95342-175">3.1</span><span class="sxs-lookup"><span data-stu-id="95342-175">3.1</span></span>               | <span data-ttu-id="95342-176">Alta serra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="95342-176">High Sierra (10.13+)</span></span>  | <span data-ttu-id="95342-177">x64</span><span class="sxs-lookup"><span data-stu-id="95342-177">x64</span></span> | [<span data-ttu-id="95342-178">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="95342-179">3.0</span><span class="sxs-lookup"><span data-stu-id="95342-179">3.0</span></span>               | <span data-ttu-id="95342-180">Alta serra (10.13 +)</span><span class="sxs-lookup"><span data-stu-id="95342-180">High Sierra (10.13+)</span></span>  | <span data-ttu-id="95342-181">x64</span><span class="sxs-lookup"><span data-stu-id="95342-181">x64</span></span> | [<span data-ttu-id="95342-182">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="95342-183">2.2</span><span class="sxs-lookup"><span data-stu-id="95342-183">2.2</span></span>               | <span data-ttu-id="95342-184">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="95342-184">Sierra (10.12+)</span></span>       | <span data-ttu-id="95342-185">x64</span><span class="sxs-lookup"><span data-stu-id="95342-185">x64</span></span> | [<span data-ttu-id="95342-186">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-186">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="95342-187">2.1</span><span class="sxs-lookup"><span data-stu-id="95342-187">2.1</span></span>               | <span data-ttu-id="95342-188">Sierra (10.12 +)</span><span class="sxs-lookup"><span data-stu-id="95342-188">Sierra (10.12+)</span></span>       | <span data-ttu-id="95342-189">x64</span><span class="sxs-lookup"><span data-stu-id="95342-189">x64</span></span> | [<span data-ttu-id="95342-190">Mais informações</span><span class="sxs-lookup"><span data-stu-id="95342-190">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="95342-191">A partir do macOS Catalina (versão 10,15), todo software criado após 1º de junho de 2019 que é distribuído com a ID do desenvolvedor deve ser notarized.</span><span class="sxs-lookup"><span data-stu-id="95342-191">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="95342-192">Esse requisito se aplica ao tempo de execução do .NET, ao SDK do .NET e ao software criado com o .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-192">This requirement applies to the .NET runtime, .NET SDK, and software created with .NET.</span></span>

<span data-ttu-id="95342-193">Os instaladores de tempo de execução e SDK para .NET 5,0 e .NET Core 3,1, 3,0 e 2,1, foram notarizeddos desde 18 de fevereiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="95342-193">The runtime and SDK installers for .NET 5.0 and .NET Core 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="95342-194">Versões anteriores liberadas não são notarized.</span><span class="sxs-lookup"><span data-stu-id="95342-194">Prior released versions aren't notarized.</span></span> <span data-ttu-id="95342-195">Se você executar um aplicativo não notarized, verá um erro semelhante à imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="95342-195">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![alerta de notarization Catalina do macOS](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="95342-197">Para obter mais informações sobre como o imforced-notarization afeta o .NET (e seus aplicativos .NET), consulte [trabalhando com o MacOS Catalina notarization](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="95342-197">For more information about how enforced-notarization affects .NET (and your .NET apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="95342-198">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="95342-198">libgdiplus</span></span>

<span data-ttu-id="95342-199">Os aplicativos .NET que usam o assembly *System. sorteio. Common* exigem que o libgdiplus seja instalado.</span><span class="sxs-lookup"><span data-stu-id="95342-199">.NET applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="95342-200">Uma maneira fácil de obter o libgdiplus é usando o Gerenciador de pacotes [homebrew ("Brew")](https://brew.sh/) para MacOS.</span><span class="sxs-lookup"><span data-stu-id="95342-200">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="95342-201">Depois de instalar o *Brew*, instale o libgdiplus executando os seguintes comandos em um prompt de terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="95342-201">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="95342-202">Instalar com um instalador</span><span class="sxs-lookup"><span data-stu-id="95342-202">Install with an installer</span></span>

<span data-ttu-id="95342-203">o macOS tem instaladores autônomos que podem ser usados para instalar o SDK do .NET 5,0:</span><span class="sxs-lookup"><span data-stu-id="95342-203">macOS has standalone installers that can be used to install the .NET 5.0 SDK:</span></span>

- [<span data-ttu-id="95342-204">CPUs x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="95342-204">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/5.0)

## <a name="download-and-manually-install"></a><span data-ttu-id="95342-205">Baixar e instalar manualmente</span><span class="sxs-lookup"><span data-stu-id="95342-205">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="95342-206">Como alternativa para os instaladores do macOS para .NET, você pode baixar e instalar manualmente o SDK e o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="95342-206">As an alternative to the macOS installers for .NET, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="95342-207">A instalação manual geralmente é executada como parte do teste de integração contínua.</span><span class="sxs-lookup"><span data-stu-id="95342-207">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="95342-208">Para um desenvolvedor ou usuário, geralmente é melhor usar um [instalador](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="95342-208">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="95342-209">Se você instalar o SDK do .NET, não precisará instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="95342-209">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="95342-210">Primeiro, Baixe uma versão **binária** para o SDK ou o tempo de execução de um dos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="95342-210">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="95342-211">downloads do ✔️ [.net 5,0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="95342-211">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="95342-212">downloads do ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="95342-212">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="95342-213">downloads do ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="95342-213">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="95342-214">Todos os downloads do .NET Core</span><span class="sxs-lookup"><span data-stu-id="95342-214">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="95342-215">Em seguida, extraia o arquivo baixado e use o `export` comando para definir as variáveis usadas pelo .net e, em seguida, verifique se o .net está no caminho.</span><span class="sxs-lookup"><span data-stu-id="95342-215">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="95342-216">Para extrair o tempo de execução e tornar os comandos da CLI do .NET disponíveis no terminal, primeiro Baixe uma versão binária do .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-216">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="95342-217">Em seguida, abra um terminal e execute os seguintes comandos no diretório em que o arquivo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="95342-217">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="95342-218">O nome do arquivo morto pode ser diferente dependendo do que você baixou.</span><span class="sxs-lookup"><span data-stu-id="95342-218">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="95342-219">**Use o seguinte comando para extrair o tempo de execução**:</span><span class="sxs-lookup"><span data-stu-id="95342-219">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="95342-220">**Use o seguinte comando para extrair o SDK**:</span><span class="sxs-lookup"><span data-stu-id="95342-220">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="95342-221">Os `export` comandos anteriores tornam os comandos da CLI do .net disponíveis para a sessão de terminal na qual ele foi executado.</span><span class="sxs-lookup"><span data-stu-id="95342-221">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="95342-222">Você pode editar seu perfil de Shell para adicionar os comandos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="95342-222">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="95342-223">Há vários shells diferentes disponíveis para o Linux e cada um deles tem um perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="95342-223">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="95342-224">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95342-224">For example:</span></span>
>
> - <span data-ttu-id="95342-225">**Shell bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="95342-225">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="95342-226">**Shell Korn**: *~/.Kshrc* ou *. Profile*</span><span class="sxs-lookup"><span data-stu-id="95342-226">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="95342-227">**Shell Z**: *~/.zshrc* ou *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="95342-227">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="95342-228">Edite o arquivo de origem apropriado para o Shell e adicione `:$HOME/dotnet` ao final da `PATH` instrução existente.</span><span class="sxs-lookup"><span data-stu-id="95342-228">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="95342-229">Se nenhuma `PATH` instrução for incluída, adicione uma nova linha com `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="95342-229">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="95342-230">Além disso, adicione `export DOTNET_ROOT=$HOME/dotnet` ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="95342-230">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="95342-231">Essa abordagem permite que você instale versões diferentes em locais separados e escolha explicitamente qual deles usar por qual aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95342-231">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="95342-232">Instalar com o Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="95342-232">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="95342-233">Visual Studio para Mac instala o SDK do .NET quando a carga de trabalho do **.net** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="95342-233">Visual Studio for Mac installs the .NET SDK when the **.NET** workload is selected.</span></span> <span data-ttu-id="95342-234">Para começar a usar o desenvolvimento do .NET no macOS, consulte [instalar o Visual Studio 2019 para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="95342-234">To get started with .NET development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

| <span data-ttu-id="95342-235">Versão do SDK do .NET</span><span class="sxs-lookup"><span data-stu-id="95342-235">.NET SDK version</span></span>      | <span data-ttu-id="95342-236">Versão do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95342-236">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="95342-237">5.0</span><span class="sxs-lookup"><span data-stu-id="95342-237">5.0</span></span>                   | <span data-ttu-id="95342-238">Visual Studio 2019 para Mac versão 8,8 ou superior.</span><span class="sxs-lookup"><span data-stu-id="95342-238">Visual Studio 2019 for Mac version 8.8 or higher.</span></span> |
| <span data-ttu-id="95342-239">3.1</span><span class="sxs-lookup"><span data-stu-id="95342-239">3.1</span></span>                   | <span data-ttu-id="95342-240">Visual Studio 2019 para Mac versão 8,4 ou superior.</span><span class="sxs-lookup"><span data-stu-id="95342-240">Visual Studio 2019 for Mac version 8.4 or higher.</span></span> |
| <span data-ttu-id="95342-241">2.1</span><span class="sxs-lookup"><span data-stu-id="95342-241">2.1</span></span>                   | <span data-ttu-id="95342-242">Visual Studio 2019 para Mac versão 8,0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="95342-242">Visual Studio 2019 for Mac version 8.0 or higher.</span></span> |

<span data-ttu-id="95342-243">[![recurso macOS Visual Studio 2019 para Mac com carga de trabalho .NET](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="95342-243">[![macOS Visual Studio 2019 for Mac with .NET workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="95342-244">Instalar junto com Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="95342-244">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="95342-245">Visual Studio Code é um editor de código-fonte leve e avançado que é executado em sua área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="95342-245">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="95342-246">Visual Studio Code está disponível para Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="95342-246">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="95342-247">Embora Visual Studio Code não venha com um instalador .NET automatizado como o Visual Studio, é simples adicionar suporte ao .NET.</span><span class="sxs-lookup"><span data-stu-id="95342-247">While Visual Studio Code doesn't come with an automated .NET installer like Visual Studio does, adding .NET support is simple.</span></span>

01. <span data-ttu-id="95342-248">[Baixe e instale o Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="95342-248">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="95342-249">[Baixe e instale o SDK do .net](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="95342-249">[Download and install the .NET SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="95342-250">[Instale a extensão C# do Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="95342-250">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="95342-251">Instalar com a automação do bash</span><span class="sxs-lookup"><span data-stu-id="95342-251">Install with bash automation</span></span>

<span data-ttu-id="95342-252">Os [scripts dotnet-install](../tools/dotnet-install-script.md) são usados para automação e instalações não administrativas do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="95342-252">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="95342-253">Você pode baixar o script na [página de referência de script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="95342-253">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="95342-254">O script assume como padrão a instalação da versão mais recente do [LTS (suporte a longo prazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , que é o .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="95342-254">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="95342-255">Você pode escolher uma versão específica especificando a `current` opção.</span><span class="sxs-lookup"><span data-stu-id="95342-255">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="95342-256">Inclua a `runtime` opção para instalar um tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="95342-256">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="95342-257">Caso contrário, o script instalará o [SDK](./windows.md).</span><span class="sxs-lookup"><span data-stu-id="95342-257">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 5.0 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="95342-258">O comando anterior instala o tempo de execução de ASP.NET Core para compatibilidade máxima.</span><span class="sxs-lookup"><span data-stu-id="95342-258">The previous command installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="95342-259">O tempo de execução de ASP.NET Core também inclui o tempo de execução do .NET padrão.</span><span class="sxs-lookup"><span data-stu-id="95342-259">The ASP.NET Core runtime also includes the standard .NET runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="95342-260">Docker</span><span class="sxs-lookup"><span data-stu-id="95342-260">Docker</span></span>

<span data-ttu-id="95342-261">Os contêineres fornecem uma maneira leve de isolar seu aplicativo do restante do sistema host.</span><span class="sxs-lookup"><span data-stu-id="95342-261">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="95342-262">Os contêineres no mesmo computador compartilham apenas o kernel e usam os recursos fornecidos ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95342-262">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="95342-263">O .NET pode ser executado em um contêiner do Docker.</span><span class="sxs-lookup"><span data-stu-id="95342-263">.NET can run in a Docker container.</span></span> <span data-ttu-id="95342-264">As imagens oficiais do Docker do .NET são publicadas no MCR (registro de contêiner da Microsoft) e podem ser descobertas no [repositório do Hub do Docker do Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet/).</span><span class="sxs-lookup"><span data-stu-id="95342-264">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet/).</span></span> <span data-ttu-id="95342-265">Cada repositório contém imagens para diferentes combinações do .NET (SDK ou Runtime) e do sistema operacional que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="95342-265">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="95342-266">A Microsoft fornece imagens personalizadas para cenários específicos.</span><span class="sxs-lookup"><span data-stu-id="95342-266">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="95342-267">Por exemplo, o [repositório do ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) fornece imagens que são criadas para a execução de aplicativos ASP.NET Core na produção.</span><span class="sxs-lookup"><span data-stu-id="95342-267">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="95342-268">Para obter mais informações sobre como usar o .NET Core em um contêiner do Docker, consulte [introdução ao .net e ao Docker](../docker/introduction.md) e [amostras](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="95342-268">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="95342-269">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="95342-269">Next steps</span></span>

- <span data-ttu-id="95342-270">[Como verificar se o .NET Core já está instalado](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="95342-270">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="95342-271">[Trabalhando com o notarization Catalina do MacOS](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="95342-271">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="95342-272">[Tutorial: introdução ao MacOS](../tutorials/with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="95342-272">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="95342-273">[Tutorial: criar um novo aplicativo com Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="95342-273">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="95342-274">[Tutorial: colocar em contêiner um aplicativo .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="95342-274">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
