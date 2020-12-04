---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2020
ms.locfileid: "96585603"
---
<span data-ttu-id="e9a65-101">[Usando um cliente SFTP](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copie os arquivos do local de publicação no computador de desenvolvimento para uma nova pasta no Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="e9a65-101">[Using an SFTP client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copy the files from the publish location on the development computer to a new folder on the Raspberry Pi.</span></span>

<span data-ttu-id="e9a65-102">Por exemplo, para usar o `scp` comando para copiar arquivos do computador de desenvolvimento para o Raspberry Pi, abra um prompt de comando e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e9a65-102">For example, to use the `scp` command to copy files from the development computer to your Raspberry Pi, open a command prompt and execute the following:</span></span>

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

<span data-ttu-id="e9a65-103">Sendo que:</span><span class="sxs-lookup"><span data-stu-id="e9a65-103">Where:</span></span>

- <span data-ttu-id="e9a65-104">A `-r` opção instrui `scp` a copiar os arquivos recursivamente.</span><span class="sxs-lookup"><span data-stu-id="e9a65-104">The `-r` option instructs `scp` to copy files recursively.</span></span>
- <span data-ttu-id="e9a65-105">*/Publish-Location/* é a pasta que você publicou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e9a65-105">*/publish-location/* is the folder you published to in the previous step.</span></span>
- <span data-ttu-id="e9a65-106">`pi@raspberypi` é o usuário e os nomes de host no formato `<username>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="e9a65-106">`pi@raspberypi` is the user and host names in the format `<username>@<hostname>`.</span></span>
- <span data-ttu-id="e9a65-107">*/Home/PI/Deployment-Location/* é a nova pasta no Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="e9a65-107">*/home/pi/deployment-location/* is the new folder on the Raspberry Pi.</span></span>

> [!TIP]
> <span data-ttu-id="e9a65-108">As versões recentes do Windows têm o OpenSSH, que inclui o `scp` , pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="e9a65-108">Recent versions of Windows have OpenSSH, which includes `scp`, pre-installed.</span></span>
