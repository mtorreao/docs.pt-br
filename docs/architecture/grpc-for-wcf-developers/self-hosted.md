---
title: Aplicativos gRPC de hospedagem interna – gRPC para desenvolvedores do WCF
description: Implantando ASP.NET Core aplicativos gRPC como serviços hospedados internamente.
ms.date: 12/15/2020
ms.openlocfilehash: a5e2316b8d76593f4eb53760d2609b5bbbc9d2c5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938527"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="b8620-103">Aplicativos gRPC auto-hospedados</span><span class="sxs-lookup"><span data-stu-id="b8620-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="b8620-104">Embora ASP.NET Core aplicativos 5,0 possam ser hospedados no IIS no Windows Server, atualmente não é possível hospedar um aplicativo gRPC no IIS porque não há suporte para algumas das funcionalidades HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="b8620-104">Although ASP.NET Core 5.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="b8620-105">Essa funcionalidade é uma meta para uma atualização futura do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8620-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="b8620-106">Você pode executar seu aplicativo como um serviço do Windows.</span><span class="sxs-lookup"><span data-stu-id="b8620-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="b8620-107">Ou você pode executá-lo como um serviço do Linux controlado pelo [sistema](https://en.wikipedia.org/wiki/Systemd), devido aos novos recursos nas extensões de hospedagem do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="b8620-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET 5.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="b8620-108">Executar seu aplicativo como um serviço do Windows</span><span class="sxs-lookup"><span data-stu-id="b8620-108">Run your app as a Windows service</span></span>

<span data-ttu-id="b8620-109">Para configurar seu aplicativo ASP.NET Core para ser executado como um serviço do Windows, instale o pacote [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) do NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8620-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="b8620-110">Em seguida, adicione uma chamada para `UseWindowsService` para o `CreateHostBuilder` método em `Program.cs` .</span><span class="sxs-lookup"><span data-stu-id="b8620-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="b8620-111">Se o aplicativo não estiver sendo executado como um serviço do Windows, o `UseWindowsService` método não fará nada.</span><span class="sxs-lookup"><span data-stu-id="b8620-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="b8620-112">Agora, publique seu aplicativo usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="b8620-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="b8620-113">No Visual Studio, clicando com o botão direito do mouse no projeto e selecionando **publicar** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="b8620-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="b8620-114">Da CLI do .NET.</span><span class="sxs-lookup"><span data-stu-id="b8620-114">From the .NET CLI.</span></span>

