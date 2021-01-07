---
title: Instalar manualmente o .NET no Linux-.NET
description: Demonstra como instalar o SDK do .NET e o tempo de execução do .NET sem um Gerenciador de pacotes no Linux. Use o script de instalação ou extraia os binários manualmente.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 5879d4d66aba8bfa00caadbe3c33d6df0d7da59a
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970959"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a><span data-ttu-id="d7da9-104">Instalar o SDK do .NET ou o tempo de execução do .NET manualmente</span><span class="sxs-lookup"><span data-stu-id="d7da9-104">Install the .NET SDK or the .NET Runtime manually</span></span>

<span data-ttu-id="d7da9-105">O .NET tem suporte no Linux e este artigo descreve como instalar o .NET no Linux usando o script de instalação ou extraindo os binários.</span><span class="sxs-lookup"><span data-stu-id="d7da9-105">.NET is supported on Linux and this article describes how to install .NET on Linux using the install script or by extracting the binaries.</span></span> <span data-ttu-id="d7da9-106">Para obter uma lista de distribuições que dão suporte ao Gerenciador de pacotes interno, consulte [instalar o .net no Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="d7da9-106">For a list of distributions that support the built-in package manager, see [Install .NET on Linux](linux.md).</span></span>

<span data-ttu-id="d7da9-107">Você também pode instalar o .NET com snap.</span><span class="sxs-lookup"><span data-stu-id="d7da9-107">You can also install .NET with snap.</span></span> <span data-ttu-id="d7da9-108">Para obter mais informações, consulte [instalar o SDK do .net ou o tempo de execução do .NET com snap](linux-snap.md).</span><span class="sxs-lookup"><span data-stu-id="d7da9-108">For more information, see [Install the .NET SDK or the .NET Runtime with Snap](linux-snap.md).</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a><span data-ttu-id="d7da9-109">Versões do .NET</span><span class="sxs-lookup"><span data-stu-id="d7da9-109">.NET releases</span></span>

<span data-ttu-id="d7da9-110">A tabela a seguir lista as versões do .NET (e do .NET Core):</span><span class="sxs-lookup"><span data-stu-id="d7da9-110">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="d7da9-111">✔️ com suporte</span><span class="sxs-lookup"><span data-stu-id="d7da9-111">✔️ Supported</span></span> | <span data-ttu-id="d7da9-112">❌ Sem suporte</span><span class="sxs-lookup"><span data-stu-id="d7da9-112">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="d7da9-113">5.0</span><span class="sxs-lookup"><span data-stu-id="d7da9-113">5.0</span></span>         | <span data-ttu-id="d7da9-114">3.0</span><span class="sxs-lookup"><span data-stu-id="d7da9-114">3.0</span></span>           |
| <span data-ttu-id="d7da9-115">3,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="d7da9-115">3.1 (LTS)</span></span>   | <span data-ttu-id="d7da9-116">2.2</span><span class="sxs-lookup"><span data-stu-id="d7da9-116">2.2</span></span>           |
| <span data-ttu-id="d7da9-117">2,1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="d7da9-117">2.1 (LTS)</span></span>   | <span data-ttu-id="d7da9-118">2,0</span><span class="sxs-lookup"><span data-stu-id="d7da9-118">2.0</span></span>           |
|             | <span data-ttu-id="d7da9-119">1,1</span><span class="sxs-lookup"><span data-stu-id="d7da9-119">1.1</span></span>           |
|             | <span data-ttu-id="d7da9-120">1.0</span><span class="sxs-lookup"><span data-stu-id="d7da9-120">1.0</span></span>           |

<span data-ttu-id="d7da9-121">Para obter mais informações sobre o ciclo de vida de versões do .NET, consulte [.NET Core e .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="d7da9-121">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="dependencies"></a><span data-ttu-id="d7da9-122">Dependências</span><span class="sxs-lookup"><span data-stu-id="d7da9-122">Dependencies</span></span>

<span data-ttu-id="d7da9-123">É possível que, ao instalar o .NET, as dependências específicas não sejam instaladas, como durante a [instalação manual](#manual-install)do.</span><span class="sxs-lookup"><span data-stu-id="d7da9-123">It's possible that when you install .NET, specific dependencies may not be installed, such as when [manually installing](#manual-install).</span></span> <span data-ttu-id="d7da9-124">A lista a seguir fornece detalhes sobre as distribuições do Linux com suporte da Microsoft e tem dependências que talvez você precise instalar.</span><span class="sxs-lookup"><span data-stu-id="d7da9-124">The following list details Linux distributions that are supported by Microsoft and have dependencies you may need to install.</span></span> <span data-ttu-id="d7da9-125">Verifique a página de distribuição para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="d7da9-125">Check the distribution page for more information:</span></span>

- [<span data-ttu-id="d7da9-126">Alpine</span><span class="sxs-lookup"><span data-stu-id="d7da9-126">Alpine</span></span>](linux-alpine.md#dependencies)
- [<span data-ttu-id="d7da9-127">Debian</span><span class="sxs-lookup"><span data-stu-id="d7da9-127">Debian</span></span>](linux-debian.md#dependencies)
- [<span data-ttu-id="d7da9-128">CentOS</span><span class="sxs-lookup"><span data-stu-id="d7da9-128">CentOS</span></span>](linux-centos.md#dependencies)
- [<span data-ttu-id="d7da9-129">Fedora</span><span class="sxs-lookup"><span data-stu-id="d7da9-129">Fedora</span></span>](linux-fedora.md#dependencies)
- [<span data-ttu-id="d7da9-130">RHEL</span><span class="sxs-lookup"><span data-stu-id="d7da9-130">RHEL</span></span>](linux-rhel.md#dependencies)
- [<span data-ttu-id="d7da9-131">SLES</span><span class="sxs-lookup"><span data-stu-id="d7da9-131">SLES</span></span>](linux-sles.md#dependencies)
- [<span data-ttu-id="d7da9-132">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d7da9-132">Ubuntu</span></span>](linux-ubuntu.md#dependencies)

<span data-ttu-id="d7da9-133">Para obter informações genéricas sobre as dependências, consulte [aplicativos do Linux autocontidos](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="d7da9-133">For generic information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

### <a name="rpm-dependencies"></a><span data-ttu-id="d7da9-134">Dependências de RPM</span><span class="sxs-lookup"><span data-stu-id="d7da9-134">RPM dependencies</span></span>

<span data-ttu-id="d7da9-135">Se a distribuição não tiver sido listada anteriormente e for baseada em RPM, talvez você precise das seguintes dependências:</span><span class="sxs-lookup"><span data-stu-id="d7da9-135">If your distribution wasn't previously listed, and is RPM-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="d7da9-136">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="d7da9-136">krb5-libs</span></span>
- <span data-ttu-id="d7da9-137">libicu</span><span class="sxs-lookup"><span data-stu-id="d7da9-137">libicu</span></span>
- <span data-ttu-id="d7da9-138">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="d7da9-138">openssl-libs</span></span>

<span data-ttu-id="d7da9-139">Se a versão do OpenSSL do ambiente de tempo de execução de destino for 1,1 ou mais recente, você precisará instalar o **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="d7da9-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

### <a name="deb-dependencies"></a><span data-ttu-id="d7da9-140">Dependências de DEB</span><span class="sxs-lookup"><span data-stu-id="d7da9-140">DEB dependencies</span></span>

<span data-ttu-id="d7da9-141">Se sua distribuição não foi listada anteriormente e for baseada em Debian, talvez você precise das seguintes dependências:</span><span class="sxs-lookup"><span data-stu-id="d7da9-141">If your distribution wasn't previously listed, and is debian-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="d7da9-142">libc6</span><span class="sxs-lookup"><span data-stu-id="d7da9-142">libc6</span></span>
- <span data-ttu-id="d7da9-143">libgcc1</span><span class="sxs-lookup"><span data-stu-id="d7da9-143">libgcc1</span></span>
- <span data-ttu-id="d7da9-144">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="d7da9-144">libgssapi-krb5-2</span></span>
- <span data-ttu-id="d7da9-145">libicu67</span><span class="sxs-lookup"><span data-stu-id="d7da9-145">libicu67</span></span>
- <span data-ttu-id="d7da9-146">libssl 1.1</span><span class="sxs-lookup"><span data-stu-id="d7da9-146">libssl1.1</span></span>
- <span data-ttu-id="d7da9-147">libstdc + + 6</span><span class="sxs-lookup"><span data-stu-id="d7da9-147">libstdc++6</span></span>
- <span data-ttu-id="d7da9-148">zlib1g</span><span class="sxs-lookup"><span data-stu-id="d7da9-148">zlib1g</span></span>

### <a name="common-dependencies"></a><span data-ttu-id="d7da9-149">Dependências comuns</span><span class="sxs-lookup"><span data-stu-id="d7da9-149">Common dependencies</span></span>

<span data-ttu-id="d7da9-150">Para aplicativos .NET que usam o assembly *System. Drawing. Common* , você também precisará da seguinte dependência:</span><span class="sxs-lookup"><span data-stu-id="d7da9-150">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="d7da9-151">libgdiplus (versão 6.0.1 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="d7da9-151">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="d7da9-152">Você pode instalar uma versão recente do *libgdiplus* adicionando o repositório do mono ao seu sistema.</span><span class="sxs-lookup"><span data-stu-id="d7da9-152">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="d7da9-153">Para obter mais informações, consulte <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="d7da9-153">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="d7da9-154">Instalação com script</span><span class="sxs-lookup"><span data-stu-id="d7da9-154">Scripted install</span></span>

<span data-ttu-id="d7da9-155">Os [scripts dotnet-install](../tools/dotnet-install-script.md) são usados para instalações de automação e não administrativas do **SDK** e do **tempo de execução**.</span><span class="sxs-lookup"><span data-stu-id="d7da9-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="d7da9-156">É possível baixar o script em <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="d7da9-156">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="d7da9-157">O script assume como padrão a instalação da versão mais recente do [LTS (suporte a longo prazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) do SDK, que é o .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="d7da9-157">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d7da9-158">Para instalar a versão atual, que pode não ser uma versão (LTS), use o `-c Current` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7da9-158">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="d7da9-159">Para instalar o tempo de execução do .NET em vez do SDK, use o `--runtime` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d7da9-159">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="d7da9-160">Você pode instalar uma versão específica alterando o `-c` parâmetro para indicar a versão específica.</span><span class="sxs-lookup"><span data-stu-id="d7da9-160">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="d7da9-161">O comando a seguir instala o SDK do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="d7da9-161">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="d7da9-162">Para obter mais informações, consulte [dotnet – referência de scripts de instalação](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="d7da9-162">For more information, see [dotnet-install scripts reference](../tools/dotnet-install-script.md).</span></span>

## <a name="manual-install"></a><span data-ttu-id="d7da9-163">Instalação manual</span><span class="sxs-lookup"><span data-stu-id="d7da9-163">Manual install</span></span>

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="d7da9-164">Como alternativa para os gerenciadores de pacotes, você pode baixar e instalar manualmente o SDK e o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d7da9-164">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="d7da9-165">A instalação manual é normalmente usada como parte do teste de integração contínua ou em uma distribuição do Linux sem suporte.</span><span class="sxs-lookup"><span data-stu-id="d7da9-165">Manual install is commonly used as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="d7da9-166">Para um desenvolvedor ou usuário, é melhor usar um Gerenciador de pacotes.</span><span class="sxs-lookup"><span data-stu-id="d7da9-166">For a developer or user, it's better to use a package manager.</span></span>

<span data-ttu-id="d7da9-167">Se você instalar o SDK do .NET, não precisará instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="d7da9-167">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="d7da9-168">Primeiro, Baixe uma versão **binária** para o SDK ou o tempo de execução de um dos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="d7da9-168">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="d7da9-169">downloads do ✔️ [.net 5,0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="d7da9-169">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="d7da9-170">downloads do ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="d7da9-170">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="d7da9-171">downloads do ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="d7da9-171">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="d7da9-172">Todos os downloads do .NET Core</span><span class="sxs-lookup"><span data-stu-id="d7da9-172">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="d7da9-173">Em seguida, extraia o arquivo baixado e use o `export` comando para definir as variáveis usadas pelo .net e, em seguida, verifique se o .net está no caminho.</span><span class="sxs-lookup"><span data-stu-id="d7da9-173">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="d7da9-174">Para extrair o tempo de execução e tornar os comandos da CLI do .NET disponíveis no terminal, primeiro Baixe uma versão binária do .NET.</span><span class="sxs-lookup"><span data-stu-id="d7da9-174">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="d7da9-175">Em seguida, abra um terminal e execute os seguintes comandos no diretório em que o arquivo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="d7da9-175">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="d7da9-176">O nome do arquivo morto pode ser diferente dependendo do que você baixou.</span><span class="sxs-lookup"><span data-stu-id="d7da9-176">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="d7da9-177">**Use o seguinte comando para extrair o tempo de execução**:</span><span class="sxs-lookup"><span data-stu-id="d7da9-177">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="d7da9-178">**Use o seguinte comando para extrair o SDK**:</span><span class="sxs-lookup"><span data-stu-id="d7da9-178">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="d7da9-179">Os `export` comandos anteriores tornam os comandos da CLI do .net disponíveis para a sessão de terminal na qual ele foi executado.</span><span class="sxs-lookup"><span data-stu-id="d7da9-179">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="d7da9-180">Você pode editar seu perfil de Shell para adicionar os comandos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="d7da9-180">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="d7da9-181">Há vários shells diferentes disponíveis para o Linux e cada um deles tem um perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="d7da9-181">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="d7da9-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d7da9-182">For example:</span></span>
>
> - <span data-ttu-id="d7da9-183">**Shell bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="d7da9-183">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="d7da9-184">**Shell Korn**: *~/.Kshrc* ou *. Profile*</span><span class="sxs-lookup"><span data-stu-id="d7da9-184">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="d7da9-185">**Shell Z**: *~/.zshrc* ou *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="d7da9-185">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="d7da9-186">Edite o arquivo de origem apropriado para o Shell e adicione `:$HOME/dotnet` ao final da `PATH` instrução existente.</span><span class="sxs-lookup"><span data-stu-id="d7da9-186">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="d7da9-187">Se nenhuma `PATH` instrução for incluída, adicione uma nova linha com `export PATH=$PATH:$HOME/dotnet` .</span><span class="sxs-lookup"><span data-stu-id="d7da9-187">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="d7da9-188">Além disso, adicione `export DOTNET_ROOT=$HOME/dotnet` ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d7da9-188">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="d7da9-189">Essa abordagem permite que você instale versões diferentes em locais separados e escolha explicitamente qual deles usar por qual aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d7da9-189">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7da9-190">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d7da9-190">Next steps</span></span>

- [<span data-ttu-id="d7da9-191">Como habilitar o preenchimento com TAB para a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="d7da9-191">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="d7da9-192">Tutorial: criar um aplicativo de console com o SDK do .NET usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d7da9-192">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
