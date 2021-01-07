---
title: Instalar o .NET no Ubuntu – .NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no Ubuntu.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 14e5e9548d4aa09a586e2038f3e35a489ee65cd2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970754"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="309d0-103">Instalar o SDK do .NET ou o tempo de execução do .NET no Ubuntu</span><span class="sxs-lookup"><span data-stu-id="309d0-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="309d0-104">O .NET tem suporte no Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="309d0-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="309d0-105">Este artigo descreve como instalar o .NET no Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="309d0-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="309d0-106">Quando uma versão do Ubuntu ficar sem suporte, o .NET não terá mais suporte com essa versão.</span><span class="sxs-lookup"><span data-stu-id="309d0-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="309d0-107">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="309d0-107">Supported distributions</span></span>

<span data-ttu-id="309d0-108">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do Ubuntu nas quais elas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="309d0-108">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="309d0-109">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do [Ubuntu atinja o fim da vida útil](https://wiki.ubuntu.com/Releases).</span><span class="sxs-lookup"><span data-stu-id="309d0-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="309d0-110">Um ✔️ indica que a versão do Ubuntu ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="309d0-110">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="309d0-111">Um ❌ indica que a versão do Ubuntu ou do .net não tem suporte nessa versão do Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="309d0-111">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="309d0-112">Quando uma versão do Ubuntu e uma versão do .NET têm ✔️, essa combinação de so e .NET é suportada.</span><span class="sxs-lookup"><span data-stu-id="309d0-112">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="309d0-113">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="309d0-113">Ubuntu</span></span>                   | <span data-ttu-id="309d0-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="309d0-114">.NET Core 2.1</span></span> | <span data-ttu-id="309d0-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="309d0-115">.NET Core 3.1</span></span> | <span data-ttu-id="309d0-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="309d0-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="309d0-117">✔️ [20,10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="309d0-117">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="309d0-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-118">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-119">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-120">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-120">✔️ 5.0</span></span> |
| <span data-ttu-id="309d0-121">✔️ [20, 4 (LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="309d0-121">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="309d0-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-122">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-123">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-124">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-124">✔️ 5.0</span></span> |
| <span data-ttu-id="309d0-125">❌[19,10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="309d0-125">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="309d0-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-126">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-127">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-127">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-128">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-128">✔️ 5.0</span></span> |
| <span data-ttu-id="309d0-129">❌[19, 4](#1904-)</span><span class="sxs-lookup"><span data-stu-id="309d0-129">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="309d0-130">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-130">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-131">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-131">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-132">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-132">❌ 5.0</span></span> |
| <span data-ttu-id="309d0-133">❌[18,10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="309d0-133">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="309d0-134">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-134">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-135">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-135">❌ 3.1</span></span>        | <span data-ttu-id="309d0-136">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-136">❌ 5.0</span></span> |
| <span data-ttu-id="309d0-137">✔️ [18, 4 (LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="309d0-137">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="309d0-138">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-138">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-139">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-139">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-140">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-140">✔️ 5.0</span></span> |
| <span data-ttu-id="309d0-141">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="309d0-141">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="309d0-142">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-142">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-143">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-143">❌ 3.1</span></span>        | <span data-ttu-id="309d0-144">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-144">❌ 5.0</span></span> |
| <span data-ttu-id="309d0-145">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="309d0-145">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="309d0-146">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-146">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-147">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-147">❌ 3.1</span></span>        | <span data-ttu-id="309d0-148">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-148">❌ 5.0</span></span> |
| <span data-ttu-id="309d0-149">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="309d0-149">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="309d0-150">❌ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-150">❌ 2.1</span></span>        | <span data-ttu-id="309d0-151">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-151">❌ 3.1</span></span>        | <span data-ttu-id="309d0-152">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-152">❌ 5.0</span></span> |
| <span data-ttu-id="309d0-153">✔️ [16, 4 (LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="309d0-153">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="309d0-154">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="309d0-154">✔️ 2.1</span></span>        | <span data-ttu-id="309d0-155">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="309d0-155">✔️ 3.1</span></span>        | <span data-ttu-id="309d0-156">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="309d0-156">✔️ 5.0</span></span> |

<span data-ttu-id="309d0-157">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="309d0-157">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="309d0-158">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="309d0-158">The downloads for these still remain published:</span></span>

- <span data-ttu-id="309d0-159">3.0</span><span class="sxs-lookup"><span data-stu-id="309d0-159">3.0</span></span>
- <span data-ttu-id="309d0-160">2.2</span><span class="sxs-lookup"><span data-stu-id="309d0-160">2.2</span></span>
- <span data-ttu-id="309d0-161">2,0</span><span class="sxs-lookup"><span data-stu-id="309d0-161">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="309d0-162">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="309d0-162">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="2010-"></a><span data-ttu-id="309d0-163">20,10 ✔️</span><span class="sxs-lookup"><span data-stu-id="309d0-163">20.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="2004-"></a><span data-ttu-id="309d0-164">20, 4 ✔️</span><span class="sxs-lookup"><span data-stu-id="309d0-164">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="309d0-165">19,10 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-165">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="309d0-166">19, 4 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-166">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="309d0-167">18,10 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-167">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="309d0-168">18, 4 ✔️</span><span class="sxs-lookup"><span data-stu-id="309d0-168">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="309d0-169">17,10 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-169">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="309d0-170">17, 4 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-170">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="309d0-171">16,10 ❌</span><span class="sxs-lookup"><span data-stu-id="309d0-171">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="309d0-172">16, 4 ✔️</span><span class="sxs-lookup"><span data-stu-id="309d0-172">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="309d0-173">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="309d0-173">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="309d0-174">Usar a APT para atualizar o .NET</span><span class="sxs-lookup"><span data-stu-id="309d0-174">Use APT to update .NET</span></span>

<span data-ttu-id="309d0-175">Quando uma nova versão de patch estiver disponível para o .NET, você poderá simplesmente atualizá-la por meio de APT com os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="309d0-175">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="309d0-176">Solução de problemas da APT</span><span class="sxs-lookup"><span data-stu-id="309d0-176">APT troubleshooting</span></span>

<span data-ttu-id="309d0-177">Esta seção fornece informações sobre erros comuns que você pode obter ao usar a APT para instalar o .NET.</span><span class="sxs-lookup"><span data-stu-id="309d0-177">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="309d0-178">Não é possível localizar o pacote</span><span class="sxs-lookup"><span data-stu-id="309d0-178">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="309d0-179">Não foi possível \\ instalar alguns pacotes</span><span class="sxs-lookup"><span data-stu-id="309d0-179">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="309d0-180">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="309d0-180">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="309d0-181">Dependências</span><span class="sxs-lookup"><span data-stu-id="309d0-181">Dependencies</span></span>

<span data-ttu-id="309d0-182">Quando você instala o com um Gerenciador de pacotes, essas bibliotecas são instaladas para você.</span><span class="sxs-lookup"><span data-stu-id="309d0-182">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="309d0-183">Mas, se você instalar o .NET manualmente ou publicar um aplicativo independente, precisará verificar se essas bibliotecas estão instaladas:</span><span class="sxs-lookup"><span data-stu-id="309d0-183">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="309d0-184">libc6</span><span class="sxs-lookup"><span data-stu-id="309d0-184">libc6</span></span>
- <span data-ttu-id="309d0-185">libgcc1</span><span class="sxs-lookup"><span data-stu-id="309d0-185">libgcc1</span></span>
- <span data-ttu-id="309d0-186">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="309d0-186">libgssapi-krb5-2</span></span>
- <span data-ttu-id="309d0-187">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="309d0-187">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="309d0-188">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="309d0-188">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="309d0-189">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="309d0-189">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="309d0-190">libicu66 (para 20. x)</span><span class="sxs-lookup"><span data-stu-id="309d0-190">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="309d0-191">libssl 1.0.0 (para 14. x, 16. x)</span><span class="sxs-lookup"><span data-stu-id="309d0-191">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="309d0-192">libssl 1.1 (para 18. x, 20. x)</span><span class="sxs-lookup"><span data-stu-id="309d0-192">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="309d0-193">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="309d0-193">libstdc++6</span></span>
- <span data-ttu-id="309d0-194">zlib1g</span><span class="sxs-lookup"><span data-stu-id="309d0-194">zlib1g</span></span>

<span data-ttu-id="309d0-195">Para aplicativos .NET que usam o assembly *System. Drawing. Common* , você também precisa da seguinte dependência:</span><span class="sxs-lookup"><span data-stu-id="309d0-195">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="309d0-196">libgdiplus (versão 6.0.1 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="309d0-196">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="309d0-197">Você pode instalar uma versão recente do *libgdiplus* adicionando o repositório do mono ao seu sistema.</span><span class="sxs-lookup"><span data-stu-id="309d0-197">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="309d0-198">Para obter mais informações, consulte <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="309d0-198">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="309d0-199">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="309d0-199">Next steps</span></span>

- [<span data-ttu-id="309d0-200">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="309d0-200">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="309d0-201">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="309d0-201">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
