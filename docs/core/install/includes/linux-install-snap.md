---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031744"
---

[<span data-ttu-id="5b72c-101">O .NET Core está disponível no repositório de snap.</span><span class="sxs-lookup"><span data-stu-id="5b72c-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="5b72c-102">Um snap é um pacote de um aplicativo e suas dependências que funcionam sem modificação em várias distribuições do Linux diferentes.</span><span class="sxs-lookup"><span data-stu-id="5b72c-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="5b72c-103">Os snaps são detectáveis e instaláveis no repositório de instantâneos.</span><span class="sxs-lookup"><span data-stu-id="5b72c-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="5b72c-104">Para obter mais informações sobre o snap, consulte [introdução ao snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="5b72c-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="5b72c-105">Somente as versões com suporte do .NET Core estão disponíveis por meio do snap.</span><span class="sxs-lookup"><span data-stu-id="5b72c-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="5b72c-106">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="5b72c-106">Install the SDK</span></span>

<span data-ttu-id="5b72c-107">Pacotes snap para SDK do .NET são todos publicados sob o mesmo identificador: `dotnet-sdk` .</span><span class="sxs-lookup"><span data-stu-id="5b72c-107">Snap packages for .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="5b72c-108">Uma versão específica do SDK pode ser instalada especificando o canal.</span><span class="sxs-lookup"><span data-stu-id="5b72c-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="5b72c-109">O SDK inclui o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="5b72c-109">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="5b72c-110">A tabela a seguir lista os canais:</span><span class="sxs-lookup"><span data-stu-id="5b72c-110">The following table lists the channels:</span></span>

| <span data-ttu-id="5b72c-111">Versão do .NET</span><span class="sxs-lookup"><span data-stu-id="5b72c-111">.NET version</span></span> | <span data-ttu-id="5b72c-112">Ajustar pacote</span><span class="sxs-lookup"><span data-stu-id="5b72c-112">Snap package</span></span>             |
|--------------|--------------------------|
| <span data-ttu-id="5b72c-113">5.0</span><span class="sxs-lookup"><span data-stu-id="5b72c-113">5.0</span></span>          | <span data-ttu-id="5b72c-114">`5.0` ou `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="5b72c-114">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="5b72c-115">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="5b72c-115">3.1 (LTS)</span></span>    | <span data-ttu-id="5b72c-116">`3.1` ou `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="5b72c-116">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="5b72c-117">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="5b72c-117">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="5b72c-118">Use o `snap install` comando para instalar um pacote de snap do SDK do .net.</span><span class="sxs-lookup"><span data-stu-id="5b72c-118">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="5b72c-119">Use o `--channel` parâmetro para indicar qual versão deve ser instalada.</span><span class="sxs-lookup"><span data-stu-id="5b72c-119">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="5b72c-120">Se esse parâmetro for omitido, `latest/stable` será usado.</span><span class="sxs-lookup"><span data-stu-id="5b72c-120">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="5b72c-121">Neste exemplo, `5.0` é especificado:</span><span class="sxs-lookup"><span data-stu-id="5b72c-121">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="5b72c-122">Em seguida, registre o `dotnet` comando para o sistema com o `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="5b72c-122">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="5b72c-123">Este comando é formatado como: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="5b72c-123">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="5b72c-124">Você pode escolher qualquer `{alias}` nome que desejar.</span><span class="sxs-lookup"><span data-stu-id="5b72c-124">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="5b72c-125">Por exemplo, você pode nomear o comando após a versão específica instalada pelo snap: `sudo snap alias dotnet-sdk.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="5b72c-125">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="5b72c-126">Ao usar o comando `dotnet50` , você invocará essa versão específica do .net.</span><span class="sxs-lookup"><span data-stu-id="5b72c-126">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="5b72c-127">Mas isso é incompatível com a maioria dos tutoriais e exemplos, pois eles esperam que um `dotnet` comando esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="5b72c-127">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="5b72c-128">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="5b72c-128">Install the runtime</span></span>

<span data-ttu-id="5b72c-129">Os pacotes snap para o tempo de execução do .NET Core são publicados em seu próprio identificador de pacote.</span><span class="sxs-lookup"><span data-stu-id="5b72c-129">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="5b72c-130">A tabela a seguir lista os identificadores de pacote:</span><span class="sxs-lookup"><span data-stu-id="5b72c-130">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="5b72c-131">Versão do .NET</span><span class="sxs-lookup"><span data-stu-id="5b72c-131">.NET version</span></span>      | <span data-ttu-id="5b72c-132">Ajustar pacote</span><span class="sxs-lookup"><span data-stu-id="5b72c-132">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="5b72c-133">5.0</span><span class="sxs-lookup"><span data-stu-id="5b72c-133">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="5b72c-134">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="5b72c-134">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="5b72c-135">3.0</span><span class="sxs-lookup"><span data-stu-id="5b72c-135">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="5b72c-136">2.2</span><span class="sxs-lookup"><span data-stu-id="5b72c-136">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="5b72c-137">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="5b72c-137">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="5b72c-138">Use o `snap install` comando para instalar um pacote de snap do tempo de execução .net.</span><span class="sxs-lookup"><span data-stu-id="5b72c-138">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="5b72c-139">Neste exemplo, o .NET 5,0 está instalado:</span><span class="sxs-lookup"><span data-stu-id="5b72c-139">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="5b72c-140">Em seguida, registre o `dotnet` comando para o sistema com o `snap alias` comando:</span><span class="sxs-lookup"><span data-stu-id="5b72c-140">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="5b72c-141">Este comando é formatado como: `sudo snap alias {package}.{command} {alias}` .</span><span class="sxs-lookup"><span data-stu-id="5b72c-141">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="5b72c-142">Você pode escolher qualquer `{alias}` nome que desejar.</span><span class="sxs-lookup"><span data-stu-id="5b72c-142">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="5b72c-143">Por exemplo, você pode nomear o comando após a versão específica instalada pelo snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50` .</span><span class="sxs-lookup"><span data-stu-id="5b72c-143">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="5b72c-144">Ao usar o comando `dotnet50` , você invocará essa versão específica do .net.</span><span class="sxs-lookup"><span data-stu-id="5b72c-144">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="5b72c-145">Mas isso é incompatível com a maioria dos tutoriais e exemplos, pois eles esperam que um `dotnet` comando esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="5b72c-145">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="5b72c-146">Erros de certificado SSL</span><span class="sxs-lookup"><span data-stu-id="5b72c-146">SSL Certificate errors</span></span>

<span data-ttu-id="5b72c-147">Quando o .NET é instalado por meio do snap, é possível que, em alguns distribuições, os certificados SSL do .NET possam não ser encontrados e você receba um erro semelhante ao seguinte durante `restore` :</span><span class="sxs-lookup"><span data-stu-id="5b72c-147">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="5b72c-148">Para resolver esse problema, defina algumas variáveis de ambiente:</span><span class="sxs-lookup"><span data-stu-id="5b72c-148">To resolve this issue, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="5b72c-149">O local do certificado variará de acordo com distribuição.</span><span class="sxs-lookup"><span data-stu-id="5b72c-149">The certificate location will vary by distro.</span></span> <span data-ttu-id="5b72c-150">Aqui estão os locais para o distribuições onde tivemos o problema.</span><span class="sxs-lookup"><span data-stu-id="5b72c-150">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="5b72c-151">Fedora `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="5b72c-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="5b72c-152">OpenSUSE `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="5b72c-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="5b72c-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="5b72c-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>
