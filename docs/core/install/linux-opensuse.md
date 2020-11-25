---
title: Instalar o .NET em openSUSE-.NET
description: Demonstra as várias maneiras de instalar o SDK do .NET e o tempo de execução do .NET no openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: eb31e3109ccd40999c22a27607d48544bf117dc2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031859"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="cd890-103">Instalar o SDK do .NET ou o tempo de execução do .NET no openSUSE</span><span class="sxs-lookup"><span data-stu-id="cd890-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="cd890-104">O .NET tem suporte no openSUSE.</span><span class="sxs-lookup"><span data-stu-id="cd890-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="cd890-105">Este artigo descreve como instalar o .NET no openSUSE.</span><span class="sxs-lookup"><span data-stu-id="cd890-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="cd890-106">Distribuições com suporte</span><span class="sxs-lookup"><span data-stu-id="cd890-106">Supported distributions</span></span>

<span data-ttu-id="cd890-107">A tabela a seguir é uma lista de versões do .NET com suporte no momento no openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="cd890-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="cd890-108">Essas versões permanecem com suporte até que a versão do [.net atinja o fim do suporte](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ou a versão do openSUSE não seja mais suportada.</span><span class="sxs-lookup"><span data-stu-id="cd890-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="cd890-109">Um ✔️ indica que a versão do openSUSE ou do .NET ainda tem suporte.</span><span class="sxs-lookup"><span data-stu-id="cd890-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="cd890-110">Um ❌ indica que a versão do openSUSE ou do .net não tem suporte nessa versão do openSUSE.</span><span class="sxs-lookup"><span data-stu-id="cd890-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="cd890-111">Quando uma versão do openSUSE e uma versão do .NET têm ✔️, há suporte para essa combinação de so e .NET.</span><span class="sxs-lookup"><span data-stu-id="cd890-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="cd890-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="cd890-112">openSUSE</span></span>                   | <span data-ttu-id="cd890-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cd890-113">.NET Core 2.1</span></span> | <span data-ttu-id="cd890-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cd890-114">.NET Core 3.1</span></span> | <span data-ttu-id="cd890-115">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="cd890-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="cd890-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="cd890-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="cd890-117">✔️ 2,1</span><span class="sxs-lookup"><span data-stu-id="cd890-117">✔️ 2.1</span></span>        | <span data-ttu-id="cd890-118">✔️ 3,1</span><span class="sxs-lookup"><span data-stu-id="cd890-118">✔️ 3.1</span></span>        | <span data-ttu-id="cd890-119">✔️ 5,0</span><span class="sxs-lookup"><span data-stu-id="cd890-119">✔️ 5.0</span></span> |

<span data-ttu-id="cd890-120">Não há mais suporte para as seguintes versões do .NET.</span><span class="sxs-lookup"><span data-stu-id="cd890-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="cd890-121">Os downloads para eles ainda permanecem publicados:</span><span class="sxs-lookup"><span data-stu-id="cd890-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="cd890-122">3.0</span><span class="sxs-lookup"><span data-stu-id="cd890-122">3.0</span></span>
- <span data-ttu-id="cd890-123">2.2</span><span class="sxs-lookup"><span data-stu-id="cd890-123">2.2</span></span>
- <span data-ttu-id="cd890-124">2,0</span><span class="sxs-lookup"><span data-stu-id="cd890-124">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="cd890-125">Remover versões de visualização</span><span class="sxs-lookup"><span data-stu-id="cd890-125">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="cd890-126">Como instalar outras versões</span><span class="sxs-lookup"><span data-stu-id="cd890-126">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="cd890-127">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="cd890-127">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="cd890-128">Solucionar problemas do Gerenciador de pacotes</span><span class="sxs-lookup"><span data-stu-id="cd890-128">Troubleshoot the package manager</span></span>

<span data-ttu-id="cd890-129">Esta seção fornece informações sobre erros comuns que você pode obter ao usar o Gerenciador de pacotes para instalar o .NET.</span><span class="sxs-lookup"><span data-stu-id="cd890-129">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="cd890-130">Não é possível localizar o pacote</span><span class="sxs-lookup"><span data-stu-id="cd890-130">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="cd890-131">Falha ao buscar</span><span class="sxs-lookup"><span data-stu-id="cd890-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="cd890-132">Snap</span><span class="sxs-lookup"><span data-stu-id="cd890-132">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="cd890-133">Dependências</span><span class="sxs-lookup"><span data-stu-id="cd890-133">Dependencies</span></span>

<span data-ttu-id="cd890-134">Quando você instala o com um Gerenciador de pacotes, essas bibliotecas são instaladas para você.</span><span class="sxs-lookup"><span data-stu-id="cd890-134">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="cd890-135">Mas, se você instalar o .NET manualmente ou publicar um aplicativo independente, precisará verificar se essas bibliotecas estão instaladas:</span><span class="sxs-lookup"><span data-stu-id="cd890-135">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="cd890-136">krb5</span><span class="sxs-lookup"><span data-stu-id="cd890-136">krb5</span></span>
- <span data-ttu-id="cd890-137">libicu</span><span class="sxs-lookup"><span data-stu-id="cd890-137">libicu</span></span>
- <span data-ttu-id="cd890-138">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="cd890-138">libopenssl1_0_0</span></span>

<span data-ttu-id="cd890-139">Se a versão do OpenSSL do ambiente de tempo de execução de destino for 1,1 ou mais recente, você precisará instalar o **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="cd890-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="cd890-140">Para obter mais informações sobre as dependências, consulte [aplicativos do Linux autocontidos](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cd890-140">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="cd890-141">Para aplicativos .NET que usam o assembly *System. Drawing. Common* , você também precisará da seguinte dependência:</span><span class="sxs-lookup"><span data-stu-id="cd890-141">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="cd890-142">libgdiplus (versão 6.0.1 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="cd890-142">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="cd890-143">Você pode instalar uma versão recente do *libgdiplus* adicionando o repositório do mono ao seu sistema.</span><span class="sxs-lookup"><span data-stu-id="cd890-143">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="cd890-144">Para obter mais informações, consulte <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="cd890-144">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="cd890-145">Instalação com script</span><span class="sxs-lookup"><span data-stu-id="cd890-145">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="cd890-146">Instalação manual</span><span class="sxs-lookup"><span data-stu-id="cd890-146">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="cd890-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cd890-147">Next steps</span></span>

- [<span data-ttu-id="cd890-148">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cd890-148">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
