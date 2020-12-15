---
title: 'Tutorial: instalar e usar as ferramentas locais do .NET'
description: Saiba como instalar e usar uma ferramenta .NET como uma ferramenta local.
ms.topic: tutorial
ms.date: 12/11/2020
ms.openlocfilehash: f32a5c4091ff63c7c50cf339dddd89b78e543c4c
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512457"
---
# <a name="tutorial-install-and-use-a-net-local-tool-using-the-net-cli"></a><span data-ttu-id="9432b-103">Tutorial: instalar e usar uma ferramenta local do .NET usando a CLI do .NET</span><span class="sxs-lookup"><span data-stu-id="9432b-103">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>

<span data-ttu-id="9432b-104">**Este artigo aplica-se a:** ✔️ SDK do .net Core 3,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="9432b-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="9432b-105">Este tutorial ensina como instalar e usar uma ferramenta local.</span><span class="sxs-lookup"><span data-stu-id="9432b-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="9432b-106">Você usa uma ferramenta que você cria no [primeiro tutorial desta série](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="9432b-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9432b-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9432b-107">Prerequisites</span></span>

* <span data-ttu-id="9432b-108">Conclua o [primeiro tutorial desta série](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="9432b-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="9432b-109">Instale o tempo de execução do .NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="9432b-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="9432b-110">Para este tutorial, você instala e usa uma ferramenta que tem como alvo o .NET Core 2,1, portanto, você precisa ter esse tempo de execução instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="9432b-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="9432b-111">Para instalar o tempo de execução 2,1, vá para a [página de download do .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1) e localize o link de instalação de tempo de execução na coluna **executar aplicativos-tempo de execução** .</span><span class="sxs-lookup"><span data-stu-id="9432b-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="9432b-112">Criar um arquivo de manifesto</span><span class="sxs-lookup"><span data-stu-id="9432b-112">Create a manifest file</span></span>

<span data-ttu-id="9432b-113">Para instalar uma ferramenta somente para acesso local (para o diretório e subdiretórios atuais), ela deve ser adicionada a um arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="9432b-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span>

<span data-ttu-id="9432b-114">Na pasta *Microsoft. botsay* , navegue até um nível para a pasta do *repositório* :</span><span class="sxs-lookup"><span data-stu-id="9432b-114">From the *microsoft.botsay* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="9432b-115">Crie um arquivo de manifesto executando o comando [dotnet novo](dotnet-new.md) :</span><span class="sxs-lookup"><span data-stu-id="9432b-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="9432b-116">A saída indica a criação bem-sucedida do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9432b-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="9432b-117">O *. config/dotnet-tools.jsno* arquivo ainda não tem ferramentas:</span><span class="sxs-lookup"><span data-stu-id="9432b-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="9432b-118">As ferramentas listadas em um arquivo de manifesto estão disponíveis para o diretório e os subdiretórios atuais.</span><span class="sxs-lookup"><span data-stu-id="9432b-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="9432b-119">O diretório atual é aquele que contém o diretório *. config* com o arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="9432b-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="9432b-120">Quando você usa um comando da CLI que se refere a uma ferramenta local, o SDK pesquisa um arquivo de manifesto no diretório atual e nos diretórios pai.</span><span class="sxs-lookup"><span data-stu-id="9432b-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="9432b-121">Se encontrar um arquivo de manifesto, mas o arquivo não incluir a ferramenta referenciada, ele continuará a pesquisa por meio de diretórios pai.</span><span class="sxs-lookup"><span data-stu-id="9432b-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="9432b-122">A pesquisa termina quando encontra a ferramenta referenciada ou encontra um arquivo de manifesto com `isRoot` definido como `true` .</span><span class="sxs-lookup"><span data-stu-id="9432b-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="9432b-123">Instalar o botsay como uma ferramenta local</span><span class="sxs-lookup"><span data-stu-id="9432b-123">Install botsay as a local tool</span></span>

<span data-ttu-id="9432b-124">Instale a ferramenta do pacote que você criou no primeiro tutorial:</span><span class="sxs-lookup"><span data-stu-id="9432b-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

<span data-ttu-id="9432b-125">Esse comando adiciona a ferramenta ao arquivo de manifesto que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="9432b-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="9432b-126">A saída do comando mostra qual arquivo de manifesto está em sua ferramenta recém-instalada:</span><span class="sxs-lookup"><span data-stu-id="9432b-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="9432b-127">O *. config/dotnet-tools.jsno* arquivo agora tem uma ferramenta:</span><span class="sxs-lookup"><span data-stu-id="9432b-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="9432b-128">Usar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="9432b-128">Use the tool</span></span>

<span data-ttu-id="9432b-129">Invoque a ferramenta executando o `dotnet tool run` comando da pasta do *repositório* :</span><span class="sxs-lookup"><span data-stu-id="9432b-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="9432b-130">Restaurar uma ferramenta local instalada por outras pessoas</span><span class="sxs-lookup"><span data-stu-id="9432b-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="9432b-131">Normalmente, você instala uma ferramenta local no diretório raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="9432b-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="9432b-132">Depois de fazer o check-in do arquivo de manifesto para o repositório, outros desenvolvedores poderão obter o arquivo de manifesto mais recente.</span><span class="sxs-lookup"><span data-stu-id="9432b-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="9432b-133">Para instalar todas as ferramentas listadas no arquivo de manifesto, elas podem executar um único `dotnet tool restore` comando.</span><span class="sxs-lookup"><span data-stu-id="9432b-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="9432b-134">Abra o arquivo *. config/dotnet-tools.js* e substitua o conteúdo pelo JSON a seguir:</span><span class="sxs-lookup"><span data-stu-id="9432b-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="9432b-135">Substitua `<name>` pelo nome usado para criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="9432b-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="9432b-136">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9432b-136">Save your changes.</span></span>

   <span data-ttu-id="9432b-137">Fazer essa alteração é o mesmo que obter a versão mais recente do repositório depois que outra pessoa instalou o pacote `dotnetsay` para o diretório do projeto.</span><span class="sxs-lookup"><span data-stu-id="9432b-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span>

1. <span data-ttu-id="9432b-138">Execute o comando `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="9432b-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="9432b-139">O comando produz uma saída semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9432b-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="9432b-140">Verifique se as ferramentas estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9432b-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="9432b-141">A saída é uma lista de pacotes e comandos, semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="9432b-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="9432b-142">Teste as ferramentas:</span><span class="sxs-lookup"><span data-stu-id="9432b-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="9432b-143">Atualizar uma ferramenta local</span><span class="sxs-lookup"><span data-stu-id="9432b-143">Update a local tool</span></span>

<span data-ttu-id="9432b-144">A versão instalada da ferramenta local `dotnetsay` é 2.1.3.</span><span class="sxs-lookup"><span data-stu-id="9432b-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="9432b-145">Use o comando [dotnet ferramenta de atualização](dotnet-tool-update.md) para atualizar a ferramenta para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="9432b-145">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="9432b-146">A saída indica o novo número de versão:</span><span class="sxs-lookup"><span data-stu-id="9432b-146">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.7'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="9432b-147">O comando Update localiza o primeiro arquivo de manifesto que contém a ID do pacote e o atualiza.</span><span class="sxs-lookup"><span data-stu-id="9432b-147">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="9432b-148">Se não houver nenhuma ID de pacote em nenhum arquivo de manifesto que esteja no escopo da pesquisa, o SDK adicionará uma nova entrada ao arquivo de manifesto mais próximo.</span><span class="sxs-lookup"><span data-stu-id="9432b-148">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="9432b-149">O escopo da pesquisa é feito por meio de diretórios pai até que um arquivo de manifesto com `isRoot = true` seja encontrado.</span><span class="sxs-lookup"><span data-stu-id="9432b-149">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="9432b-150">Remover ferramentas locais</span><span class="sxs-lookup"><span data-stu-id="9432b-150">Remove local tools</span></span>

<span data-ttu-id="9432b-151">Remova as ferramentas instaladas executando o comando [dotnet ferramenta de desinstalação](dotnet-tool-uninstall.md) :</span><span class="sxs-lookup"><span data-stu-id="9432b-151">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="9432b-152">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="9432b-152">Troubleshoot</span></span>

<span data-ttu-id="9432b-153">Se você receber uma mensagem de erro ao seguir o tutorial, consulte [solucionar problemas de uso da ferramenta .net](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9432b-153">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9432b-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9432b-154">See also</span></span>

<span data-ttu-id="9432b-155">Para obter mais informações, consulte [ferramentas .net](global-tools.md)</span><span class="sxs-lookup"><span data-stu-id="9432b-155">For more information, see [.NET tools](global-tools.md)</span></span>
