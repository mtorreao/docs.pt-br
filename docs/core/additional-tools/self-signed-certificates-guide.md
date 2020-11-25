---
title: Gerar visão geral de certificados de Self-Signed
description: Uma visão geral da ferramenta de desenvolvimento/certificados do Microsoft dotnet que adiciona funcionalidade para projetos do .NET Core e ASP.NET Core e outras opções para usar certificados autoassinados.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: 15bbe3997ca34b503074595fa027bc6dfff1c0a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760349"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a><span data-ttu-id="0f975-103">Gerar certificados autoassinados com a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="0f975-103">Generate self-signed certificates with the .NET CLI</span></span>

<span data-ttu-id="0f975-104">Ao usar certificados autoassinados, há diferentes maneiras de criá-los e usá-los para cenários de desenvolvimento e teste.</span><span class="sxs-lookup"><span data-stu-id="0f975-104">When using self-signed certificates, there's different ways to create and use them for development and testing scenarios.</span></span>  <span data-ttu-id="0f975-105">Neste guia, você abordará o uso de certificados autoassinados com o e `dotnet dev-certs` outras opções como `PowerShell` e `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="0f975-105">In this guide, you'll cover using self-signed certificates with `dotnet dev-certs`, and other options like `PowerShell` and `OpenSSL`.</span></span>

