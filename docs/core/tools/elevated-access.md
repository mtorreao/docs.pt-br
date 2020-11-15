---
title: Acesso elevado para os comandos dotnet
description: Conheça as melhores práticas para os comandos dotnet que exigem acesso elevado.
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: b34a4d631ec0e5ef641e1ffbc91e081d25645157
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634045"
---
# <a name="elevated-access-for-dotnet-commands"></a><span data-ttu-id="03090-103">Acesso elevado para os comandos dotnet</span><span class="sxs-lookup"><span data-stu-id="03090-103">Elevated access for dotnet commands</span></span>

<span data-ttu-id="03090-104">As melhores práticas de desenvolvimento de software orientam os desenvolvedores a escrever um software que exija o mínimo de privilégios.</span><span class="sxs-lookup"><span data-stu-id="03090-104">Software development best practices guide developers to writing software that requires the least amount of privilege.</span></span> <span data-ttu-id="03090-105">No entanto, alguns softwares, como as ferramentas de monitoramento de desempenho, requerem permissão de administrador devido a regras do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="03090-105">However, some software, like performance monitoring tools, requires admin permission because of operating system rules.</span></span> <span data-ttu-id="03090-106">As diretrizes a seguir descrevem os cenários compatíveis com a gravação desse software com o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="03090-106">The following guidance describes supported scenarios for writing such software with .NET Core.</span></span>

<span data-ttu-id="03090-107">Os seguintes comandos podem ser executados com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="03090-107">The following commands can be run elevated:</span></span>