<span data-ttu-id="b8620-115">Ao publicar um aplicativo .NET, você pode optar por criar uma implantação *dependente da estrutura* ou uma implantação *independente* .</span><span class="sxs-lookup"><span data-stu-id="b8620-115">When you publish a .NET application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="b8620-116">As implantações dependentes da estrutura exigem que o tempo de execução compartilhado do .NET seja instalado no host onde eles são executados.</span><span class="sxs-lookup"><span data-stu-id="b8620-116">Framework-dependent deployments require the .NET Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="b8620-117">As implantações independentes são publicadas com uma cópia completa do tempo de execução e da estrutura do .NET e podem ser executadas em qualquer host.</span><span class="sxs-lookup"><span data-stu-id="b8620-117">Self-contained deployments are published with a complete copy of the .NET runtime and framework and can be run on any host.</span></span> <span data-ttu-id="b8620-118">Para obter mais informações, incluindo as vantagens e desvantagens de cada abordagem, consulte a documentação de [implantação de aplicativos .net](../../core/deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="b8620-118">For more information, including the advantages and disadvantages of each approach, see the [.NET application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="b8620-119">Para publicar uma compilação independente do aplicativo que não exige que o tempo de execução do .NET 5,0 seja instalado no host, especifique o tempo de execução a ser incluído no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b8620-119">To publish a self-contained build of the application that does not require the .NET 5.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="b8620-120">Use o `-r` sinalizador (ou `--runtime` ).</span><span class="sxs-lookup"><span data-stu-id="b8620-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="b8620-121">Para publicar uma compilação dependente de estrutura, omita o `-r` sinalizador.</span><span class="sxs-lookup"><span data-stu-id="b8620-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="b8620-122">Copie todo o conteúdo do `publish` diretório para uma pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="b8620-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="b8620-123">Em seguida, use a [ferramenta SC](/windows/desktop/services/controlling-a-service-using-sc) para criar um serviço do Windows para o arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="b8620-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="b8620-124">Registrar no log de eventos do Windows</span><span class="sxs-lookup"><span data-stu-id="b8620-124">Log to the Windows event log</span></span>

<span data-ttu-id="b8620-125">O `UseWindowsService` método adiciona automaticamente um provedor de [log](/aspnet/core/fundamentals/logging/) que grava mensagens de log no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="b8620-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="b8620-126">Você pode configurar o log para esse provedor adicionando uma `EventLog` entrada à `Logging` seção de `appsettings.json` ou outra fonte de configuração.</span><span class="sxs-lookup"><span data-stu-id="b8620-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="b8620-127">Você pode substituir o nome de origem usado no log de eventos definindo uma `SourceName` Propriedade nessas configurações.</span><span class="sxs-lookup"><span data-stu-id="b8620-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="b8620-128">Se você não especificar um nome, o nome do aplicativo padrão (normalmente, o nome do assembly executável) será usado.</span><span class="sxs-lookup"><span data-stu-id="b8620-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="b8620-129">Mais informações sobre o registro em log estão no final deste capítulo.</span><span class="sxs-lookup"><span data-stu-id="b8620-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="b8620-130">Execute seu aplicativo como um serviço Linux com o sistema</span><span class="sxs-lookup"><span data-stu-id="b8620-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="b8620-131">Para configurar seu aplicativo ASP.NET Core para ser executado como um serviço do Linux (ou *daemon* na linguagem Linux), instale o pacote [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) do NuGet.</span><span class="sxs-lookup"><span data-stu-id="b8620-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="b8620-132">Em seguida, adicione uma chamada para `UseSystemd` para o `CreateHostBuilder` método em `Program.cs` .</span><span class="sxs-lookup"><span data-stu-id="b8620-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="b8620-133">Se o aplicativo não estiver sendo executado como um serviço do Linux, o `UseSystemd` método não fará nada.</span><span class="sxs-lookup"><span data-stu-id="b8620-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="b8620-134">Agora, publique seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b8620-134">Now publish your application.</span></span> <span data-ttu-id="b8620-135">O aplicativo pode ser dependente da estrutura ou independente para o tempo de execução do Linux relevante (por exemplo, `linux-x64` ).</span><span class="sxs-lookup"><span data-stu-id="b8620-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="b8620-136">Você pode publicar usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="b8620-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="b8620-137">No Visual Studio, clicando com o botão direito do mouse no projeto e selecionando **publicar** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="b8620-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="b8620-138">Na CLI do .NET, usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b8620-138">From the .NET CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="b8620-139">Copie todo o conteúdo do `publish` diretório para uma pasta de instalação no host do Linux.</span><span class="sxs-lookup"><span data-stu-id="b8620-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="b8620-140">O registro do serviço requer um arquivo especial, chamado *arquivo de unidade*, a ser adicionado ao `/etc/systemd/system` diretório.</span><span class="sxs-lookup"><span data-stu-id="b8620-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="b8620-141">Você precisará de permissão de raiz para criar um arquivo nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="b8620-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="b8620-142">Nomeie o arquivo com o identificador que você deseja `systemd` usar e a `.service` extensão.</span><span class="sxs-lookup"><span data-stu-id="b8620-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="b8620-143">Por exemplo, use `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="b8620-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="b8620-144">O arquivo de serviço usa o formato INI, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="b8620-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="b8620-145">A `Type=notify` propriedade informa `systemd` que o aplicativo irá notificá-lo na inicialização e no desligamento.</span><span class="sxs-lookup"><span data-stu-id="b8620-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="b8620-146">A `WantedBy=multi-user.target` configuração fará com que o serviço seja iniciado quando o sistema Linux atingir "runlevel 2", o que significa que um shell de vários usuários não gráficas está ativo.</span><span class="sxs-lookup"><span data-stu-id="b8620-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="b8620-147">Antes que `systemd` o reconheça o serviço, ele precisa recarregar sua configuração.</span><span class="sxs-lookup"><span data-stu-id="b8620-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="b8620-148">Você controla `systemd` usando o `systemctl` comando.</span><span class="sxs-lookup"><span data-stu-id="b8620-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="b8620-149">Após o recarregamento, use o `status` subcomando para confirmar se o aplicativo foi registrado com êxito.</span><span class="sxs-lookup"><span data-stu-id="b8620-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="b8620-150">Se você tiver configurado o serviço corretamente, obterá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="b8620-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="b8620-151">Use o `start` comando para iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="b8620-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="b8620-152">A `.service` extensão é opcional quando você está usando o `systemctl start` .</span><span class="sxs-lookup"><span data-stu-id="b8620-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="b8620-153">Para saber `systemd` como iniciar o serviço automaticamente na inicialização do sistema, use o `enable` comando.</span><span class="sxs-lookup"><span data-stu-id="b8620-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="b8620-154">Log no diário</span><span class="sxs-lookup"><span data-stu-id="b8620-154">Log to journald</span></span>

<span data-ttu-id="b8620-155">O equivalente do Linux do log de eventos do Windows é `journald` um serviço de sistema de registro em log estruturado que faz parte do `systemd` .</span><span class="sxs-lookup"><span data-stu-id="b8620-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="b8620-156">As mensagens de log gravadas na saída padrão por um daemon do Linux são gravadas automaticamente no `journald` .</span><span class="sxs-lookup"><span data-stu-id="b8620-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="b8620-157">Para configurar os níveis de log, use a `Console` seção da configuração de log.</span><span class="sxs-lookup"><span data-stu-id="b8620-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="b8620-158">O `UseSystemd` método do host Builder configura automaticamente o formato de saída do console para se adequar ao diário.</span><span class="sxs-lookup"><span data-stu-id="b8620-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="b8620-159">Como `journald` o é o padrão para logs do Linux, uma variedade de ferramentas integra-se a ele.</span><span class="sxs-lookup"><span data-stu-id="b8620-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="b8620-160">Você pode facilmente rotear logs do `journald` para um sistema de log externo.</span><span class="sxs-lookup"><span data-stu-id="b8620-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="b8620-161">Trabalhando localmente no host, você pode usar o `journalctl` comando para exibir os logs da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="b8620-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="b8620-162">Se você tiver um ambiente de GUI disponível em seu host, alguns visualizadores de log gráficos estarão disponíveis para Linux, como *QJournalctl* e *logs GNOME*.</span><span class="sxs-lookup"><span data-stu-id="b8620-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="b8620-163">Para saber mais sobre como consultar o `systemd` diário na linha de comando usando `journalctl` , consulte [o manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="b8620-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="b8620-164">Certificados HTTPS para aplicativos de hospedagem interna</span><span class="sxs-lookup"><span data-stu-id="b8620-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="b8620-165">Quando você estiver executando um aplicativo gRPC em produção, deverá usar um certificado TLS de uma autoridade de certificação confiável (CA).</span><span class="sxs-lookup"><span data-stu-id="b8620-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="b8620-166">Essa autoridade de certificação pode ser uma CA pública ou uma interna para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8620-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="b8620-167">Em hosts do Windows, você pode carregar o certificado de um [repositório de certificados](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) seguro usando a <xref:System.Security.Cryptography.X509Certificates.X509Store> classe.</span><span class="sxs-lookup"><span data-stu-id="b8620-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="b8620-168">Você também pode usar a `X509Store` classe com o armazenamento de chaves OpenSSL em alguns hosts Linux.</span><span class="sxs-lookup"><span data-stu-id="b8620-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="b8620-169">Você também pode criar certificados usando um dos [construtores X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), de:</span><span class="sxs-lookup"><span data-stu-id="b8620-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="b8620-170">Um arquivo, como um `.pfx` arquivo protegido por uma senha forte</span><span class="sxs-lookup"><span data-stu-id="b8620-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="b8620-171">Dados binários recuperados de um serviço de armazenamento seguro, como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="b8620-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="b8620-172">Você pode configurar o Kestrel para usar um certificado de duas maneiras: da configuração ou no código.</span><span class="sxs-lookup"><span data-stu-id="b8620-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="b8620-173">Definir certificados HTTPS usando a configuração</span><span class="sxs-lookup"><span data-stu-id="b8620-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="b8620-174">A abordagem de configuração requer a definição do caminho para o arquivo de certificado `.pfx` e a senha na seção de configuração Kestrel.</span><span class="sxs-lookup"><span data-stu-id="b8620-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="b8620-175">No `appsettings.json` , isso teria a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="b8620-175">In `appsettings.json`, that would look like this:</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="b8620-176">Forneça a senha usando uma fonte de configuração segura, como o Azure Key Vault ou o cofre Hashicorp.</span><span class="sxs-lookup"><span data-stu-id="b8620-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8620-177">Não armazene senhas não criptografadas em arquivos de configuração.</span><span class="sxs-lookup"><span data-stu-id="b8620-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="b8620-178">Definir certificados HTTPS no código</span><span class="sxs-lookup"><span data-stu-id="b8620-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="b8620-179">Para configurar o HTTPS em Kestrel no código, use o `ConfigureKestrel` método em `IWebHostBuilder` na `Program` classe.</span><span class="sxs-lookup"><span data-stu-id="b8620-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="b8620-180">Novamente, certifique-se de armazenar a senha do `.pfx` arquivo em e recuperá-la de uma fonte de configuração segura.</span><span class="sxs-lookup"><span data-stu-id="b8620-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b8620-181">[Anterior](grpc-in-production.md) 
> [Avançar](docker.md)</span><span class="sxs-lookup"><span data-stu-id="b8620-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
