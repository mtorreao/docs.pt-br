---
title: Instalar o .NET no SLES-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no SLES.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 80da69616dd1507b809ef56d439645d569a6a805
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970779"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a><span data-ttu-id="ed5b1-103">Instalar o SDK do .NET ou o tempo de execução do .NET no SLES</span><span class="sxs-lookup"><span data-stu-id="ed5b1-103">Install the .NET SDK or the .NET Runtime on SLES</span></span>

<span data-ttu-id="ed5b1-104">O .NET tem suporte no SLES.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-104">.NET is supported on SLES.</span></span> <span data-ttu-id="ed5b1-105">Este artigo descreve como instalar o .NET no SLES.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-105">This article describes how to install .NET on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="ed5b1-106">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="ed5b1-106">Supported distributions</span></span>

<span data-ttu-id="ed5b1-107">A tabela a seguir é uma lista de versões do .NET com suporte no momento no SLES 12 SP2 e no SLES 15.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-107">The following table is a list of currently supported .NET releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="ed5b1-108">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do SLES não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="ed5b1-109">Um ✔️ indica que a versão do SLES ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-109">A ✔️ indicates that the version of SLES or .NET is still supported.</span></span>
- <span data-ttu-id="ed5b1-110">Um ❌ indica que a versão do SLES ou do .net não tem suporte nessa versão do SLES.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-110">A ❌ indicates that the version of SLES or .NET isn't supported on that SLES release.</span></span>
- <span data-ttu-id="ed5b1-111">Quando uma versão do SLES e uma versão do .NET têm ✔️, essa combinação de so e .NET é suportada.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-111">When both a version of SLES and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="ed5b1-112">SLES</span><span class="sxs-lookup"><span data-stu-id="ed5b1-112">SLES</span></span>                   | <span data-ttu-id="ed5b1-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-113">.NET Core 2.1</span></span> | <span data-ttu-id="ed5b1-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-114">.NET Core 3.1</span></span> | <span data-ttu-id="ed5b1-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed5b1-115">.NET 5.0</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="ed5b1-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="ed5b1-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="ed5b1-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-117">✔️ 2.1</span></span>        | <span data-ttu-id="ed5b1-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-118">✔️ 3.1</span></span>        | <span data-ttu-id="ed5b1-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="ed5b1-119">✔️ 5.0</span></span> |
| <span data-ttu-id="ed5b1-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="ed5b1-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="ed5b1-121">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-121">✔️ 2.1</span></span>        | <span data-ttu-id="ed5b1-122">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-122">✔️ 3.1</span></span>        | <span data-ttu-id="ed5b1-123">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="ed5b1-123">✔️ 5.0</span></span> |

<span data-ttu-id="ed5b1-124">Não há mais suporte para as seguintes versões do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="ed5b1-125">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="ed5b1-126">3.0</span><span class="sxs-lookup"><span data-stu-id="ed5b1-126">3.0</span></span>
- <span data-ttu-id="ed5b1-127">2.2</span><span class="sxs-lookup"><span data-stu-id="ed5b1-127">2.2</span></span>
- <span data-ttu-id="ed5b1-128">2,0</span><span class="sxs-lookup"><span data-stu-id="ed5b1-128">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="ed5b1-129">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="ed5b1-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="sles-15-"></a><span data-ttu-id="ed5b1-130">✔️ SLES 15</span><span class="sxs-lookup"><span data-stu-id="ed5b1-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="ed5b1-131">Atualmente, o pacote de instalação do repositório do SLES 15 da Microsoft instala o arquivo *Microsoft-prod. repositório* no diretório errado, impedindo que o Zypper Localize os pacotes .net.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET packages.</span></span> <span data-ttu-id="ed5b1-132">Para corrigir esse problema, crie um symlink no diretório correto.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="ed5b1-133">✔️ SLES 12</span><span class="sxs-lookup"><span data-stu-id="ed5b1-133">SLES 12 ✔️</span></span>

<span data-ttu-id="ed5b1-134">O .NET requer o SP2 como um mínimo para a família SLES 12.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-134">.NET requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ed5b1-135">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="ed5b1-135">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ed5b1-136">Solucionar problemas do Gerenciador de pacotes</span><span class="sxs-lookup"><span data-stu-id="ed5b1-136">Troubleshoot the package manager</span></span>

<span data-ttu-id="ed5b1-137">Esta seção fornece informações sobre erros comuns que você pode obter ao usar o Gerenciador de pacotes para instalar o .NET.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-137">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="ed5b1-138">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="ed5b1-138">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="ed5b1-139">Dependências</span><span class="sxs-lookup"><span data-stu-id="ed5b1-139">Dependencies</span></span>

<span data-ttu-id="ed5b1-140">Quando você instala o com um Gerenciador de pacotes, essas bibliotecas são instaladas para você.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-140">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="ed5b1-141">Mas, se você instalar o .NET manualmente ou publicar um aplicativo independente, precisará verificar se essas bibliotecas estão instaladas:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-141">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="ed5b1-142">krb5</span><span class="sxs-lookup"><span data-stu-id="ed5b1-142">krb5</span></span>
- <span data-ttu-id="ed5b1-143">libicu</span><span class="sxs-lookup"><span data-stu-id="ed5b1-143">libicu</span></span>
- <span data-ttu-id="ed5b1-144">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="ed5b1-144">libopenssl1_1</span></span>

<span data-ttu-id="ed5b1-145">Se a versão do OpenSSL do ambiente de tempo de execução de destino for 1,1 ou mais recente, você precisará instalar o **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-145">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="ed5b1-146">Para obter mais informações sobre as dependências, consulte [aplicativos do Linux autocontidos](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ed5b1-146">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="ed5b1-147">Para aplicativos .NET que usam o assembly *System. Drawing. Common* , você também precisará da seguinte dependência:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-147">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="ed5b1-148">libgdiplus (versão 6.0.1 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="ed5b1-148">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="ed5b1-149">Você pode instalar uma versão recente do *libgdiplus* adicionando o repositório do mono ao seu sistema.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-149">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="ed5b1-150">Para obter mais informações, consulte <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="ed5b1-150">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed5b1-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ed5b1-151">Next steps</span></span>

- [<span data-ttu-id="ed5b1-152">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="ed5b1-152">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="ed5b1-153">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ed5b1-153">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
