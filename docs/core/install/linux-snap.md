---
title: Instalar o .NET no Linux com snap-.NET
description: Demonstra como instalar o SDK do .NET ou o tempo de execução do .NET no Linux com o snap.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 741933b5ca6f01d73b388675fe7f8a43c4efb0f9
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970958"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a><span data-ttu-id="13fe1-103">Instalar o SDK do .NET ou o tempo de execução do .NET com snap</span><span class="sxs-lookup"><span data-stu-id="13fe1-103">Install the .NET SDK or the .NET Runtime with Snap</span></span>

<span data-ttu-id="13fe1-104">Use um pacote de snap para instalar o SDK do .NET ou o tempo de execução do .NET.</span><span class="sxs-lookup"><span data-stu-id="13fe1-104">Use a Snap package to install the .NET SDK or .NET Runtime.</span></span> <span data-ttu-id="13fe1-105">Os snaps são uma ótima alternativa para o Gerenciador de pacotes incorporado à sua distribuição do Linux.</span><span class="sxs-lookup"><span data-stu-id="13fe1-105">Snaps are a great alternative to the package manager built into your Linux distribution.</span></span> <span data-ttu-id="13fe1-106">Este artigo descreve como instalar o .NET por meio do [snap](https://snapcraft.io/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="13fe1-106">This article describes how to install .NET through [Snap](https://snapcraft.io/dotnet-sdk).</span></span>

<span data-ttu-id="13fe1-107">Um snap é um pacote de um aplicativo e suas dependências que funcionam sem modificação em várias distribuições do Linux diferentes.</span><span class="sxs-lookup"><span data-stu-id="13fe1-107">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="13fe1-108">Os snaps são detectáveis e instaláveis no repositório de instantâneos.</span><span class="sxs-lookup"><span data-stu-id="13fe1-108">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="13fe1-109">Para obter mais informações sobre o snap, consulte [introdução ao snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="13fe1-109">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

> [!CAUTION]
> <span data-ttu-id="13fe1-110">Os pacotes snap não têm suporte no WSL2 no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="13fe1-110">Snap packages aren't supported in WSL2 on Windows 10.</span></span> <span data-ttu-id="13fe1-111">Como alternativa, use o [ `dotnet-install` script](linux-scripted-manual.md#scripted-install) ou o Gerenciador de pacotes para a distribuição WSL2 específica.</span><span class="sxs-lookup"><span data-stu-id="13fe1-111">As an alternative, use the [`dotnet-install` script](linux-scripted-manual.md#scripted-install) or the package manager for the particular WSL2 distribution.</span></span> <span data-ttu-id="13fe1-112">Não é recomendável, mas você pode tentar habilitar o snap com uma [solução alternativa sem suporte dos fóruns do snapcraft](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span><span class="sxs-lookup"><span data-stu-id="13fe1-112">It's not recommended but you can try to enable snap with an [unsupported workaround from the snapcraft forums](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span></span>

## <a name="net-releases"></a><span data-ttu-id="13fe1-113">Versões do .NET</span><span class="sxs-lookup"><span data-stu-id="13fe1-113">.NET releases</span></span>

<span data-ttu-id="13fe1-114">Somente ✔️ versões com suporte do SDK do .NET estão disponíveis por meio do snap.</span><span class="sxs-lookup"><span data-stu-id="13fe1-114">Only ✔️ supported versions of .NET SDK are available through Snap.</span></span> <span data-ttu-id="13fe1-115">Todas as versões do tempo de execução do .NET estão disponíveis por meio do snap, começando com a versão 2,1.</span><span class="sxs-lookup"><span data-stu-id="13fe1-115">All versions of the .NET Runtime are available through snap starting with version 2.1.</span></span> <span data-ttu-id="13fe1-116">A tabela a seguir lista as versões do .NET (e do .NET Core):</span><span class="sxs-lookup"><span data-stu-id="13fe1-116">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="13fe1-117">✔️ com suporte</span><span class="sxs-lookup"><span data-stu-id="13fe1-117">✔️ Supported</span></span> | <span data-ttu-id="13fe1-118">❌ Sem suporte</span><span class="sxs-lookup"><span data-stu-id="13fe1-118">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="13fe1-119">5.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-119">5.0</span></span>         | <span data-ttu-id="13fe1-120">3.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-120">3.0</span></span>           |
| <span data-ttu-id="13fe1-121">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-121">3.1 (LTS)</span></span>   | <span data-ttu-id="13fe1-122">2.2</span><span class="sxs-lookup"><span data-stu-id="13fe1-122">2.2</span></span>           |
| <span data-ttu-id="13fe1-123">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-123">2.1 (LTS)</span></span>   | <span data-ttu-id="13fe1-124">2,0</span><span class="sxs-lookup"><span data-stu-id="13fe1-124">2.0</span></span>           |
|             | <span data-ttu-id="13fe1-125">1,1</span><span class="sxs-lookup"><span data-stu-id="13fe1-125">1.1</span></span>           |
|             | <span data-ttu-id="13fe1-126">1.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-126">1.0</span></span>           |

<span data-ttu-id="13fe1-127">Para obter mais informações sobre o ciclo de vida de versões do .NET, consulte [.NET Core e .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="13fe1-127">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="sdk-or-runtime"></a><span data-ttu-id="13fe1-128">SDK ou tempo de execução</span><span class="sxs-lookup"><span data-stu-id="13fe1-128">SDK or Runtime</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a><span data-ttu-id="13fe1-129">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="13fe1-129">Install the SDK</span></span>

<span data-ttu-id="13fe1-130">Pacotes snap para o SDK do .NET são todos publicados sob o mesmo identificador: `dotnet-sdk` .</span><span class="sxs-lookup"><span data-stu-id="13fe1-130">Snap packages for the .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="13fe1-131">Uma versão específica do SDK pode ser instalada especificando o canal.</span><span class="sxs-lookup"><span data-stu-id="13fe1-131">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="13fe1-132">O SDK inclui o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="13fe1-132">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="13fe1-133">A tabela a seguir lista os canais:</span><span class="sxs-lookup"><span data-stu-id="13fe1-133">The following table lists the channels:</span></span>

| <span data-ttu-id="13fe1-134">Versão do .NET</span><span class="sxs-lookup"><span data-stu-id="13fe1-134">.NET version</span></span> | <span data-ttu-id="13fe1-135">Ajustar pacote ou canal</span><span class="sxs-lookup"><span data-stu-id="13fe1-135">Snap package or channel</span></span>  |
|--------------|--------------------------|
| <span data-ttu-id="13fe1-136">5.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-136">5.0</span></span>          | <span data-ttu-id="13fe1-137">`5.0` ou `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="13fe1-137">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="13fe1-138">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-138">3.1 (LTS)</span></span>    | <span data-ttu-id="13fe1-139">`3.1` ou `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="13fe1-139">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="13fe1-140">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-140">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="13fe1-141">Use o `snap install` comando para instalar um pacote de snap do SDK do .net.</span><span class="sxs-lookup"><span data-stu-id="13fe1-141">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="13fe1-142">Use o `--channel` parâmetro para indicar qual versão deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="13fe1-142">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="13fe1-143">Se esse parâmetro for omitido, `latest/stable` será usado.</span><span class="sxs-lookup"><span data-stu-id="13fe1-143">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="13fe1-144">Neste exemplo, `5.0` é especificado:</span><span class="sxs-lookup"><span data-stu-id="13fe1-144">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="13fe1-145">Em seguida, registre o `dotnet` comando para o sistema com o `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="13fe1-145">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="13fe1-146">Este comando é formatado como: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="13fe1-146">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="13fe1-147">Você pode escolher qualquer `{alias}` nome que desejar.</span><span class="sxs-lookup"><span data-stu-id="13fe1-147">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="13fe1-148">Por exemplo, você pode nomear o comando após a versão específica instalada pelo snap: `sudo snap alias dotnet-sdk.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="13fe1-148">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="13fe1-149">Ao usar o comando `dotnet50` , você invocará essa versão específica do .net.</span><span class="sxs-lookup"><span data-stu-id="13fe1-149">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="13fe1-150">Mas a escolha de um alias diferente é incompatível com a maioria dos tutoriais e exemplos, pois eles esperam que um `dotnet` comando seja usado.</span><span class="sxs-lookup"><span data-stu-id="13fe1-150">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be used.</span></span>

## <a name="install-the-runtime"></a><span data-ttu-id="13fe1-151">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="13fe1-151">Install the runtime</span></span>

<span data-ttu-id="13fe1-152">Os pacotes snap para o tempo de execução do .NET são publicados em seu próprio identificador de pacote.</span><span class="sxs-lookup"><span data-stu-id="13fe1-152">Snap packages for the .NET Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="13fe1-153">A tabela a seguir lista os identificadores de pacote:</span><span class="sxs-lookup"><span data-stu-id="13fe1-153">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="13fe1-154">Versão do .NET</span><span class="sxs-lookup"><span data-stu-id="13fe1-154">.NET version</span></span>      | <span data-ttu-id="13fe1-155">Ajustar pacote</span><span class="sxs-lookup"><span data-stu-id="13fe1-155">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="13fe1-156">5.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-156">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="13fe1-157">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-157">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="13fe1-158">3.0</span><span class="sxs-lookup"><span data-stu-id="13fe1-158">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="13fe1-159">2.2</span><span class="sxs-lookup"><span data-stu-id="13fe1-159">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="13fe1-160">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="13fe1-160">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="13fe1-161">Use o `snap install` comando para instalar um pacote de snap do tempo de execução .net.</span><span class="sxs-lookup"><span data-stu-id="13fe1-161">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="13fe1-162">Neste exemplo, o .NET 5,0 está instalado:</span><span class="sxs-lookup"><span data-stu-id="13fe1-162">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="13fe1-163">Em seguida, registre o `dotnet` comando para o sistema com o `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="13fe1-163">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="13fe1-164">O comando é formatado como: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="13fe1-164">The command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="13fe1-165">Você pode escolher qualquer `{alias}` nome que desejar.</span><span class="sxs-lookup"><span data-stu-id="13fe1-165">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="13fe1-166">Por exemplo, você pode nomear o comando após a versão específica instalada pelo snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="13fe1-166">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="13fe1-167">Ao usar o comando `dotnet50` , você invocará uma versão específica do .net.</span><span class="sxs-lookup"><span data-stu-id="13fe1-167">When you use the command `dotnet50`, you'll invoke a specific version of .NET.</span></span> <span data-ttu-id="13fe1-168">Mas a escolha de um alias diferente é incompatível com a maioria dos tutoriais e exemplos, pois eles esperam que um `dotnet` comando esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="13fe1-168">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

## <a name="tlsssl-certificate-errors"></a><span data-ttu-id="13fe1-169">Erros de certificado TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="13fe1-169">TLS/SSL Certificate errors</span></span>

<span data-ttu-id="13fe1-170">Quando o .NET é instalado por meio do snap, é possível que, em alguns distribuições, os certificados .NET TLS/SSL possam não ser encontrados e você receba um erro durante `restore` :</span><span class="sxs-lookup"><span data-stu-id="13fe1-170">When .NET is installed through Snap, it's possible that on some distros the .NET TLS/SSL certificates may not be found and you may receive an error during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="13fe1-171">Para resolver esse problema, defina algumas variáveis de ambiente:</span><span class="sxs-lookup"><span data-stu-id="13fe1-171">To resolve this problem, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="13fe1-172">O local do certificado variará de acordo com distribuição.</span><span class="sxs-lookup"><span data-stu-id="13fe1-172">The certificate location will vary by distro.</span></span> <span data-ttu-id="13fe1-173">Aqui estão os locais para o distribuições onde o problema foi experimentado.</span><span class="sxs-lookup"><span data-stu-id="13fe1-173">Here are the locations for the distros where the issue has been experienced.</span></span>

| <span data-ttu-id="13fe1-174">Distribuição</span><span class="sxs-lookup"><span data-stu-id="13fe1-174">Distribution</span></span> | <span data-ttu-id="13fe1-175">Localização</span><span class="sxs-lookup"><span data-stu-id="13fe1-175">Location</span></span>                                            |
|--------------|-----------------------------------------------------|
| <span data-ttu-id="13fe1-176">**Fedora**</span><span class="sxs-lookup"><span data-stu-id="13fe1-176">**Fedora**</span></span>   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| <span data-ttu-id="13fe1-177">**OpenSUSE**</span><span class="sxs-lookup"><span data-stu-id="13fe1-177">**OpenSUSE**</span></span> | `/etc/ssl/ca-bundle.pem`                            |
| <span data-ttu-id="13fe1-178">**Solus**</span><span class="sxs-lookup"><span data-stu-id="13fe1-178">**Solus**</span></span>    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a><span data-ttu-id="13fe1-179">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="13fe1-179">Next steps</span></span>

- [<span data-ttu-id="13fe1-180">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="13fe1-180">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="13fe1-181">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="13fe1-181">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
