---
title: Transportes no Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 8623b788b848867f25836a657b07349dd50c2780
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251679"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="135b1-102">Transportes no Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="135b1-102">Transports in Windows Communication Foundation</span></span>

<span data-ttu-id="135b1-103">A camada de transporte está no nível mais baixo da pilha de canais.</span><span class="sxs-lookup"><span data-stu-id="135b1-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="135b1-104">Os transportes principais usados no Windows Communication Foundation (WCF) são HTTP, HTTPS, TCP e pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="135b1-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="135b1-105">Os tópicos nesta seção abordam a escolha entre esses transportes, a configuração do transporte e a definição de propriedades de ajuste.</span><span class="sxs-lookup"><span data-stu-id="135b1-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="135b1-106">O WCF inclui transportes adicionais.</span><span class="sxs-lookup"><span data-stu-id="135b1-106">WCF includes additional transports.</span></span> <span data-ttu-id="135b1-107">Para obter informações sobre o transporte do serviço de enfileiramento de mensagens (também conhecido como MSMQ), consulte [filas e sessões confiáveis](queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="135b1-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="135b1-108">Para obter informações sobre o transporte ponto a ponto, consulte [rede ponto a ponto](peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="135b1-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="135b1-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="135b1-109">In This Section</span></span>  

 [<span data-ttu-id="135b1-110">Selecionando um transporte</span><span class="sxs-lookup"><span data-stu-id="135b1-110">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="135b1-111">Descreve os três transportes principais e considerações na seleção de um.</span><span class="sxs-lookup"><span data-stu-id="135b1-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="135b1-112">Escolhendo um codificador de mensagem</span><span class="sxs-lookup"><span data-stu-id="135b1-112">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="135b1-113">Descreve os fatores a serem considerados ao escolher um elemento de associação de codificação de mensagem.</span><span class="sxs-lookup"><span data-stu-id="135b1-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="135b1-114">Transmissão de transferência de mensagem</span><span class="sxs-lookup"><span data-stu-id="135b1-114">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="135b1-115">Descreve como configurar a camada de transporte para fazer streaming.</span><span class="sxs-lookup"><span data-stu-id="135b1-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="135b1-116">Configurando HTTP e HTTPS</span><span class="sxs-lookup"><span data-stu-id="135b1-116">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="135b1-117">Descreve como configurar os elementos de associação de transporte HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="135b1-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="135b1-118">Como: substituir a reserva de URL do WCF com uma reserva restrita</span><span class="sxs-lookup"><span data-stu-id="135b1-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="135b1-119">Descreve como usar reservas restritas do WCFURL.</span><span class="sxs-lookup"><span data-stu-id="135b1-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="135b1-120">Cotas de transporte</span><span class="sxs-lookup"><span data-stu-id="135b1-120">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="135b1-121">Descreve as considerações sobre como definir as cotas disponíveis na camada de transporte.</span><span class="sxs-lookup"><span data-stu-id="135b1-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="135b1-122">Trabalhando com NATs e firewalls</span><span class="sxs-lookup"><span data-stu-id="135b1-122">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="135b1-123">Descreve como configurar a camada de transporte quando as mensagens são enviadas ou recebidas atrás de um firewall ou quando a conversão de endereços de rede (NAT) está presente.</span><span class="sxs-lookup"><span data-stu-id="135b1-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="135b1-124">Compartilhamento de porta Net.TCP</span><span class="sxs-lookup"><span data-stu-id="135b1-124">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="135b1-125">Descreve como usar o componente de compartilhamento de porta Net. TCP do WCF.</span><span class="sxs-lookup"><span data-stu-id="135b1-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="135b1-126">Referência</span><span class="sxs-lookup"><span data-stu-id="135b1-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="135b1-127">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="135b1-127">Related Sections</span></span>  

 [<span data-ttu-id="135b1-128">Associações</span><span class="sxs-lookup"><span data-stu-id="135b1-128">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="135b1-129">Estendendo associações</span><span class="sxs-lookup"><span data-stu-id="135b1-129">Extending Bindings</span></span>](../extending/extending-bindings.md)
