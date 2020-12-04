---
title: Depurar aplicativos .NET no Raspberry Pi
description: Saiba como depurar aplicativos .NET no Raspberry Pi e dispositivos semelhantes.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 7b9872304ee53071452772e3da02081a7def4d80
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96585602"
---
# <a name="debug-net-apps-on-raspberry-pi"></a><span data-ttu-id="49c13-103">Depurar aplicativos .NET no Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="49c13-103">Debug .NET apps on Raspberry Pi</span></span>

<span data-ttu-id="49c13-104">A depuração de aplicativos .NET executados em dispositivos IoT baseados em ARM como o Raspberry Pi apresenta um desafio exclusivo.</span><span class="sxs-lookup"><span data-stu-id="49c13-104">Debugging .NET apps running on ARM-based IoT devices like Raspberry Pi presents a unique challenge.</span></span> <span data-ttu-id="49c13-105">É possível desenvolver aplicativos .NET em dispositivos ARM.</span><span class="sxs-lookup"><span data-stu-id="49c13-105">It is possible to develop .NET apps on ARM devices.</span></span> <span data-ttu-id="49c13-106">No entanto, OmniSharp, que é necessário para depurar aplicativos .NET fora do Visual Studio, não é compatível com dispositivos ARM.</span><span class="sxs-lookup"><span data-stu-id="49c13-106">However, OmniSharp, which is required for debugging .NET apps outside of Visual Studio, is not compatible with ARM devices.</span></span> <span data-ttu-id="49c13-107">Como resultado, os aplicativos devem ser depurados remotamente de uma plataforma compatível.</span><span class="sxs-lookup"><span data-stu-id="49c13-107">As a result, apps must be debugged remotely from a compatible platform.</span></span>

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a><span data-ttu-id="49c13-108">Depurar de Visual Studio Code (plataforma cruzada)</span><span class="sxs-lookup"><span data-stu-id="49c13-108">Debug from Visual Studio Code (cross-platform)</span></span>

<span data-ttu-id="49c13-109">A depuração do .NET no Raspberry Pi de Visual Studio Code requer etapas de configuração no Raspberry Pi e nalaunch.jsdo projeto *no* arquivo.</span><span class="sxs-lookup"><span data-stu-id="49c13-109">Debugging .NET on Raspberry Pi from Visual Studio Code requires configuration steps on the Raspberry Pi and in the project's *launch.json* file.</span></span>

### <a name="enable-ssh-on-the-raspberry-pi"></a><span data-ttu-id="49c13-110">Habilitar o SSH no Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="49c13-110">Enable SSH on the Raspberry Pi</span></span>

