---
title: Objetos binários de codificação com codificador ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276731"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="7eaa0-102">Objetos binários de codificação com codificador ByteStream</span><span class="sxs-lookup"><span data-stu-id="7eaa0-102">Encoding Binary Objects with ByteStream Encoder</span></span>

<span data-ttu-id="7eaa0-103">O envio e o recebimento de dados binários brutos com Windows Communication Foundation (WCF) são configurados usando <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="7eaa0-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="7eaa0-104">Arquitetura do codificador de mensagens de fluxo de bytes</span><span class="sxs-lookup"><span data-stu-id="7eaa0-104">Byte Stream Message Encoder Architecture</span></span>  

 <span data-ttu-id="7eaa0-105">O codificador de mensagem binária usado pelo WCF não tem nenhum recurso para processar, validar ou identificar os dados binários subjacentes na mensagem.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="7eaa0-106">O pacote de dados é codificado em XML, enviado, recebido e decodificado.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="7eaa0-107">O codificador processa os dados depois de serem passados para o transporte e antes que a mensagem seja enviada para a fila de mensagens.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="7eaa0-108">Funcionalmente, o codificador binário encapsula os dados da mensagem em `<binary>` elementos para enviar e remove os elementos depois que a mensagem é recebida.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="7eaa0-109">Usando o codificador de mensagens de fluxo de bytes</span><span class="sxs-lookup"><span data-stu-id="7eaa0-109">Using the Byte Stream Message Encoder</span></span>  

 <span data-ttu-id="7eaa0-110">O exemplo a seguir mostra um contrato de serviço que implementa o codificador de mensagem de fluxo de bytes.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="7eaa0-111">O exemplo a seguir mostra o serviço que está sendo invocado.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="7eaa0-112">No caso do uso de um serviço que implementa uma infraestrutura de mensagem (como um roteador), a mensagem é processada sem inspecionar, validar ou interagir com a mensagem, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="7eaa0-113">Cenários</span><span class="sxs-lookup"><span data-stu-id="7eaa0-113">Scenarios</span></span>  

 <span data-ttu-id="7eaa0-114">O codificador de fluxo de bytes é útil nos cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
- <span data-ttu-id="7eaa0-115">Transferindo uma imagem JPEG entre computadores usando o WCF.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="7eaa0-116">Nesse cenário, a imagem será recebida pelo transporte de uma fonte externa e os dados enviados serão os bytes brutos que compõem a imagem.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="7eaa0-117">Um serviço receberá os dados binários e exibirá a imagem.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-117">A service will receive the binary data and display the image.</span></span>  
  
- <span data-ttu-id="7eaa0-118">Ler informações de uma fila de mensagens e processá-las.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="7eaa0-119">A mensagem será lida de um Gerenciador de filas de mensagens e transmitida ao canal da fila de mensagens a ser tratada.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="7eaa0-120">O canal da fila de mensagens atuará como um Gerenciador de filas na pilha de canais do WCF.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="7eaa0-121">No caso de envio de uma mensagem por um canal da fila de mensagens, o remetente não tem controle sobre os bytes recebidos do Gerenciador de filas.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="7eaa0-122">Se o processo de recebimento não tiver capacidade para ler bytes brutos, a mensagem será recebida como formatada incorretamente e não será processada; Supõe-se que o processo de recebimento terá a capacidade de converter os bytes recebidos de volta em um formato utilizável.</span><span class="sxs-lookup"><span data-stu-id="7eaa0-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
