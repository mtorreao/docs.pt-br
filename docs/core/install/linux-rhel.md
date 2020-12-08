---
title: Instalar o .NET no RHEL-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851634"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="a6a41-103">Instalar o SDK do .NET ou o tempo de execução do .NET no RHEL</span><span class="sxs-lookup"><span data-stu-id="a6a41-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="a6a41-104">O .NET tem suporte no RHEL.</span><span class="sxs-lookup"><span data-stu-id="a6a41-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="a6a41-105">Este artigo descreve como instalar o .NET no RHEL.</span><span class="sxs-lookup"><span data-stu-id="a6a41-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="a6a41-106">Registrar sua assinatura do Red Hat</span><span class="sxs-lookup"><span data-stu-id="a6a41-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="a6a41-107">Para instalar o .NET do Red Hat no RHEL, primeiro você precisa se registrar usando o Gerenciador de assinaturas do Red Hat.</span><span class="sxs-lookup"><span data-stu-id="a6a41-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="a6a41-108">Se isso não tiver sido feito em seu sistema ou se você não tiver certeza, consulte a [documentação do produto Red Hat para .net](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="a6a41-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="a6a41-109">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="a6a41-109">Supported distributions</span></span>

<span data-ttu-id="a6a41-110">A tabela a seguir é uma lista de versões do .NET com suporte no momento no RHEL 7 e RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="a6a41-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="a6a41-111">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do RHEL não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="a6a41-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="a6a41-112">Um ✔️ indica que a versão do RHEL ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="a6a41-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="a6a41-113">Um ❌ indica que a versão do RHEL ou .net não tem suporte nessa versão do RHEL.</span><span class="sxs-lookup"><span data-stu-id="a6a41-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="a6a41-114">Quando uma versão do RHEL e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="a6a41-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a6a41-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="a6a41-115">RHEL</span></span>                     | <span data-ttu-id="a6a41-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a6a41-116">.NET Core 2.1</span></span> | <span data-ttu-id="a6a41-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a6a41-117">.NET Core 3.1</span></span> | <span data-ttu-id="a6a41-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a6a41-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a6a41-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="a6a41-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="a6a41-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a6a41-120">✔️ 2.1</span></span>        | <span data-ttu-id="a6a41-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a6a41-121">✔️ 3.1</span></span>        | <span data-ttu-id="a6a41-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a6a41-122">✔️ 5.0</span></span> |
| <span data-ttu-id="a6a41-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="a6a41-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="a6a41-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a6a41-124">✔️ 2.1</span></span>        | <span data-ttu-id="a6a41-125">✔️ [3,1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="a6a41-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="a6a41-126">✔️ [5,0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="a6a41-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="a6a41-127">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="a6a41-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a6a41-128">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="a6a41-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a6a41-129">3.0</span><span class="sxs-lookup"><span data-stu-id="a6a41-129">3.0</span></span>
- <span data-ttu-id="a6a41-130">2.2</span><span class="sxs-lookup"><span data-stu-id="a6a41-130">2.2</span></span>
- <span data-ttu-id="a6a41-131">2,0</span><span class="sxs-lookup"><span data-stu-id="a6a41-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="a6a41-132">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="a6a41-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a6a41-133">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="a6a41-133">How to install other versions</span></span>

<span data-ttu-id="a6a41-134">Consulte a [documentação do Red Hat para .net](https://access.redhat.com/documentation/net/5.0/) nas etapas necessárias para instalar outras versões do .net.</span><span class="sxs-lookup"><span data-stu-id="a6a41-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="a6a41-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="a6a41-135">RHEL 8 ✔️</span></span>

<span data-ttu-id="a6a41-136">O .NET está incluído nos repositórios do AppStream para RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="a6a41-136">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="a6a41-137">RHEL 7 ✔️ .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a6a41-137">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="a6a41-138">O comando a seguir instala o `scl-utils` pacote:</span><span class="sxs-lookup"><span data-stu-id="a6a41-138">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="a6a41-139">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="a6a41-139">Install the SDK</span></span>

<span data-ttu-id="a6a41-140">O SDK do .NET permite que você desenvolva aplicativos com o .NET.</span><span class="sxs-lookup"><span data-stu-id="a6a41-140">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="a6a41-141">Se você instalar o SDK do .NET, não precisará instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="a6a41-141">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a6a41-142">Para instalar o SDK do .NET, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a6a41-142">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="a6a41-143">O Red Hat não recomenda a habilitação permanente `rh-dotnet50` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="a6a41-143">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="a6a41-144">Se você quiser habilitar `rh-dotnet` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="a6a41-144">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="a6a41-145">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="a6a41-145">Install the runtime</span></span>

<span data-ttu-id="a6a41-146">O tempo de execução do .NET permite executar aplicativos que foram feitos com o .NET que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a6a41-146">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="a6a41-147">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6a41-147">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="a6a41-148">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6a41-148">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="a6a41-149">O Red Hat não recomenda a habilitação permanente `rh-dotnet50` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="a6a41-149">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="a6a41-150">Se você quiser habilitar `rh-dotnet50` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="a6a41-150">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="a6a41-151">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET que não inclui suporte a ASP.NET Core: substitua `rh-dotnet50-aspnetcore-runtime-5.0` nos comandos acima por `rh-dotnet50-dotnet-runtime-5.0` .</span><span class="sxs-lookup"><span data-stu-id="a6a41-151">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="a6a41-152">RHEL 7 ✔️ .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="a6a41-152">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="a6a41-153">O comando a seguir instala o `scl-utils` pacote:</span><span class="sxs-lookup"><span data-stu-id="a6a41-153">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="a6a41-154">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="a6a41-154">Install the SDK</span></span>

<span data-ttu-id="a6a41-155">SDK do .NET Core permite que você desenvolva aplicativos com o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6a41-155">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="a6a41-156">Se você instalar SDK do .NET Core, não será necessário instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="a6a41-156">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a6a41-157">Para instalar o SDK do .NET Core, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a6a41-157">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="a6a41-158">O Red Hat não recomenda a habilitação permanente `rh-dotnet31` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="a6a41-158">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="a6a41-159">Por exemplo, `rh-dotnet31` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="a6a41-159">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="a6a41-160">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="a6a41-160">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="a6a41-161">Se você quiser habilitar `rh-dotnet` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="a6a41-161">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="a6a41-162">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="a6a41-162">Install the runtime</span></span>

<span data-ttu-id="a6a41-163">O tempo de execução do .NET Core permite executar aplicativos que foram feitos com o .NET Core que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a6a41-163">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="a6a41-164">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6a41-164">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="a6a41-165">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a6a41-165">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="a6a41-166">O Red Hat não recomenda a habilitação permanente `rh-dotnet31` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="a6a41-166">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="a6a41-167">Por exemplo, `rh-dotnet31` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="a6a41-167">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="a6a41-168">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="a6a41-168">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="a6a41-169">Se você quiser habilitar `rh-dotnet31` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="a6a41-169">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="a6a41-170">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET Core que não inclui suporte a ASP.NET Core: substitua `rh-dotnet31-aspnetcore-runtime-3.1` nos comandos acima por `rh-dotnet31-dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="a6a41-170">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="a6a41-171">Snap</span><span class="sxs-lookup"><span data-stu-id="a6a41-171">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="a6a41-172">Dependências</span><span class="sxs-lookup"><span data-stu-id="a6a41-172">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="a6a41-173">Instalação com script</span><span class="sxs-lookup"><span data-stu-id="a6a41-173">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a6a41-174">Instalação manual</span><span class="sxs-lookup"><span data-stu-id="a6a41-174">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a6a41-175">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a6a41-175">Next steps</span></span>

- [<span data-ttu-id="a6a41-176">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a6a41-176">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
