---
title: 'Como: Modificar o arquivo de configuração do computador para habilitar o suporte ao IPv6'
description: Saiba como modificar o arquivo de configuração do computador, machine.config, para habilitar o suporte a IPv6 no .NET Framework.
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 2c5e3e094eca480a7cab4f7c25cc0fedba196338
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269594"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="fd30f-103">Como: Modificar o arquivo de configuração do computador para habilitar o suporte ao IPv6</span><span class="sxs-lookup"><span data-stu-id="fd30f-103">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>

<span data-ttu-id="fd30f-104">O exemplo de código a seguir mostra como modificar o arquivo de configuração do computador, *machine.config* para habilitar o suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="fd30f-104">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="fd30f-105">O arquivo *machine.config* é armazenado na pasta *%Windir%\Microsoft.NET\Framework* no diretório em que o Windows foi instalado.</span><span class="sxs-lookup"><span data-stu-id="fd30f-105">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="fd30f-106">Há um outro arquivo *machine.config* nas pastas em *%Windir%\Microsoft.NET\Framework* para cada versão do .NET Framework instalada no computador (por exemplo, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="fd30f-106">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="fd30f-107">Essas configurações também podem ser feitas no arquivo de configuração do aplicativo, que tem precedência sobre o arquivo de configuração do computador.</span><span class="sxs-lookup"><span data-stu-id="fd30f-107">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="fd30f-108">Para o .NET Framework versão 1.1 e anterior, o valor da opção de configuração **ipv6 enabled** especifica se os membros da classe <xref:System.Net.Dns?displayProperty=nameWithType> retornam endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="fd30f-108">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="fd30f-109">Para o .NET Framework versão 2.0 e posteriores, se o Windows der suporte ao IPv6, todos os membros da classe <xref:System.Net.Dns?displayProperty=nameWithType>, (por exemplo, o método <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>), retornarão endereços IPv6 com uma limitação.</span><span class="sxs-lookup"><span data-stu-id="fd30f-109">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="fd30f-110">Os membros obsoletos da classe <xref:System.Net.Dns?displayProperty=nameWithType> (por exemplo, o método <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) lerão e reconhecerão o valor no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="fd30f-110">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd30f-111">Para o .NET Framework versão 2.0 e posteriores, o IPv6 é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fd30f-111">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="fd30f-112">Para o .NET Framework versão 1.1 e anteriores, o IPv6 é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="fd30f-112">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd30f-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fd30f-113">Example</span></span>  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>
    ……………  
    </settings>  
    ………………  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd30f-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fd30f-114">See also</span></span>

- [<span data-ttu-id="fd30f-115">Endereçamento IPv6</span><span class="sxs-lookup"><span data-stu-id="fd30f-115">IPv6 Addressing</span></span>](ipv6-addressing.md)
- [<span data-ttu-id="fd30f-116">Esquema de configurações de rede</span><span class="sxs-lookup"><span data-stu-id="fd30f-116">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="fd30f-117">\<ipv6> Elemento (configurações de rede)</span><span class="sxs-lookup"><span data-stu-id="fd30f-117">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
