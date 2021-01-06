---
title: Protocolos de rede-gRPC para desenvolvedores do WCF
description: Uma visão geral dos protocolos de rede gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 801d57c95aec748e5dcf667ca480775ff945b55c
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938553"
---
# <a name="network-protocols"></a><span data-ttu-id="9d999-103">Protocolos de rede</span><span class="sxs-lookup"><span data-stu-id="9d999-103">Network protocols</span></span>

<span data-ttu-id="9d999-104">Ao contrário de Windows Communication Foundation (WCF), o gRPC usa HTTP/2 como base para sua rede.</span><span class="sxs-lookup"><span data-stu-id="9d999-104">Unlike Windows Communication Foundation (WCF), gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="9d999-105">Esse protocolo oferece vantagens significativas em relação ao WCF e ao SOAP, que operam somente no HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="9d999-105">This protocol offers significant advantages over WCF and SOAP, which operate only on HTTP/1.1.</span></span> <span data-ttu-id="9d999-106">Para os desenvolvedores que desejam usar o gRPC, Considerando que não há nenhuma alternativa ao HTTP/2, parece ser o momento ideal para explorar o HTTP/2 mais detalhadamente e identificar os benefícios adicionais do uso do gRPC.</span><span class="sxs-lookup"><span data-stu-id="9d999-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits of using gRPC.</span></span>

<span data-ttu-id="9d999-107">O HTTP/2, lançado pela Internet Engineering Task Force no 2015, foi derivado do protocolo SPDY experimental, que já estava sendo usado pelo Google.</span><span class="sxs-lookup"><span data-stu-id="9d999-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="9d999-108">Ele foi projetado especificamente para ser mais eficiente, mais rápido e mais seguro do que o HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="9d999-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="9d999-109">Principais recursos do HTTP/2</span><span class="sxs-lookup"><span data-stu-id="9d999-109">Key features of HTTP/2</span></span>

<span data-ttu-id="9d999-110">Esta lista mostra alguns dos principais recursos e vantagens do HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="9d999-110">This list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="9d999-111">Protocolo binário</span><span class="sxs-lookup"><span data-stu-id="9d999-111">Binary protocol</span></span>

<span data-ttu-id="9d999-112">Os ciclos de solicitação/resposta não precisam mais de comandos de texto.</span><span class="sxs-lookup"><span data-stu-id="9d999-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="9d999-113">Essa atividade simplifica e acelera a implementação de comandos.</span><span class="sxs-lookup"><span data-stu-id="9d999-113">This activity simplifies and speeds up the implementation of commands.</span></span> <span data-ttu-id="9d999-114">Especificamente, a análise de dados é mais rápida e usa menos memória, a latência de rede é reduzida com melhorias de desempenho óbvias em relação à velocidade, e há um melhor uso geral dos recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="9d999-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="9d999-115">Fluxos</span><span class="sxs-lookup"><span data-stu-id="9d999-115">Streams</span></span>

<span data-ttu-id="9d999-116">Os fluxos permitem que você crie conexões de longa duração entre o remetente e o destinatário, em que várias mensagens ou quadros podem ser enviados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="9d999-116">Streams allow you to create long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="9d999-117">Vários fluxos podem operar de forma independente em uma única conexão HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="9d999-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="9d999-118">Solicitação de multiplexação em uma única conexão TCP</span><span class="sxs-lookup"><span data-stu-id="9d999-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="9d999-119">Esse recurso é uma das inovações mais importantes do HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="9d999-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="9d999-120">Como ele permite várias solicitações paralelas de dados, agora é possível baixar arquivos da Web simultaneamente de um único servidor.</span><span class="sxs-lookup"><span data-stu-id="9d999-120">Because it allows multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="9d999-121">Os sites são carregados mais rapidamente e a necessidade de otimização é reduzida.</span><span class="sxs-lookup"><span data-stu-id="9d999-121">Websites load faster, and the need for optimization is reduced.</span></span> <span data-ttu-id="9d999-122">Bloqueio de cabeçalho de linha (Chol), em que as respostas que estão prontas devem aguardar para serem enviadas até que uma solicitação anterior seja concluída, também é mitigada (embora o bloqueio de Chol ainda possa ocorrer no nível de transporte de TCP).</span><span class="sxs-lookup"><span data-stu-id="9d999-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP-transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="9d999-123">Desempenho de net. TCP como, entre plataformas</span><span class="sxs-lookup"><span data-stu-id="9d999-123">Net.TCP-like performance, cross-platform</span></span>

<span data-ttu-id="9d999-124">Fundamentalmente, a combinação de gRPC e HTTP/2 oferece aos desenvolvedores pelo menos a velocidade equivalente e a eficiência das associações de net. TCP para o WCF e, em alguns casos, até maior velocidade e eficiência.</span><span class="sxs-lookup"><span data-stu-id="9d999-124">Fundamentally, the combination of gRPC and HTTP/2 offers developers at least the equivalent speed and efficiency of Net.TCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="9d999-125">Mas, ao contrário de net. TCP, gRPC sobre HTTP/2 não é restrito a aplicativos .NET.</span><span class="sxs-lookup"><span data-stu-id="9d999-125">But, unlike Net.TCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9d999-126">[Anterior](interface-definition-language.md) 
> [Avançar](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="9d999-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
