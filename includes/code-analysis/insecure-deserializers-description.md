---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 9235f1bcda7529b71aef542d3a49da08a9d4b59e
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96584633"
---
<span data-ttu-id="7ac0a-101">Desserializadores inseguros são vulneráveis ao desserializar dados não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="7ac0a-101">Insecure deserializers are vulnerable when deserializing untrusted data.</span></span> <span data-ttu-id="7ac0a-102">Um invasor pode modificar os dados serializados para incluir tipos inesperados para injetar objetos com efeitos colaterais mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="7ac0a-102">An attacker could modify the serialized data to include unexpected types to inject objects with malicious side effects.</span></span> <span data-ttu-id="7ac0a-103">Um ataque contra um desserializador inseguro pode, por exemplo, executar comandos no sistema operacional subjacente, comunicar-se pela rede ou excluir arquivos.</span><span class="sxs-lookup"><span data-stu-id="7ac0a-103">An attack against an insecure deserializer could, for example, execute commands on the underlying operating system, communicate over the network, or delete files.</span></span>
