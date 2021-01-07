---
title: Instalar o .NET no RHEL-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no RHEL.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: d585017919507a8fdcbb24778a0ff3ab3d9049c2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970792"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="fc65d-103">Instalar o SDK do .NET ou o tempo de execução do .NET no RHEL</span><span class="sxs-lookup"><span data-stu-id="fc65d-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="fc65d-104">O .NET tem suporte no RHEL.</span><span class="sxs-lookup"><span data-stu-id="fc65d-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="fc65d-105">Este artigo descreve como instalar o .NET no RHEL.</span><span class="sxs-lookup"><span data-stu-id="fc65d-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="fc65d-106">Registrar sua assinatura do Red Hat</span><span class="sxs-lookup"><span data-stu-id="fc65d-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="fc65d-107">Para instalar o .NET do Red Hat no RHEL, primeiro você precisa se registrar usando o Gerenciador de assinaturas do Red Hat.</span><span class="sxs-lookup"><span data-stu-id="fc65d-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="fc65d-108">Se isso não tiver sido feito em seu sistema ou se você não tiver certeza, consulte a [documentação do produto Red Hat para .net](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="fc65d-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="fc65d-109">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="fc65d-109">Supported distributions</span></span>

<span data-ttu-id="fc65d-110">A tabela a seguir é uma lista de versões do .NET com suporte no momento no RHEL 7 e RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="fc65d-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="fc65d-111">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do RHEL não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="fc65d-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="fc65d-112">Um ✔️ indica que a versão do RHEL ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="fc65d-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="fc65d-113">Um ❌ indica que a versão do RHEL ou .net não tem suporte nessa versão do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fc65d-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="fc65d-114">Quando uma versão do RHEL e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="fc65d-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="fc65d-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="fc65d-115">RHEL</span></span>                     | <span data-ttu-id="fc65d-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fc65d-116">.NET Core 2.1</span></span> | <span data-ttu-id="fc65d-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fc65d-117">.NET Core 3.1</span></span> | <span data-ttu-id="fc65d-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fc65d-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="fc65d-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="fc65d-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="fc65d-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fc65d-120">✔️ 2.1</span></span>        | <span data-ttu-id="fc65d-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="fc65d-121">✔️ 3.1</span></span>        | <span data-ttu-id="fc65d-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="fc65d-122">✔️ 5.0</span></span> |
| <span data-ttu-id="fc65d-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="fc65d-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="fc65d-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fc65d-124">✔️ 2.1</span></span>        | <span data-ttu-id="fc65d-125">✔️ [3,1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="fc65d-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="fc65d-126">✔️ [5,0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="fc65d-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="fc65d-127">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="fc65d-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="fc65d-128">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="fc65d-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="fc65d-129">3.0</span><span class="sxs-lookup"><span data-stu-id="fc65d-129">3.0</span></span>
- <span data-ttu-id="fc65d-130">2.2</span><span class="sxs-lookup"><span data-stu-id="fc65d-130">2.2</span></span>
- <span data-ttu-id="fc65d-131">2,0</span><span class="sxs-lookup"><span data-stu-id="fc65d-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="fc65d-132">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="fc65d-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="rhel-8-"></a><span data-ttu-id="fc65d-133">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="fc65d-133">RHEL 8 ✔️</span></span>

<span data-ttu-id="fc65d-134">O .NET está incluído nos repositórios do AppStream para RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="fc65d-134">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="fc65d-135">RHEL 7 ✔️ .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="fc65d-135">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="fc65d-136">O comando a seguir instala o `scl-utils` pacote:</span><span class="sxs-lookup"><span data-stu-id="fc65d-136">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="fc65d-137">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="fc65d-137">Install the SDK</span></span>

<span data-ttu-id="fc65d-138">O SDK do .NET permite que você desenvolva aplicativos com o .NET.</span><span class="sxs-lookup"><span data-stu-id="fc65d-138">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="fc65d-139">Se você instalar o SDK do .NET, não precisará instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="fc65d-139">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="fc65d-140">Para instalar o SDK do .NET, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fc65d-140">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="fc65d-141">O Red Hat não recomenda a habilitação permanente `rh-dotnet50` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fc65d-141">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="fc65d-142">Se você quiser habilitar `rh-dotnet` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fc65d-142">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="fc65d-143">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="fc65d-143">Install the runtime</span></span>

<span data-ttu-id="fc65d-144">O tempo de execução do .NET permite executar aplicativos que foram feitos com o .NET que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="fc65d-144">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="fc65d-145">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc65d-145">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="fc65d-146">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc65d-146">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="fc65d-147">O Red Hat não recomenda a habilitação permanente `rh-dotnet50` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fc65d-147">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="fc65d-148">Se você quiser habilitar `rh-dotnet50` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fc65d-148">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="fc65d-149">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET que não inclui suporte a ASP.NET Core: substitua `rh-dotnet50-aspnetcore-runtime-5.0` nos comandos acima por `rh-dotnet50-dotnet-runtime-5.0` .</span><span class="sxs-lookup"><span data-stu-id="fc65d-149">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="fc65d-150">RHEL 7 ✔️ .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="fc65d-150">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="fc65d-151">O comando a seguir instala o `scl-utils` pacote:</span><span class="sxs-lookup"><span data-stu-id="fc65d-151">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="fc65d-152">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="fc65d-152">Install the SDK</span></span>

<span data-ttu-id="fc65d-153">SDK do .NET Core permite que você desenvolva aplicativos com o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc65d-153">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="fc65d-154">Se você instalar SDK do .NET Core, não será necessário instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="fc65d-154">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="fc65d-155">Para instalar o SDK do .NET Core, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fc65d-155">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="fc65d-156">O Red Hat não recomenda a habilitação permanente `rh-dotnet31` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fc65d-156">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="fc65d-157">Por exemplo, `rh-dotnet31` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fc65d-157">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="fc65d-158">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="fc65d-158">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="fc65d-159">Se você quiser habilitar `rh-dotnet` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fc65d-159">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="fc65d-160">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="fc65d-160">Install the runtime</span></span>

<span data-ttu-id="fc65d-161">O tempo de execução do .NET Core permite executar aplicativos que foram feitos com o .NET Core que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="fc65d-161">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="fc65d-162">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc65d-162">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="fc65d-163">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc65d-163">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="fc65d-164">O Red Hat não recomenda a habilitação permanente `rh-dotnet31` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fc65d-164">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="fc65d-165">Por exemplo, `rh-dotnet31` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fc65d-165">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="fc65d-166">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="fc65d-166">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="fc65d-167">Se você quiser habilitar `rh-dotnet31` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fc65d-167">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="fc65d-168">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET Core que não inclui suporte a ASP.NET Core: substitua `rh-dotnet31-aspnetcore-runtime-3.1` nos comandos acima por `rh-dotnet31-dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="fc65d-168">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="dependencies"></a><span data-ttu-id="fc65d-169">Dependências</span><span class="sxs-lookup"><span data-stu-id="fc65d-169">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fc65d-170">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="fc65d-170">How to install other versions</span></span>

<span data-ttu-id="fc65d-171">Consulte a [documentação do Red Hat para .net](https://access.redhat.com/documentation/net/5.0/) nas etapas necessárias para instalar outras versões do .net.</span><span class="sxs-lookup"><span data-stu-id="fc65d-171">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc65d-172">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fc65d-172">Next steps</span></span>

- [<span data-ttu-id="fc65d-173">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="fc65d-173">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="fc65d-174">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fc65d-174">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
