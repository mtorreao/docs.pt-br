---
title: Instalar o .NET no Debian-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no Debian.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 913d8bffdd6c0b5e88a70dae0ec4c8d732e80cc0
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970831"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-debian"></a><span data-ttu-id="a8c35-103">Instalar o SDK do .NET ou o tempo de execução do .NET no Debian</span><span class="sxs-lookup"><span data-stu-id="a8c35-103">Install the .NET SDK or the .NET Runtime on Debian</span></span>

<span data-ttu-id="a8c35-104">Este artigo descreve como instalar o .NET no Debian.</span><span class="sxs-lookup"><span data-stu-id="a8c35-104">This article describes how to install .NET on Debian.</span></span> <span data-ttu-id="a8c35-105">Quando uma versão Debian fica sem suporte, o .NET não é mais compatível com essa versão.</span><span class="sxs-lookup"><span data-stu-id="a8c35-105">When a Debian version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="a8c35-106">No entanto, essas instruções podem ajudá-lo a obter o .NET em execução nessas versões, mesmo que não haja suporte.</span><span class="sxs-lookup"><span data-stu-id="a8c35-106">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a8c35-107">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="a8c35-107">Supported distributions</span></span>

<span data-ttu-id="a8c35-108">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do Debian nas quais elas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="a8c35-108">The following table is a list of currently supported .NET releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="a8c35-109">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do [Debian atinja o fim da vida útil](https://wiki.debian.org/DebianReleases).</span><span class="sxs-lookup"><span data-stu-id="a8c35-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="a8c35-110">Um ✔️ indica que a versão do Debian ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="a8c35-110">A ✔️ indicates that the version of Debian or .NET is still supported.</span></span>
- <span data-ttu-id="a8c35-111">Um ❌ indica que a versão do Debian ou do .net não tem suporte nessa versão do Debian.</span><span class="sxs-lookup"><span data-stu-id="a8c35-111">A ❌ indicates that the version of Debian or .NET isn't supported on that Debian release.</span></span>
- <span data-ttu-id="a8c35-112">Quando uma versão do Debian e uma versão do .NET têm ✔️, essa combinação de so e .NET é suportada.</span><span class="sxs-lookup"><span data-stu-id="a8c35-112">When both a version of Debian and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a8c35-113">Debian</span><span class="sxs-lookup"><span data-stu-id="a8c35-113">Debian</span></span>                   | <span data-ttu-id="a8c35-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a8c35-114">.NET Core 2.1</span></span> | <span data-ttu-id="a8c35-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a8c35-115">.NET Core 3.1</span></span> | <span data-ttu-id="a8c35-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a8c35-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a8c35-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="a8c35-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="a8c35-118">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-118">✔️ 2.1</span></span>        | <span data-ttu-id="a8c35-119">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-119">✔️ 3.1</span></span>        | <span data-ttu-id="a8c35-120">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a8c35-120">✔️ 5.0</span></span> |
| <span data-ttu-id="a8c35-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="a8c35-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="a8c35-122">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-122">✔️ 2.1</span></span>        | <span data-ttu-id="a8c35-123">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-123">✔️ 3.1</span></span>        | <span data-ttu-id="a8c35-124">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="a8c35-124">✔️ 5.0</span></span> |
| <span data-ttu-id="a8c35-125">❌[8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="a8c35-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="a8c35-126">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-126">✔️ 2.1</span></span>        | <span data-ttu-id="a8c35-127">❌ 3,1</span><span class="sxs-lookup"><span data-stu-id="a8c35-127">❌ 3.1</span></span>        | <span data-ttu-id="a8c35-128">❌ 5,0</span><span class="sxs-lookup"><span data-stu-id="a8c35-128">❌ 5.0</span></span> |

<span data-ttu-id="a8c35-129">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="a8c35-129">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a8c35-130">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="a8c35-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a8c35-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a8c35-131">3.0</span></span>
- <span data-ttu-id="a8c35-132">2.2</span><span class="sxs-lookup"><span data-stu-id="a8c35-132">2.2</span></span>
- <span data-ttu-id="a8c35-133">2,0</span><span class="sxs-lookup"><span data-stu-id="a8c35-133">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="a8c35-134">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="a8c35-134">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="debian-10-"></a><span data-ttu-id="a8c35-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="a8c35-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="a8c35-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="a8c35-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="a8c35-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="a8c35-137">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a8c35-138">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="a8c35-138">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="a8c35-139">Usar a APT para atualizar o .NET</span><span class="sxs-lookup"><span data-stu-id="a8c35-139">Use APT to update .NET</span></span>

<span data-ttu-id="a8c35-140">Quando uma nova versão de patch estiver disponível para o .NET, você poderá simplesmente atualizá-la por meio de APT com os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a8c35-140">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="a8c35-141">Solução de problemas da APT</span><span class="sxs-lookup"><span data-stu-id="a8c35-141">APT troubleshooting</span></span>

<span data-ttu-id="a8c35-142">Esta seção fornece informações sobre erros comuns que você pode obter ao usar a APT para instalar o .NET.</span><span class="sxs-lookup"><span data-stu-id="a8c35-142">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a8c35-143">Não é possível localizar o pacote</span><span class="sxs-lookup"><span data-stu-id="a8c35-143">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="a8c35-144">Não foi possível \\ instalar alguns pacotes</span><span class="sxs-lookup"><span data-stu-id="a8c35-144">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="a8c35-145">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="a8c35-145">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="a8c35-146">Dependências</span><span class="sxs-lookup"><span data-stu-id="a8c35-146">Dependencies</span></span>

<span data-ttu-id="a8c35-147">Quando você instala o com um Gerenciador de pacotes, essas bibliotecas são instaladas para você.</span><span class="sxs-lookup"><span data-stu-id="a8c35-147">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="a8c35-148">Mas, se você instalar manualmente o .NET Core ou publicar um aplicativo independente, precisará verificar se essas bibliotecas estão instaladas:</span><span class="sxs-lookup"><span data-stu-id="a8c35-148">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="a8c35-149">libc6</span><span class="sxs-lookup"><span data-stu-id="a8c35-149">libc6</span></span>
- <span data-ttu-id="a8c35-150">libgcc1</span><span class="sxs-lookup"><span data-stu-id="a8c35-150">libgcc1</span></span>
- <span data-ttu-id="a8c35-151">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="a8c35-151">libgssapi-krb5-2</span></span>
- <span data-ttu-id="a8c35-152">libicu52 (para 8. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-152">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="a8c35-153">libicu57 (para 9. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-153">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="a8c35-154">libicu63 (para 10. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-154">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="a8c35-155">libicu67 (para 11. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-155">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="a8c35-156">libssl 1.0.0 (para 8. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-156">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="a8c35-157">libssl 1.1 (para 9. x-11. x)</span><span class="sxs-lookup"><span data-stu-id="a8c35-157">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="a8c35-158">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="a8c35-158">libstdc++6</span></span>
- <span data-ttu-id="a8c35-159">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a8c35-159">zlib1g</span></span>

<span data-ttu-id="a8c35-160">Para aplicativos .NET Core que usam o assembly *System. Drawing. Common* , você também precisa da seguinte dependência:</span><span class="sxs-lookup"><span data-stu-id="a8c35-160">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a8c35-161">libgdiplus (versão 6.0.1 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="a8c35-161">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="a8c35-162">Você pode instalar uma versão recente do *libgdiplus* adicionando o repositório do mono ao seu sistema.</span><span class="sxs-lookup"><span data-stu-id="a8c35-162">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="a8c35-163">Para obter mais informações, consulte <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="a8c35-163">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8c35-164">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a8c35-164">Next steps</span></span>

- [<span data-ttu-id="a8c35-165">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="a8c35-165">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="a8c35-166">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a8c35-166">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
