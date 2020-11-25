---
title: Instalar o .NET no RHEL-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 931cad51ff8e35ff16b67ff9b795feb36010a66b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031745"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="fca3a-103">Instalar o SDK do .NET ou o tempo de execução do .NET no RHEL</span><span class="sxs-lookup"><span data-stu-id="fca3a-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="fca3a-104">O .NET tem suporte no RHEL.</span><span class="sxs-lookup"><span data-stu-id="fca3a-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="fca3a-105">Este artigo descreve como instalar o .NET no RHEL.</span><span class="sxs-lookup"><span data-stu-id="fca3a-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="fca3a-106">Registrar sua assinatura do Red Hat</span><span class="sxs-lookup"><span data-stu-id="fca3a-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="fca3a-107">Para instalar o .NET do Red Hat no RHEL, primeiro você precisa se registrar usando o Gerenciador de assinaturas do Red Hat.</span><span class="sxs-lookup"><span data-stu-id="fca3a-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="fca3a-108">Se isso não tiver sido feito em seu sistema ou se você não tiver certeza, consulte a [documentação do produto Red Hat para .net](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="fca3a-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="fca3a-109">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="fca3a-109">Supported distributions</span></span>

<span data-ttu-id="fca3a-110">A tabela a seguir é uma lista de versões do .NET com suporte no momento no RHEL 7 e RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="fca3a-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="fca3a-111">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do RHEL não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="fca3a-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="fca3a-112">Um ✔️ indica que a versão do RHEL ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="fca3a-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="fca3a-113">Um ❌ indica que a versão do RHEL ou .net não tem suporte nessa versão do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fca3a-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="fca3a-114">Quando uma versão do RHEL e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="fca3a-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="fca3a-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="fca3a-115">RHEL</span></span>                     | <span data-ttu-id="fca3a-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fca3a-116">.NET Core 2.1</span></span> | <span data-ttu-id="fca3a-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="fca3a-117">.NET Core 3.1</span></span> | <span data-ttu-id="fca3a-118">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="fca3a-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="fca3a-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="fca3a-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="fca3a-120">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fca3a-120">✔️ 2.1</span></span>        | <span data-ttu-id="fca3a-121">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="fca3a-121">✔️ 3.1</span></span>        | <span data-ttu-id="fca3a-122">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="fca3a-122">✔️ 5.0</span></span> |
| <span data-ttu-id="fca3a-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="fca3a-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="fca3a-124">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="fca3a-124">✔️ 2.1</span></span>        | <span data-ttu-id="fca3a-125">✔️ [3,1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="fca3a-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="fca3a-126">✔️ [5,0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="fca3a-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="fca3a-127">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="fca3a-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="fca3a-128">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="fca3a-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="fca3a-129">3.0</span><span class="sxs-lookup"><span data-stu-id="fca3a-129">3.0</span></span>
- <span data-ttu-id="fca3a-130">2.2</span><span class="sxs-lookup"><span data-stu-id="fca3a-130">2.2</span></span>
- <span data-ttu-id="fca3a-131">2,0</span><span class="sxs-lookup"><span data-stu-id="fca3a-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="fca3a-132">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="fca3a-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fca3a-133">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="fca3a-133">How to install other versions</span></span>

<span data-ttu-id="fca3a-134">Consulte a [documentação do Red Hat para .net](https://access.redhat.com/documentation/net/5.0/) nas etapas necessárias para instalar outras versões do .net.</span><span class="sxs-lookup"><span data-stu-id="fca3a-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="fca3a-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="fca3a-135">RHEL 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="fca3a-136">O .NET 5,0 ainda não está disponível nos repositórios do AppStream, mas o .NET Core 3,1 é.</span><span class="sxs-lookup"><span data-stu-id="fca3a-136">.NET 5.0 isn't yet available in the AppStream repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="fca3a-137">Para instalar o .NET Core 3,1, use o `dnf install` comando com o pacote apropriado, como `aspnetcore-runtime-3.1` ou `dotnet-sdk-3.1` .</span><span class="sxs-lookup"><span data-stu-id="fca3a-137">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="fca3a-138">As instruções a seguir são para o .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="fca3a-138">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="fca3a-139">RHEL 7 ✔️ .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="fca3a-139">RHEL 7 ✔️ .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="fca3a-140">RHEL 7 ✔️ .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="fca3a-140">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="fca3a-141">O comando a seguir instala o `scl-utils` pacote:</span><span class="sxs-lookup"><span data-stu-id="fca3a-141">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="fca3a-142">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="fca3a-142">Install the SDK</span></span>

<span data-ttu-id="fca3a-143">SDK do .NET Core permite que você desenvolva aplicativos com o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fca3a-143">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="fca3a-144">Se você instalar SDK do .NET Core, não será necessário instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="fca3a-144">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="fca3a-145">Para instalar o SDK do .NET Core, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="fca3a-145">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="fca3a-146">O Red Hat não recomenda a habilitação permanente `rh-dotnet31` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fca3a-146">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="fca3a-147">Por exemplo, `rh-dotnet31` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fca3a-147">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="fca3a-148">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="fca3a-148">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="fca3a-149">Se você quiser habilitar `rh-dotnet` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fca3a-149">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="fca3a-150">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="fca3a-150">Install the runtime</span></span>

<span data-ttu-id="fca3a-151">O tempo de execução do .NET Core permite executar aplicativos que foram feitos com o .NET Core que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="fca3a-151">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="fca3a-152">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fca3a-152">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="fca3a-153">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fca3a-153">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="fca3a-154">O Red Hat não recomenda a habilitação permanente `rh-dotnet31-aspnetcore-runtime-3.1` porque pode afetar outros programas.</span><span class="sxs-lookup"><span data-stu-id="fca3a-154">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="fca3a-155">Por exemplo, `rh-dotnet31-aspnetcore-runtime-3.1` inclui uma versão do `libcurl` que difere da versão base do RHEL.</span><span class="sxs-lookup"><span data-stu-id="fca3a-155">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="fca3a-156">Isso pode levar a problemas em programas que não esperam uma versão diferente do `libcurl` .</span><span class="sxs-lookup"><span data-stu-id="fca3a-156">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="fca3a-157">Se você quiser habilitar `rh-dotnet31-aspnetcore-runtime-3.1` permanentemente, adicione a seguinte linha ao seu arquivo _~/.bashrc_ .</span><span class="sxs-lookup"><span data-stu-id="fca3a-157">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="fca3a-158">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET Core que não inclui suporte a ASP.NET Core: substitua `rh-dotnet31-aspnetcore-runtime-3.1` nos comandos acima por `rh-dotnet31-dotnet-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="fca3a-158">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="fca3a-159">Snap</span><span class="sxs-lookup"><span data-stu-id="fca3a-159">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="fca3a-160">Dependências</span><span class="sxs-lookup"><span data-stu-id="fca3a-160">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="fca3a-161">Instalação com script</span><span class="sxs-lookup"><span data-stu-id="fca3a-161">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="fca3a-162">Instalação manual</span><span class="sxs-lookup"><span data-stu-id="fca3a-162">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="fca3a-163">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fca3a-163">Next steps</span></span>

- [<span data-ttu-id="fca3a-164">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fca3a-164">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
