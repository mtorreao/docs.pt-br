---
title: Protobuf campos reservados – gRPC para desenvolvedores do WCF
description: Saiba mais sobre os campos reservados para compatibilidade entre versões.
ms.date: 12/15/2020
ms.openlocfilehash: d82043d619c5b3b81091ae4ea381e4778c1cf6ba
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938514"
---
# <a name="protobuf-reserved-fields"></a><span data-ttu-id="e2cb8-103">Campos reservados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="e2cb8-103">Protobuf reserved fields</span></span>

<span data-ttu-id="e2cb8-104">As garantias de compatibilidade com versões anteriores no buffer de protocolo (Protobuf) dependem de números de campo sempre representando o mesmo item de dados.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-104">The backward-compatibility guarantees in Protocol Buffer (Protobuf) rely on field numbers always representing the same data item.</span></span> <span data-ttu-id="e2cb8-105">Se um campo for removido de uma mensagem em uma nova versão do serviço, esse número de campo nunca deverá ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-105">If a field is removed from a message in a new version of the service, that field number should never be reused.</span></span> <span data-ttu-id="e2cb8-106">Você pode impor esse comportamento usando a `reserved` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-106">You can enforce this behavior by using the `reserved` keyword.</span></span>

<span data-ttu-id="e2cb8-107">Se os `displayName` `marketId` campos e tiverem sido removidos da `Stock` mensagem definida anteriormente, os números de campos deverão ser reservados como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-107">If the `displayName` and `marketId` fields were removed from the `Stock` message defined earlier, their field numbers should be reserved as in the following example.</span></span>

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

<span data-ttu-id="e2cb8-108">Você também pode usar a `reserved` palavra-chave como um espaço reservado para campos que podem ser adicionados no futuro.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-108">You can also use the `reserved` keyword as a placeholder for fields that might be added in the future.</span></span> <span data-ttu-id="e2cb8-109">Você pode expressar números de campo contíguos como um intervalo usando a `to` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="e2cb8-109">You can express contiguous field numbers as a range by using the `to` keyword.</span></span>

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="e2cb8-110">[Anterior](protobuf-repeated.md) 
> [Avançar](protobuf-any-oneof.md)</span><span class="sxs-lookup"><span data-stu-id="e2cb8-110">[Previous](protobuf-repeated.md)
[Next](protobuf-any-oneof.md)</span></span>