<span data-ttu-id="0f975-106">Em seguida, você pode validar que o certificado será carregado usando um exemplo, como um [aplicativo ASP.NET Core](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hospedado em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="0f975-106">You can then validate that the certificate will load using an example such as an [ASP.NET Core app](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md) hosted in a container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f975-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0f975-107">Prerequisites</span></span>

<span data-ttu-id="0f975-108">No exemplo, você pode utilizar o `.netcore 3.1` ou o `.net 5` .</span><span class="sxs-lookup"><span data-stu-id="0f975-108">In the sample, you can utilize either `.netcore 3.1` or `.net 5`.</span></span>

<span data-ttu-id="0f975-109">Para `dotnet dev-certs` o, certifique-se de ter a versão apropriada do `dotnet` instalada:</span><span class="sxs-lookup"><span data-stu-id="0f975-109">For `dotnet dev-certs`, be sure to have the appropriate version of `dotnet` installed:</span></span>

* [<span data-ttu-id="0f975-110">Instalar dotnet no Windows</span><span class="sxs-lookup"><span data-stu-id="0f975-110">Install dotnet on Windows</span></span>](../install/windows.md)
* [<span data-ttu-id="0f975-111">Instalar o dotnet no Linux</span><span class="sxs-lookup"><span data-stu-id="0f975-111">Install dotnet on Linux</span></span>](../install/linux.md)
* [<span data-ttu-id="0f975-112">Instalar dotnet no macOS</span><span class="sxs-lookup"><span data-stu-id="0f975-112">Install dotnet on macOS</span></span>](../install/macos.md)

<span data-ttu-id="0f975-113">Este exemplo requer o [docker 17, 6](https://docs.docker.com/release-notes/docker-ce) ou posterior do [cliente do Docker](https://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="0f975-113">This sample requires [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) or later of the [Docker client](https://www.docker.com/products/docker).</span></span>

## <a name="prepare-sample-app"></a><span data-ttu-id="0f975-114">Preparar aplicativo de exemplo</span><span class="sxs-lookup"><span data-stu-id="0f975-114">Prepare sample app</span></span>

<span data-ttu-id="0f975-115">Você precisará preparar o aplicativo de exemplo dependendo de qual tempo de execução você gostaria de usar para teste.</span><span class="sxs-lookup"><span data-stu-id="0f975-115">You'll need to prepare the sample app depending on which runtime you'd like to use for testing.</span></span>

<span data-ttu-id="0f975-116">Para este guia, você usará um [aplicativo de exemplo](https://hub.docker.com/_/microsoft-dotnet-samples) e fará alterações quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="0f975-116">For this guide, you'll be using a [sample app](https://hub.docker.com/_/microsoft-dotnet-samples) and make changes where appropriate.</span></span>

### <a name="prepare-net-core-31-sample-app"></a><span data-ttu-id="0f975-117">Preparar aplicativo de exemplo do .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="0f975-117">Prepare .NET Core 3.1 sample app</span></span>

<span data-ttu-id="0f975-118">Obter o aplicativo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0f975-118">Get the sample app.</span></span>

```console
git clone https://github.com/dotnet/dotnet-docker/
```

<span data-ttu-id="0f975-119">Navegue até o repositório localmente e abra o espaço de trabalho em um editor.</span><span class="sxs-lookup"><span data-stu-id="0f975-119">Navigate to the repository locally and open up the workspace in an editor.</span></span>

> [!NOTE]
> <span data-ttu-id="0f975-120">Se você pretende usar dotnet publish parâmetros para *cortar* a implantação, certifique-se de que as dependências apropriadas estejam incluídas para dar suporte a certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="0f975-120">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="0f975-121">Atualize o [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para garantir que os assemblies apropriados sejam incluídos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="0f975-121">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="0f975-122">Para referência, verifique como atualizar o arquivo. csproj para [dar suporte a certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) ao usar o corte para implantações independentes.</span><span class="sxs-lookup"><span data-stu-id="0f975-122">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="0f975-123">Certifique-se de que o `aspnetapp.csproj` inclui a estrutura de destino apropriada:</span><span class="sxs-lookup"><span data-stu-id="0f975-123">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

<span data-ttu-id="0f975-124">Modifique o Dockerfile para certificar-se de que o tempo de execução aponta para. NetCore 3,1:</span><span class="sxs-lookup"><span data-stu-id="0f975-124">Modify the Dockerfile to make sure the runtime points to .netcore 3.1:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

<span data-ttu-id="0f975-125">Verifique se você está apontando para o aplicativo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0f975-125">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="0f975-126">Crie o contêiner para teste local.</span><span class="sxs-lookup"><span data-stu-id="0f975-126">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="prepare-net-5-sample-app"></a><span data-ttu-id="0f975-127">Preparar aplicativo de exemplo do .NET 5</span><span class="sxs-lookup"><span data-stu-id="0f975-127">Prepare .NET 5 sample app</span></span>

<span data-ttu-id="0f975-128">Para este guia, o [exemplo de aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) deve ser verificado para o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="0f975-128">For this guide, the [sample aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) should be checked for .net 5.</span></span>

<span data-ttu-id="0f975-129">Verifique se o aplicativo de exemplo [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) está usando o .NET 5.</span><span class="sxs-lookup"><span data-stu-id="0f975-129">Check sample app [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) is using .net 5.</span></span>

<span data-ttu-id="0f975-130">Dependendo do sistema operacional do host, talvez seja necessário atualizar o tempo de execução do ASPNET.</span><span class="sxs-lookup"><span data-stu-id="0f975-130">Depending on the host os, the aspnet runtime may need to be updated.</span></span> <span data-ttu-id="0f975-131">Por exemplo, alterar de `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` para `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` no Dockerfile ajudará a direcionar o tempo de execução do Windows apropriado.</span><span class="sxs-lookup"><span data-stu-id="0f975-131">For example, changing from `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` to `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` in the Dockerfile will help with targeting the appropriate Windows runtime.</span></span>

<span data-ttu-id="0f975-132">Por exemplo, isso ajudará no teste dos certificados no Windows:</span><span class="sxs-lookup"><span data-stu-id="0f975-132">For example, this will help with testing the certificates on Windows:</span></span>

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

<span data-ttu-id="0f975-133">Se estiver testando os certificados no Linux, você poderá usar o Dockerfile existente.</span><span class="sxs-lookup"><span data-stu-id="0f975-133">If we're testing the certificates on Linux, you can use the existing Dockerfile.</span></span>

<span data-ttu-id="0f975-134">Certifique-se de que o `aspnetapp.csproj` inclui a estrutura de destino apropriada:</span><span class="sxs-lookup"><span data-stu-id="0f975-134">Make sure the `aspnetapp.csproj` includes the appropriate target framework:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> <span data-ttu-id="0f975-135">Se você pretende usar dotnet publish parâmetros para *cortar* a implantação, certifique-se de que as dependências apropriadas estejam incluídas para dar suporte a certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="0f975-135">If you're looking to use dotnet publish parameters to *trim* the deployment, you should make sure that the appropriate dependencies are included for supporting SSL certificates.</span></span>
<span data-ttu-id="0f975-136">Atualize o [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) para garantir que os assemblies apropriados sejam incluídos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="0f975-136">Update the [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj) to ensure that the appropriate assemblies are included in the container.</span></span> <span data-ttu-id="0f975-137">Para referência, verifique como atualizar o arquivo. csproj para [dar suporte a certificados SSL](../deploying/trim-self-contained.md#support-for-ssl-certificates) ao usar o corte para implantações independentes.</span><span class="sxs-lookup"><span data-stu-id="0f975-137">For reference, check how to update the .csproj file to [support ssl certificates](../deploying/trim-self-contained.md#support-for-ssl-certificates) when using trimming for self-contained deployments.</span></span>

<span data-ttu-id="0f975-138">Verifique se você está apontando para o aplicativo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="0f975-138">Make sure you're pointing to the sample app.</span></span>

```console
cd .\dotnet-docker\samples\aspnetapp
```

<span data-ttu-id="0f975-139">Crie o contêiner para teste local.</span><span class="sxs-lookup"><span data-stu-id="0f975-139">Build the container for testing locally.</span></span>

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate-with-dotnet-dev-certs"></a><span data-ttu-id="0f975-140">Criar um certificado autoassinado com o dotnet dev-certs</span><span class="sxs-lookup"><span data-stu-id="0f975-140">Create a self-signed certificate with dotnet dev-certs</span></span>

<span data-ttu-id="0f975-141">Você pode usar o `dotnet dev-certs` para trabalhar com certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="0f975-141">You can use `dotnet dev-certs` to work with self-signed certificates.</span></span> <span data-ttu-id="0f975-142">Este exemplo usa um console do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f975-142">This example uses a PowerShell console.</span></span>

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> <span data-ttu-id="0f975-143">O nome do certificado, nesse caso, *aspnetapp*. pfx, deve corresponder ao nome do assembly do projeto.</span><span class="sxs-lookup"><span data-stu-id="0f975-143">The certificate name, in this case *aspnetapp*.pfx must match the project assembly name.</span></span> <span data-ttu-id="0f975-144">`crypticpassword` é usado como um substituto para uma senha de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="0f975-144">`crypticpassword` is used as a stand-in for a password of your own choosing.</span></span> <span data-ttu-id="0f975-145">Se o console retornar "um certificado HTTPS válido já está presente.", um certificado confiável já existe em seu repositório.</span><span class="sxs-lookup"><span data-stu-id="0f975-145">If console returns "A valid HTTPS certificate is already present.", a trusted certificate already exists in your store.</span></span> <span data-ttu-id="0f975-146">Ele pode ser exportado usando o console do MMC.</span><span class="sxs-lookup"><span data-stu-id="0f975-146">It can be exported using MMC Console.</span></span>

<span data-ttu-id="0f975-147">Configure os segredos do aplicativo para o certificado:</span><span class="sxs-lookup"><span data-stu-id="0f975-147">Configure application secrets, for the certificate:</span></span>

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> <span data-ttu-id="0f975-148">Observação: a senha deve corresponder à senha usada para o certificado.</span><span class="sxs-lookup"><span data-stu-id="0f975-148">Note: The password must match the password used for the certificate.</span></span>

<span data-ttu-id="0f975-149">Execute a imagem de contêiner com ASP.NET Core configurado para HTTPS:</span><span class="sxs-lookup"><span data-stu-id="0f975-149">Run the container image with ASP.NET Core configured for HTTPS:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="0f975-150">Depois que o aplicativo for iniciado, navegue até `https://localhost:8001` no navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="0f975-150">Once the application starts, navigate to `https://localhost:8001` in your web browser.</span></span>

### <a name="clean-up"></a><span data-ttu-id="0f975-151">Limpeza</span><span class="sxs-lookup"><span data-stu-id="0f975-151">Clean up</span></span>

<span data-ttu-id="0f975-152">Se os segredos e certificados não estiverem em uso, certifique-se de limpá-los.</span><span class="sxs-lookup"><span data-stu-id="0f975-152">If the secrets and certificates are not in use, be sure to clean them up.</span></span>

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

## <a name="create-a-self-signed-certificate-with-powershell"></a><span data-ttu-id="0f975-153">Criar um certificado autoassinado com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f975-153">Create a self-signed certificate with PowerShell</span></span>

<span data-ttu-id="0f975-154">Você pode usar o PowerShell para gerar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="0f975-154">You can use PowerShell to generate self-signed certificates.</span></span> <span data-ttu-id="0f975-155">O [cliente PKI](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) pode ser usado para gerar um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="0f975-155">The [PKI Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true) can be used to generate a self-signed certificate.</span></span>

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

<span data-ttu-id="0f975-156">O certificado será gerado, mas, para fins de teste, deve ser colocado em um repositório de certificados para teste em um navegador.</span><span class="sxs-lookup"><span data-stu-id="0f975-156">The certificate will be generated, but for the purposes of testing, should be placed in a cert store for testing in a browser.</span></span>

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

<span data-ttu-id="0f975-157">Neste ponto, os certificados devem ser exibidos em um [snap-in do MMC](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="0f975-157">At this point, the certificates should be viewable from an [MMC snap-in](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

<span data-ttu-id="0f975-158">Você pode executar o contêiner de exemplo no subsistema do Windows para Linux (WSL):</span><span class="sxs-lookup"><span data-stu-id="0f975-158">You can run the sample container in Windows Subsystem for Linux (WSL):</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="0f975-159">Observe que, com a montagem de volume, o caminho do arquivo poderia ser tratado diferentemente com base no host.</span><span class="sxs-lookup"><span data-stu-id="0f975-159">Note that with the volume mount the file path could be handled differently based on host.</span></span>  <span data-ttu-id="0f975-160">Por exemplo, em WSL, poderemos substituir */c/certs* por */mnt/c/certs*.</span><span class="sxs-lookup"><span data-stu-id="0f975-160">For example, in WSL we may replace */c/certs* with */mnt/c/certs*.</span></span>

<span data-ttu-id="0f975-161">Se você estiver usando o contêiner criado anteriormente para o Windows, o comando executar será semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f975-161">If you're using the container built earlier for Windows, the run command would look like the following:</span></span>

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="0f975-162">Quando o aplicativo estiver ativo, navegue até contoso.com:8001 em um navegador.</span><span class="sxs-lookup"><span data-stu-id="0f975-162">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="0f975-163">Certifique-se de que as entradas de host sejam atualizadas para `contoso.com` que respondam no endereço IP apropriado (por exemplo, 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="0f975-163">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="0f975-164">Se o certificado não for reconhecido, verifique se o certificado carregado com o contêiner também é confiável no host e se há entradas apropriadas de SAN/DNS para o `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0f975-164">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

### <a name="clean-up"></a><span data-ttu-id="0f975-165">Limpeza</span><span class="sxs-lookup"><span data-stu-id="0f975-165">Clean up</span></span>

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

## <a name="create-a-self-signed-certificate-with-openssl"></a><span data-ttu-id="0f975-166">Criar um certificado autoassinado com OpenSSL</span><span class="sxs-lookup"><span data-stu-id="0f975-166">Create a self-signed certificate with OpenSSL</span></span>

<span data-ttu-id="0f975-167">Você pode usar o [OpenSSL](https://www.openssl.org/) para criar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="0f975-167">You can use [OpenSSL](https://www.openssl.org/) to create self-signed certificates.</span></span> <span data-ttu-id="0f975-168">Este exemplo usará o WSL/Ubuntu e um shell bash com `OpenSSL` .</span><span class="sxs-lookup"><span data-stu-id="0f975-168">This example will use WSL / Ubuntu and a bash shell with `OpenSSL`.</span></span>

<span data-ttu-id="0f975-169">Isso irá gerar um. CRT e uma. Key.</span><span class="sxs-lookup"><span data-stu-id="0f975-169">This will generate a .crt and a .key.</span></span>

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

<span data-ttu-id="0f975-170">Para obter um. pfx, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0f975-170">To get a .pfx, use the following command:</span></span>

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> <span data-ttu-id="0f975-171">O exemplo. aspnetcore 3,1 usará `.pfx` e uma senha.</span><span class="sxs-lookup"><span data-stu-id="0f975-171">The .aspnetcore 3.1 example will use `.pfx` and a password.</span></span> <span data-ttu-id="0f975-172">Começando com o `.net 5` tempo de execução, o Kestrel também pode pegar `.crt` arquivos codificados por PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="0f975-172">Starting with the `.net 5` runtime, Kestrel can also take `.crt` and PEM-encoded `.key` files.</span></span>

<span data-ttu-id="0f975-173">Dependendo do sistema operacional do host, o certificado precisará ser confiável.</span><span class="sxs-lookup"><span data-stu-id="0f975-173">Depending on the host os, the certificate will need to be trusted.</span></span> <span data-ttu-id="0f975-174">Em um host Linux, ' confiar ' o certificado é diferente e distribuição dependente.</span><span class="sxs-lookup"><span data-stu-id="0f975-174">On a Linux host, 'trusting' the certificate is different and distro dependent.</span></span>

<span data-ttu-id="0f975-175">Para os fins deste guia, veja um exemplo no Windows usando o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0f975-175">For the purposes of this guide, here's an example in Windows using PowerShell:</span></span>

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

<span data-ttu-id="0f975-176">Para o .NET Core 3,1, execute o seguinte comando em WSL:</span><span class="sxs-lookup"><span data-stu-id="0f975-176">For .NET Core 3.1, run the following command in WSL:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

<span data-ttu-id="0f975-177">A partir do .NET 5, o Kestrel pode pegar os `.crt` arquivos codificados por PEM `.key` .</span><span class="sxs-lookup"><span data-stu-id="0f975-177">Starting with .NET 5, Kestrel can take the `.crt` and PEM-encoded `.key` files.</span></span> <span data-ttu-id="0f975-178">Você pode executar o exemplo com o seguinte comando para o .NET 5:</span><span class="sxs-lookup"><span data-stu-id="0f975-178">You can run the sample with the following command for .NET 5:</span></span>

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> <span data-ttu-id="0f975-179">Observe que no WSL, o caminho de montagem do volume pode ser alterado dependendo da configuração.</span><span class="sxs-lookup"><span data-stu-id="0f975-179">Note that in WSL, the volume mount path may change depending on the configuration.</span></span>

<span data-ttu-id="0f975-180">Para o .NET Core 3,1 no Windows, execute o seguinte comando no `Powershell` :</span><span class="sxs-lookup"><span data-stu-id="0f975-180">For .NET Core 3.1 in Windows, run the following command in `Powershell`:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="0f975-181">Para o .NET 5 no Windows, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0f975-181">For .NET 5 in Windows, run the following command in PowerShell:</span></span>

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

<span data-ttu-id="0f975-182">Quando o aplicativo estiver ativo, navegue até contoso.com:8001 em um navegador.</span><span class="sxs-lookup"><span data-stu-id="0f975-182">Once the application is up, navigate to contoso.com:8001 in a browser.</span></span>

<span data-ttu-id="0f975-183">Certifique-se de que as entradas de host sejam atualizadas para `contoso.com` que respondam no endereço IP apropriado (por exemplo, 127.0.0.1).</span><span class="sxs-lookup"><span data-stu-id="0f975-183">Be sure that the host entries are updated for `contoso.com` to answer on  the appropriate ip address (for example 127.0.0.1).</span></span> <span data-ttu-id="0f975-184">Se o certificado não for reconhecido, verifique se o certificado carregado com o contêiner também é confiável no host e se há entradas apropriadas de SAN/DNS para o `contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0f975-184">If the certificate isn't recognized, make sure that the certificate that is loaded with the container is also trusted on the host, and that there's appropriate SAN / DNS entries for `contoso.com`.</span></span>

### <a name="clean-up"></a><span data-ttu-id="0f975-185">Limpeza</span><span class="sxs-lookup"><span data-stu-id="0f975-185">Clean up</span></span>

<span data-ttu-id="0f975-186">Certifique-se de limpar os certificados autoassinados depois de fazer o teste.</span><span class="sxs-lookup"><span data-stu-id="0f975-186">Be sure to clean up the self-signed certificates once done testing.</span></span>

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
