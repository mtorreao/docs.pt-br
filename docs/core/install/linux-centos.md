---
title: Instalar o .NET no CentOS-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no CentOS.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 7e73f90a1f1f7e11e592b1b074f243c9f5b32ced
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970857"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="219b6-103">Instalar o SDK do .NET ou o tempo de execução do .NET no CentOS</span><span class="sxs-lookup"><span data-stu-id="219b6-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="219b6-104">O .NET tem suporte no CentOS.</span><span class="sxs-lookup"><span data-stu-id="219b6-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="219b6-105">Este artigo descreve como instalar o .NET no CentOS.</span><span class="sxs-lookup"><span data-stu-id="219b6-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="219b6-106">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="219b6-106">Supported distributions</span></span>

<span data-ttu-id="219b6-107">A tabela a seguir é uma lista de versões do .NET com suporte no momento no CentOS 7 e no CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="219b6-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="219b6-108">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do CentOS não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="219b6-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="219b6-109">Um ✔️ indica que a versão do CentOS ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="219b6-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="219b6-110">Um ❌ indica que a versão do CentOS ou do .net não tem suporte nessa versão do CentOS.</span><span class="sxs-lookup"><span data-stu-id="219b6-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="219b6-111">Quando uma versão do CentOS e uma versão do .NET têm ✔️, essa combinação de so e .NET é suportada.</span><span class="sxs-lookup"><span data-stu-id="219b6-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="219b6-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="219b6-112">CentOS</span></span>                   | <span data-ttu-id="219b6-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="219b6-113">.NET Core 2.1</span></span> | <span data-ttu-id="219b6-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="219b6-114">.NET Core 3.1</span></span> | <span data-ttu-id="219b6-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="219b6-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="219b6-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="219b6-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="219b6-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="219b6-117">✔️ 2.1</span></span>        | <span data-ttu-id="219b6-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="219b6-118">✔️ 3.1</span></span>        | <span data-ttu-id="219b6-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="219b6-119">✔️ 5.0</span></span> |
| <span data-ttu-id="219b6-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="219b6-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="219b6-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="219b6-121">✔️ 2.1</span></span>        | <span data-ttu-id="219b6-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="219b6-122">✔️ 3.1</span></span>        | <span data-ttu-id="219b6-123">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="219b6-123">✔️ 5.0</span></span> |

<span data-ttu-id="219b6-124">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="219b6-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="219b6-125">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="219b6-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="219b6-126">3.0</span><span class="sxs-lookup"><span data-stu-id="219b6-126">3.0</span></span>
- <span data-ttu-id="219b6-127">2.2</span><span class="sxs-lookup"><span data-stu-id="219b6-127">2.2</span></span>
- <span data-ttu-id="219b6-128">2,0</span><span class="sxs-lookup"><span data-stu-id="219b6-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="219b6-129">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="219b6-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="centos-8-"></a><span data-ttu-id="219b6-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="219b6-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="219b6-131">O .NET 5,0 está disponível nos repositórios de pacotes padrão do CentOS 8.</span><span class="sxs-lookup"><span data-stu-id="219b6-131">.NET 5.0 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="219b6-132">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="219b6-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="219b6-133">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="219b6-133">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="219b6-134">Solucionar problemas do Gerenciador de pacotes</span><span class="sxs-lookup"><span data-stu-id="219b6-134">Troubleshoot the package manager</span></span>

<span data-ttu-id="219b6-135">Esta seção fornece informações sobre erros comuns que você pode obter ao usar o Gerenciador de pacotes para instalar o .NET.</span><span class="sxs-lookup"><span data-stu-id="219b6-135">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="219b6-136">Não é possível localizar o pacote</span><span class="sxs-lookup"><span data-stu-id="219b6-136">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="219b6-137">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="219b6-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="219b6-138">Dependências</span><span class="sxs-lookup"><span data-stu-id="219b6-138">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="next-steps"></a><span data-ttu-id="219b6-139">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="219b6-139">Next steps</span></span>

- [<span data-ttu-id="219b6-140">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="219b6-140">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="219b6-141">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="219b6-141">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
