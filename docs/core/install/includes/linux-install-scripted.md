---
ms.openlocfilehash: 540eebd957ce8ce0928db2bd8317cb220cba30bb
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031742"
---

<span data-ttu-id="01a1b-101">Os [scripts dotnet-install](../../tools/dotnet-install-script.md) são usados para instalações de automação e não administrativas do **SDK** e do **tempo de execução**.</span><span class="sxs-lookup"><span data-stu-id="01a1b-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="01a1b-102">É possível baixar o script em <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="01a1b-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="01a1b-103">O script assume como padrão a instalação da versão mais recente do [LTS (suporte a longo prazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) do SDK, que é o .net Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="01a1b-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="01a1b-104">Para instalar a versão atual, que pode não ser uma versão (LTS), use o `-c Current` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="01a1b-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="01a1b-105">Para instalar o tempo de execução do .NET em vez do SDK, use o `--runtime` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="01a1b-105">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="01a1b-106">Você pode instalar uma versão específica alterando o `-c` parâmetro para indicar a versão específica.</span><span class="sxs-lookup"><span data-stu-id="01a1b-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="01a1b-107">O comando a seguir instala o SDK do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="01a1b-107">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="01a1b-108">Para obter mais informações, consulte [dotnet – referência de scripts de instalação](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="01a1b-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
