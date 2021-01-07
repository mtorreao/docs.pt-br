---
title: Instalar o .NET em Fedora-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no Fedora.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970818"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="a23ee-103">Instalar o SDK do .NET ou o tempo de execução do .NET no Fedora</span><span class="sxs-lookup"><span data-stu-id="a23ee-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="a23ee-104">O .NET tem suporte no Fedora e este artigo descreve como instalar o .NET no Fedora.</span><span class="sxs-lookup"><span data-stu-id="a23ee-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="a23ee-105">Quando uma versão do Fedora fica sem suporte, o .NET não é mais compatível com essa versão.</span><span class="sxs-lookup"><span data-stu-id="a23ee-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a><span data-ttu-id="a23ee-106">Instalar o .NET 5,0</span><span class="sxs-lookup"><span data-stu-id="a23ee-106">Install .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="a23ee-107">**Fedora 32**</span><span class="sxs-lookup"><span data-stu-id="a23ee-107">**Fedora 32**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

<span data-ttu-id="a23ee-108">**Fedora 33**</span><span class="sxs-lookup"><span data-stu-id="a23ee-108">**Fedora 33**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="a23ee-109">Instalar o .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="a23ee-109">Install .NET Core 3.1</span></span>

<span data-ttu-id="a23ee-110">A versão mais recente do .NET disponível nos repositórios de pacotes padrão do Fedora é o .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a23ee-110">The latest version of .NET available in the default package repositories for Fedora is .NET Core 3.1.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a23ee-111">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="a23ee-111">Supported distributions</span></span>