- <span data-ttu-id="03090-108">comandos `dotnet tool`, como [instalação de ferramenta dotnet](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="03090-108">`dotnet tool` commands, such as [dotnet tool install](dotnet-tool-install.md).</span></span>
- `dotnet run --no-build`
- `dotnet-core-uninstall`

<span data-ttu-id="03090-109">Não recomendamos executar outros comandos com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="03090-109">We don't recommend running other commands elevated.</span></span> <span data-ttu-id="03090-110">Particularmente, não recomendamos privilégios elevados com comandos que usam o MSBuild, como [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md) e [dotnet run](dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="03090-110">In particular, we don't recommend elevation with commands that use MSBuild, such as [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md), and [dotnet run](dotnet-run.md).</span></span> <span data-ttu-id="03090-111">O principal problema é o gerenciamento de permissões quando um usuário faz a transição entre a raiz e uma conta restrita várias vezes após a emissão de comandos dotnet.</span><span class="sxs-lookup"><span data-stu-id="03090-111">The primary issue is permission management problems when a user transitions back and forth between root and a restricted account after issuing dotnet commands.</span></span> <span data-ttu-id="03090-112">Você pode achar, como um usuário restrito, que não tem acesso ao arquivo criado por um usuário raiz.</span><span class="sxs-lookup"><span data-stu-id="03090-112">You may find as a restricted user that you don't have access to the file built by a root user.</span></span> <span data-ttu-id="03090-113">Existem maneiras de resolver esta situação, mas não é necessário entrar nesse assunto agora.</span><span class="sxs-lookup"><span data-stu-id="03090-113">There are ways to resolve this situation, but they're unnecessary to get into in the first place.</span></span>

<span data-ttu-id="03090-114">Você pode executar comandos como raiz, desde que não faça a transição entre a raiz e uma conta restrita.</span><span class="sxs-lookup"><span data-stu-id="03090-114">You can run commands as root as long as you don't transition back and forth between root and a restricted account.</span></span> <span data-ttu-id="03090-115">Por exemplo, os contêineres do Docker são executados como raiz por padrão, então eles têm essa característica.</span><span class="sxs-lookup"><span data-stu-id="03090-115">For example, Docker containers run as root by default, so they have this characteristic.</span></span>

## <a name="global-tool-installation"></a><span data-ttu-id="03090-116">Instalação da ferramenta global</span><span class="sxs-lookup"><span data-stu-id="03090-116">Global tool installation</span></span>

<span data-ttu-id="03090-117">As instruções a seguir demonstram a maneira recomendada de instalar, executar e desinstalar as ferramentas .NET que exigem permissões elevadas para serem executadas.</span><span class="sxs-lookup"><span data-stu-id="03090-117">The following instructions demonstrate the recommended way to install, run, and uninstall .NET tools that require elevated permissions to execute.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="03090-118">Windows</span><span class="sxs-lookup"><span data-stu-id="03090-118">Windows</span></span>](#tab/windows)

### <a name="install-the-tool"></a><span data-ttu-id="03090-119">Instalar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="03090-119">Install the tool</span></span>

<span data-ttu-id="03090-120">Se a pasta `%ProgramFiles%\dotnet-tools` já existir, faça o seguinte para verificar se o grupo “Usuários” tem permissão para gravar ou modificar esse diretório:</span><span class="sxs-lookup"><span data-stu-id="03090-120">If the folder `%ProgramFiles%\dotnet-tools` already exists, do the following to check whether the "Users" group has permission to write or modify that directory:</span></span>

- <span data-ttu-id="03090-121">Clique com o botão direito do mouse na `%ProgramFiles%\dotnet-tools` pasta e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="03090-121">Right-click the `%ProgramFiles%\dotnet-tools` folder and select **Properties**.</span></span> <span data-ttu-id="03090-122">A caixa de diálogo **Propriedades Comuns** é aberta.</span><span class="sxs-lookup"><span data-stu-id="03090-122">The **Common Properties** dialog box opens.</span></span>
- <span data-ttu-id="03090-123">Selecione a guia **segurança** . Em **nomes de grupo ou de usuário** , verifique se o grupo "usuários" tem permissão para gravar ou modificar o diretório.</span><span class="sxs-lookup"><span data-stu-id="03090-123">Select the **Security** tab. Under **Group or user names** , check whether the "Users" group has permission to write or modify the directory.</span></span>
- <span data-ttu-id="03090-124">Se o grupo “Usuários” puder gravar ou modificar o diretório, use um nome de diretório diferente ao instalar as ferramentas em vez de *dotnet-tools*.</span><span class="sxs-lookup"><span data-stu-id="03090-124">If the "Users" group can write or modify the directory, use a different directory name when installing the tools rather than *dotnet-tools*.</span></span>

<span data-ttu-id="03090-125">Para instalar as ferramentas, execute o seguinte comando no prompt com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="03090-125">To install tools, run the following command in elevated prompt.</span></span> <span data-ttu-id="03090-126">Ele criará a pasta *dotnet-tools* durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="03090-126">It will create the *dotnet-tools* folder during the installation.</span></span>

```dotnetcli
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a><span data-ttu-id="03090-127">Executar a ferramenta global</span><span class="sxs-lookup"><span data-stu-id="03090-127">Run the global tool</span></span>

<span data-ttu-id="03090-128">**Opção 1** Usar o caminho completo com prompt com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="03090-128">**Option 1** Use the full path with elevated prompt:</span></span>

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

<span data-ttu-id="03090-129">**Opção 2** Adicionar a pasta recém-criada ao `%Path%`.</span><span class="sxs-lookup"><span data-stu-id="03090-129">**Option 2** Add the newly created folder to `%Path%`.</span></span> <span data-ttu-id="03090-130">Você só precisa fazer essa operação uma vez.</span><span class="sxs-lookup"><span data-stu-id="03090-130">You only need to do this operation once.</span></span>

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

<span data-ttu-id="03090-131">E execute com:</span><span class="sxs-lookup"><span data-stu-id="03090-131">And run with:</span></span>

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="03090-132">Desinstalar a ferramenta global</span><span class="sxs-lookup"><span data-stu-id="03090-132">Uninstall the global tool</span></span>

<span data-ttu-id="03090-133">No prompt de privilégios elevados, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="03090-133">In an elevated prompt, type the following command:</span></span>

```dotnetcli
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linux"></a>[<span data-ttu-id="03090-134">Linux</span><span class="sxs-lookup"><span data-stu-id="03090-134">Linux</span></span>](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macos"></a>[<span data-ttu-id="03090-135">macOS</span><span class="sxs-lookup"><span data-stu-id="03090-135">macOS</span></span>](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a><span data-ttu-id="03090-136">Ferramentas locais</span><span class="sxs-lookup"><span data-stu-id="03090-136">Local tools</span></span>

<span data-ttu-id="03090-137">As ferramentas locais têm escopo por árvore de subdiretório, por usuário.</span><span class="sxs-lookup"><span data-stu-id="03090-137">Local tools are scoped per subdirectory tree, per user.</span></span> <span data-ttu-id="03090-138">Quando executadas com privilégios elevados, as ferramentas locais compartilham um ambiente de usuário restrito com o ambiente com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="03090-138">When run elevated, local tools share a restricted user environment to the elevated environment.</span></span> <span data-ttu-id="03090-139">No Linux e no macOS, isso resulta em arquivos sendo definidos com acesso somente para o usuário raiz.</span><span class="sxs-lookup"><span data-stu-id="03090-139">In Linux and macOS, this results in files being set with root user-only access.</span></span> <span data-ttu-id="03090-140">Se o usuário voltar para uma conta restrita, ele não poderá acessar ou gravar arquivos.</span><span class="sxs-lookup"><span data-stu-id="03090-140">If the user switches back to a restricted account, the user can no longer access or write to the files.</span></span> <span data-ttu-id="03090-141">Então, não é recomendado instalar as ferramentas que exigem elevação como ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="03090-141">So installing tools that require elevation as local tools isn't recommended.</span></span> <span data-ttu-id="03090-142">Em vez disso, use a opção `--tool-path` e as diretrizes anteriores de ferramentas globais.</span><span class="sxs-lookup"><span data-stu-id="03090-142">Instead, use the `--tool-path` option and the previous guidelines for global tools.</span></span>

## <a name="elevation-during-development"></a><span data-ttu-id="03090-143">Elevação durante o desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="03090-143">Elevation during development</span></span>

<span data-ttu-id="03090-144">Durante o desenvolvimento, talvez você precise de acesso com privilégios elevados para testar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="03090-144">During development, you may need elevated access to test your application.</span></span> <span data-ttu-id="03090-145">Esse cenário é comum para aplicativos de IoT, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="03090-145">This scenario is common for IoT apps, for example.</span></span> <span data-ttu-id="03090-146">É recomendável que você compile o aplicativo sem elevação e, em seguida, execute-o com elevação.</span><span class="sxs-lookup"><span data-stu-id="03090-146">We recommend that you build the application without elevation and then run it with elevation.</span></span> <span data-ttu-id="03090-147">Há alguns padrões, como abaixo:</span><span class="sxs-lookup"><span data-stu-id="03090-147">There are a few patterns, as follows:</span></span>

- <span data-ttu-id="03090-148">Usando o executável gerado (fornece o melhor desempenho de inicialização):</span><span class="sxs-lookup"><span data-stu-id="03090-148">Using generated executable (it provides the best startup performance):</span></span>

   ```dotnetcli
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```

- <span data-ttu-id="03090-149">O uso do comando [dotnet run](dotnet-run.md) com o `—no-build` sinalizador para evitar a geração de novos binários:</span><span class="sxs-lookup"><span data-stu-id="03090-149">Using the [dotnet run](dotnet-run.md) command with the `—no-build` flag to avoid generating new binaries:</span></span>

   ```dotnetcli
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a><span data-ttu-id="03090-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="03090-150">See also</span></span>

- [<span data-ttu-id="03090-151">Visão geral das ferramentas .NET</span><span class="sxs-lookup"><span data-stu-id="03090-151">.NET tools overview</span></span>](global-tools.md)