<span data-ttu-id="49c13-111">O SSH é necessário para a depuração remota.</span><span class="sxs-lookup"><span data-stu-id="49c13-111">SSH is required for remote debugging.</span></span> <span data-ttu-id="49c13-112">Para habilitar o SSH, [consulte *habilitar o ssh* na documentação do Raspberry Pi](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="49c13-112">To enable SSH, [refer to *Enable SSH* in the Raspberry Pi documentation](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a><span data-ttu-id="49c13-113">Instalar o Depurador Remoto do Visual Studio no Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="49c13-113">Install the Visual Studio Remote Debugger on the Raspberry Pi</span></span>

<span data-ttu-id="49c13-114">Em um console bash no Raspberry Pi (localmente ou via SSH), conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="49c13-114">Within a Bash console on the Raspberry Pi (either locally or via SSH), complete the following steps:</span></span>

1. <span data-ttu-id="49c13-115">Execute o comando a seguir para baixar e instalar o Depurador Remoto do Visual Studio no Raspberry Pi:</span><span class="sxs-lookup"><span data-stu-id="49c13-115">Execute the following command to download and install the Visual Studio Remote Debugger on the Raspberry Pi:</span></span>

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. <span data-ttu-id="49c13-116">O depurador requer a execução de as `root` .</span><span class="sxs-lookup"><span data-stu-id="49c13-116">The debugger requires running as `root`.</span></span> <span data-ttu-id="49c13-117">Por padrão, o `root` não tem senha no Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="49c13-117">By default, `root` has no password on Raspberry Pi.</span></span> <span data-ttu-id="49c13-118">Defina uma senha para `root` executando o comando a seguir e seguindo os prompts.</span><span class="sxs-lookup"><span data-stu-id="49c13-118">Set a password for `root` by executing the following command and following the prompts.</span></span>

    ```bash
    sudo passwd root
    ```

1. <span data-ttu-id="49c13-119">Visual Studio Code usa o protocolo SSH para depurar remotamente.</span><span class="sxs-lookup"><span data-stu-id="49c13-119">Visual Studio Code uses the SSH protocol to debug remotely.</span></span> <span data-ttu-id="49c13-120">Para fins de segurança, o `root` não tem permissão para fazer logon via SSH por padrão.</span><span class="sxs-lookup"><span data-stu-id="49c13-120">For security purposes, `root` is not permitted to log on via SSH by default.</span></span> <span data-ttu-id="49c13-121">Para habilitar `root` o logon via SSH, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="49c13-121">To enable `root` to log on via SSH, complete the following steps:</span></span>

    1. <span data-ttu-id="49c13-122">Execute o seguinte comando para abrir */etc/ssh/sshd_config* no [nano](https://www.nano-editor.org/docs.php) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="49c13-122">Execute the following command to open */etc/ssh/sshd_config* in [nano](https://www.nano-editor.org/docs.php) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. <span data-ttu-id="49c13-123">Pressione <kbd>Ctrl + W</kbd> e procure por **PermitRootLogin**.</span><span class="sxs-lookup"><span data-stu-id="49c13-123">Press <kbd>Ctrl+W</kbd> and search for **PermitRootLogin**.</span></span>
    1. <span data-ttu-id="49c13-124">Remova a marca de comentário da linha com **PermitRootLogin** , se necessário.</span><span class="sxs-lookup"><span data-stu-id="49c13-124">Uncomment the line with **PermitRootLogin** if needed.</span></span>
    1. <span data-ttu-id="49c13-125">Altere a linha para ler da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="49c13-125">Change the line to read as follows:</span></span>

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > <span data-ttu-id="49c13-126">Se não houver nenhuma linha **PermitRootLogin** no */etc/ssh/sshd_config*, adicione uma nova linha com o valor mostrado acima.</span><span class="sxs-lookup"><span data-stu-id="49c13-126">If there is no **PermitRootLogin** line in */etc/ssh/sshd_config*, add a new line with the value shown above.</span></span>

    1. <span data-ttu-id="49c13-127">Pressione <kbd>Ctrl + X</kbd> para sair e salvar suas chances.</span><span class="sxs-lookup"><span data-stu-id="49c13-127">Press <kbd>Ctrl+X</kbd> to exit and save your chances.</span></span> <span data-ttu-id="49c13-128">Quando solicitado, **salve o buffer modificado?**, pressione <kbd>Y</kbd> para confirmar.</span><span class="sxs-lookup"><span data-stu-id="49c13-128">When prompted **Save modified buffer?**, press <kbd>Y</kbd> to confirm.</span></span> <span data-ttu-id="49c13-129">Pressione <kbd>Enter</kbd> para confirmar a substituição do arquivo original.</span><span class="sxs-lookup"><span data-stu-id="49c13-129">Press <kbd>Enter</kbd> to confirm overwriting the original file.</span></span>
    1. <span data-ttu-id="49c13-130">Reinicialize o Raspberry Pi executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="49c13-130">Reboot the Raspberry Pi by executing the following command:</span></span>

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a><span data-ttu-id="49c13-131">launch.jsde instalação no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49c13-131">Setup launch.json in Visual Studio Code</span></span>

<span data-ttu-id="49c13-132">Adicione uma configuração de inicialização àlaunch.jsdo projeto *em*.</span><span class="sxs-lookup"><span data-stu-id="49c13-132">Add a launch configuration to the project's *launch.json*.</span></span> <span data-ttu-id="49c13-133">Se o projeto não tiver um *launch.jsno* arquivo, adicione um, alternando para a guia **executar** , selecionando **criar um launch.jsno arquivo** e selecionando **.net** ou **.NET Core** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="49c13-133">If the project doesn't have a *launch.json* file, add one by switching to the **Run** tab, selecting **create a launch.json file**, and selecting **.NET** or **.NET Core** in the dialog.</span></span>

<span data-ttu-id="49c13-134">A nova configuração no *launch.jsem* deve ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="49c13-134">The new configuration in *launch.json* should look similar to this:</span></span>

```json
"configurations": [
    {
        "name": ".NET Core Launch (remote console)",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "/home/pi/.dotnet/dotnet",
        "args": ["/home/pi/sample/Sample.dll"],
        "cwd": "/home/pi/sample",
        "stopAtEntry": false,
        "console": "internalConsole",
        "pipeTransport": {
            "pipeCwd": "${workspaceFolder}",
            "pipeProgram": "C:\\Program Files\\PuTTY\\PLINK.EXE",
            "pipeArgs": [
                "-pw",
                "P@ssw0rd",
                "root@raspberrypi"
            ],
            "debuggerPath": "/home/pi/vsdbg/vsdbg"
        }
    },
```

<span data-ttu-id="49c13-135">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="49c13-135">Notice the following:</span></span>

- <span data-ttu-id="49c13-136">`program` é o caminho para o tempo de execução do .NET no PI.</span><span class="sxs-lookup"><span data-stu-id="49c13-136">`program` is the path to the .NET runtime on the Pi.</span></span>
- <span data-ttu-id="49c13-137">`args` é o caminho para o assembly a ser depurado no PI.</span><span class="sxs-lookup"><span data-stu-id="49c13-137">`args` is the path to the assembly to debug on the Pi.</span></span>
- <span data-ttu-id="49c13-138">`cwd` é o diretório de trabalho a ser usado ao iniciar o aplicativo no PI.</span><span class="sxs-lookup"><span data-stu-id="49c13-138">`cwd` is the working directory to use when launching the app on the Pi.</span></span>
- <span data-ttu-id="49c13-139">`pipeProgram` é o caminho para um cliente SSH no computador local.</span><span class="sxs-lookup"><span data-stu-id="49c13-139">`pipeProgram` is the path to an SSH client on the local machine.</span></span>
- <span data-ttu-id="49c13-140">`pipeArgs` são os parâmetros a serem passados para o cliente SSH.</span><span class="sxs-lookup"><span data-stu-id="49c13-140">`pipeArgs` are the parameters to be passed to the SSH client.</span></span> <span data-ttu-id="49c13-141">Certifique-se de especificar o parâmetro de senha, bem como o `root` usuário no formato `<user>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="49c13-141">Be sure to specify the password parameter, as well as the `root` user in the format `<user>@<hostname>`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49c13-142">O exemplo acima usa *plink*, um componente do cliente SSH [de saída](https://www.ssh.com/ssh/putty/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="49c13-142">The above example uses *plink*, a component of the [PuTTY](https://www.ssh.com/ssh/putty/)<span class="docon docon-navigate-external x-hidden-focus"></span> SSH client.</span></span> <span data-ttu-id="49c13-143">O [OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> , que está incluído nas versões recentes do Windows e do Linux, pode ser usado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="49c13-143">[OpenSSH](https://www.openssh.com/)<span class="docon docon-navigate-external x-hidden-focus"></span>, which is included in recent versions of Windows and Linux, may be used instead.</span></span> <span data-ttu-id="49c13-144">No entanto, o OpenSSH não dá suporte ao envio de senhas como um parâmetro de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="49c13-144">However, OpenSSH doesn't support sending passwords as a command-line parameter.</span></span> <span data-ttu-id="49c13-145">Para usar o OpenSSH, [configure seu Raspberry Pi para acesso de SSH com senha](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="49c13-145">To use OpenSSH, [configure your Raspberry Pi for passwordless SSH access](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

### <a name="deploy-the-app"></a><span data-ttu-id="49c13-146">Implantar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="49c13-146">Deploy the app</span></span>

<span data-ttu-id="49c13-147">Implante o aplicativo conforme descrito em [implantar aplicativos .net no Raspberry Pi](deployment.md).</span><span class="sxs-lookup"><span data-stu-id="49c13-147">Deploy the app as described in [Deploy .NET apps to Raspberry Pi](deployment.md).</span></span> <span data-ttu-id="49c13-148">Verifique se o caminho de implantação é o mesmo caminho especificado no `cwd` parâmetro no *launch.jsna* configuração.</span><span class="sxs-lookup"><span data-stu-id="49c13-148">Ensure the deployment path is the same path specified in the `cwd` parameter in the *launch.json* configuration.</span></span>

### <a name="launch-the-debugger"></a><span data-ttu-id="49c13-149">Iniciar o depurador</span><span class="sxs-lookup"><span data-stu-id="49c13-149">Launch the debugger</span></span>

<span data-ttu-id="49c13-150">Na guia **executar** , selecione a configuração **inicialização do .NET Core (console remoto)** e selecione **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="49c13-150">On the **Run** tab, select the **.NET Core Launch (remote console)** configuration and select **Start Debugging**.</span></span> <span data-ttu-id="49c13-151">O aplicativo é iniciado no Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="49c13-151">The app launches on the Raspberry Pi.</span></span> <span data-ttu-id="49c13-152">O depurador pode ser usado para definir pontos de interrupção, inspecionar locais e muito mais.</span><span class="sxs-lookup"><span data-stu-id="49c13-152">The debugger may be used to set breakpoints, inspect locals, and more.</span></span>

## <a name="references"></a><span data-ttu-id="49c13-153">Referências</span><span class="sxs-lookup"><span data-stu-id="49c13-153">References</span></span>

<span data-ttu-id="49c13-154">[Depuração remota com vs Code no Windows para um Raspberry Pi usando o .NET Core no ARM](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="49c13-154">[Remote debugging with VS Code on Windows to a Raspberry Pi using .NET Core on ARM](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a><span data-ttu-id="49c13-155">Depurar do Visual Studio no Windows</span><span class="sxs-lookup"><span data-stu-id="49c13-155">Debug from Visual Studio on Windows</span></span>

<span data-ttu-id="49c13-156">O Visual Studio pode depurar aplicativos .NET em dispositivos remotos via SSH.</span><span class="sxs-lookup"><span data-stu-id="49c13-156">Visual Studio can debug .NET apps on remote devices via SSH.</span></span> <span data-ttu-id="49c13-157">Nenhuma configuração especializada é necessária no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49c13-157">No specialized configuration is required on the device.</span></span> <span data-ttu-id="49c13-158">Para obter detalhes sobre como usar o Visual Studio para depurar o .NET remotamente, consulte [depuração remota do .net no Linux usando SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="49c13-158">For details on using Visual Studio to debug .NET remotely, see [Remote debug .NET on Linux using SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span></span>

::: zone-end