<span data-ttu-id="a23ee-112">A tabela a seguir é uma lista de versões do .NET com suporte no momento e as versões do Fedora em que têm suporte.</span><span class="sxs-lookup"><span data-stu-id="a23ee-112">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="a23ee-113">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do [Fedora atinja o fim da vida útil](https://fedoraproject.org/wiki/End_of_life).</span><span class="sxs-lookup"><span data-stu-id="a23ee-113">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="a23ee-114">Um ✔️ indica que a versão do Fedora ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="a23ee-114">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="a23ee-115">Um ❌ indica que a versão do Fedora ou do .net não tem suporte nessa versão do Fedora.</span><span class="sxs-lookup"><span data-stu-id="a23ee-115">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="a23ee-116">Quando uma versão do Fedora e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="a23ee-116">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a23ee-117">Versão .NET</span><span class="sxs-lookup"><span data-stu-id="a23ee-117">.NET Version</span></span>  | <span data-ttu-id="a23ee-118">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-118">Fedora 33 ✔️</span></span> | <span data-ttu-id="a23ee-119">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-119">32 ✔️</span></span> | <span data-ttu-id="a23ee-120">31 ❌</span><span class="sxs-lookup"><span data-stu-id="a23ee-120">31 ❌</span></span> | <span data-ttu-id="a23ee-121">máximo ❌</span><span class="sxs-lookup"><span data-stu-id="a23ee-121">30 ❌</span></span> | <span data-ttu-id="a23ee-122">29 ❌</span><span class="sxs-lookup"><span data-stu-id="a23ee-122">29 ❌</span></span> | <span data-ttu-id="a23ee-123">38 ❌</span><span class="sxs-lookup"><span data-stu-id="a23ee-123">28 ❌</span></span> | <span data-ttu-id="a23ee-124">27 ❌</span><span class="sxs-lookup"><span data-stu-id="a23ee-124">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="a23ee-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a23ee-125">.NET 5.0</span></span>      | <span data-ttu-id="a23ee-126">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-126">✔️</span></span>        | <span data-ttu-id="a23ee-127">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-127">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="a23ee-128">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a23ee-128">.NET Core 3.1</span></span> | <span data-ttu-id="a23ee-129">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-129">✔️</span></span>        | <span data-ttu-id="a23ee-130">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-130">✔️</span></span> | <span data-ttu-id="a23ee-131">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-131">✔️</span></span>|<span data-ttu-id="a23ee-132">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-132">✔️</span></span> |<span data-ttu-id="a23ee-133">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-133">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="a23ee-134">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a23ee-134">.NET Core 2.1</span></span> | <span data-ttu-id="a23ee-135">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-135">✔️</span></span>        | <span data-ttu-id="a23ee-136">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-136">✔️</span></span> | <span data-ttu-id="a23ee-137">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-137">✔️</span></span>|<span data-ttu-id="a23ee-138">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-138">✔️</span></span> |<span data-ttu-id="a23ee-139">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-139">✔️</span></span> |<span data-ttu-id="a23ee-140">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-140">✔️</span></span>  |<span data-ttu-id="a23ee-141">✔️</span><span class="sxs-lookup"><span data-stu-id="a23ee-141">✔️</span></span> |

<span data-ttu-id="a23ee-142">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="a23ee-142">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a23ee-143">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="a23ee-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a23ee-144">3.0</span><span class="sxs-lookup"><span data-stu-id="a23ee-144">3.0</span></span>
- <span data-ttu-id="a23ee-145">2.2</span><span class="sxs-lookup"><span data-stu-id="a23ee-145">2.2</span></span>
- <span data-ttu-id="a23ee-146">2,0</span><span class="sxs-lookup"><span data-stu-id="a23ee-146">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="a23ee-147">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="a23ee-147">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="a23ee-148">Dependências</span><span class="sxs-lookup"><span data-stu-id="a23ee-148">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="a23ee-149">Instalar em distribuições mais antigas</span><span class="sxs-lookup"><span data-stu-id="a23ee-149">Install on older distributions</span></span>

<span data-ttu-id="a23ee-150">As versões mais antigas do Fedora não contêm o .NET Core nos repositórios de pacote padrão.</span><span class="sxs-lookup"><span data-stu-id="a23ee-150">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="a23ee-151">Você pode instalar o .NET com [snap](linux-snap.md), por meio do [script _dotnet-install.sh_](linux-scripted-manual.md#scripted-install), ou usar o repositório da Microsoft para instalar o .net:</span><span class="sxs-lookup"><span data-stu-id="a23ee-151">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="a23ee-152">Primeiro, adicione a chave de assinatura da Microsoft à lista de chaves confiáveis.</span><span class="sxs-lookup"><span data-stu-id="a23ee-152">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="a23ee-153">Em seguida, adicione o repositório de pacotes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a23ee-153">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="a23ee-154">A origem do repositório é baseada em sua versão do Fedora.</span><span class="sxs-lookup"><span data-stu-id="a23ee-154">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="a23ee-155">Versão do Fedora</span><span class="sxs-lookup"><span data-stu-id="a23ee-155">Fedora Version</span></span> | <span data-ttu-id="a23ee-156">Repositório de pacotes</span><span class="sxs-lookup"><span data-stu-id="a23ee-156">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="a23ee-157">31</span><span class="sxs-lookup"><span data-stu-id="a23ee-157">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="a23ee-158">30</span><span class="sxs-lookup"><span data-stu-id="a23ee-158">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="a23ee-159">29</span><span class="sxs-lookup"><span data-stu-id="a23ee-159">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="a23ee-160">28</span><span class="sxs-lookup"><span data-stu-id="a23ee-160">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="a23ee-161">27</span><span class="sxs-lookup"><span data-stu-id="a23ee-161">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a23ee-162">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="a23ee-162">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a23ee-163">Solucionar problemas do Gerenciador de pacotes</span><span class="sxs-lookup"><span data-stu-id="a23ee-163">Troubleshoot the package manager</span></span>

<span data-ttu-id="a23ee-164">Esta seção fornece informações sobre erros comuns que você pode obter ao usar o Gerenciador de pacotes para instalar o .NET ou o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a23ee-164">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a23ee-165">Não é possível localizar o pacote</span><span class="sxs-lookup"><span data-stu-id="a23ee-165">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="a23ee-166">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="a23ee-166">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="a23ee-167">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a23ee-167">Next steps</span></span>

- [<span data-ttu-id="a23ee-168">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="a23ee-168">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="a23ee-169">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a23ee-169">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
