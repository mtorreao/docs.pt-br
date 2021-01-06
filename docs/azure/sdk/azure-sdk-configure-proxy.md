---
title: Configurar um servidor proxy ao usar o SDK do Azure para .NET
description: Usar HTTP [S] _PROXY variáveis de ambiente para definir um proxy para o SDK do Azure para .NET
ms.date: 12/10/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.openlocfilehash: 64d525f8a6c277a5ac383dfded828f2fd3cfd744
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701057"
---
# <a name="configure-a-proxy-server-when-using-the-azure-sdk-for-net"></a><span data-ttu-id="815ca-103">Configurar um servidor proxy ao usar o SDK do Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="815ca-103">Configure a proxy server when using the Azure SDK for .NET</span></span>

<span data-ttu-id="815ca-104">Se sua organização exigir o uso de um servidor proxy para acessar recursos da Internet, será necessário definir uma variável de ambiente com as informações do servidor proxy para usar o SDK do Azure para .NET.</span><span class="sxs-lookup"><span data-stu-id="815ca-104">If your organization requires the use of a proxy server to access internet resources, you will need to set an environment variable with the proxy server information to use the Azure SDK for .NET.</span></span>  

## <a name="configuration-using-environment-variables"></a><span data-ttu-id="815ca-105">Configuração usando variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="815ca-105">Configuration using environment variables</span></span>

<span data-ttu-id="815ca-106">Dependendo de se o servidor proxy usar HTTP ou HTTPS, você definirá a variável de ambiente `HTTP_PROXY` ou, `HTTPS_PROXY` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="815ca-106">Depending on if your proxy server uses HTTP or HTTPS, you will set either the environment variable `HTTP_PROXY` or `HTTPS_PROXY` respectively.</span></span> <span data-ttu-id="815ca-107">A URL do servidor proxy tem o formato `http[s]://[username:password@]<ip_address_or_hostname>:<port>/` em que a `username:password` combinação é opcional.</span><span class="sxs-lookup"><span data-stu-id="815ca-107">The proxy server URL has the form `http[s]://[username:password@]<ip_address_or_hostname>:<port>/` where the `username:password` combination is optional.</span></span> <span data-ttu-id="815ca-108">Para obter o endereço IP, o nome do host, a porta e as credenciais do servidor proxy, consulte o administrador da rede.</span><span class="sxs-lookup"><span data-stu-id="815ca-108">To get the IP address or hostname, port and credentials for your proxy server, consult your network administrator.</span></span>

<span data-ttu-id="815ca-109">Os exemplos a seguir mostram como definir as variáveis de ambiente apropriadas em ambientes Shell de comando (Windows) e bash (Linux/Mac).</span><span class="sxs-lookup"><span data-stu-id="815ca-109">The following examples show how to set the appropriate environment variables in command shell (Windows) and bash (Linux/Mac) environments.</span></span>  <span data-ttu-id="815ca-110">Definir a variável de ambiente apropriada fará com que o SDK do Azure para .NET use o servidor proxy em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="815ca-110">Setting the appropriate environment variable will then cause the Azure SDK for .NET to use the proxy server at runtime.</span></span>

### <a name="cmd"></a>[<span data-ttu-id="815ca-111">cmd</span><span class="sxs-lookup"><span data-stu-id="815ca-111">cmd</span></span>](#tab/cmd)

```cmd
rem Non-authenticated HTTP server:
set HTTP_PROXY=http://10.10.1.10:1180

rem Authenticated HTTP server:
set HTTP_PROXY=http://username:password@10.10.1.10:1180

rem Non-authenticated HTTPS server:
set HTTPS_PROXY=http://10.10.1.10:1180

rem Authenticated HTTPS server:
set HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

### <a name="bash"></a>[<span data-ttu-id="815ca-112">Bash</span><span class="sxs-lookup"><span data-stu-id="815ca-112">bash</span></span>](#tab/bash)

```bash
# Non-authenticated HTTP server:
HTTP_PROXY=http://10.10.1.10:1180

# Authenticated HTTP server:
HTTP_PROXY=http://username:password@10.10.1.10:1180

# Non-authenticated HTTPS server:
HTTPS_PROXY=http://10.10.1.10:1180

# Authenticated HTTPS server:
HTTPS_PROXY=http://username:password@10.10.1.10:1180
```

---
