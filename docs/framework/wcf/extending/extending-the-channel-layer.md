---
title: Estendendo a camada do canal
ms.date: 03/30/2017
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
ms.openlocfilehash: 8d051ff84ea0562b3d7c810b2c884f4d8b787952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273016"
---
# <a name="extending-the-channel-layer"></a><span data-ttu-id="f03bd-102">Estendendo a camada do canal</span><span class="sxs-lookup"><span data-stu-id="f03bd-102">Extending the Channel Layer</span></span>

<span data-ttu-id="f03bd-103">A camada de canal é responsável pela troca de mensagens entre clientes e serviços.</span><span class="sxs-lookup"><span data-stu-id="f03bd-103">The channel layer is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="f03bd-104">As extensões de canal podem implementar a nova funcionalidade de protocolo, como segurança ou funcionalidade de transporte, como implementar um novo transporte de rede para transportar mensagens SOAP.</span><span class="sxs-lookup"><span data-stu-id="f03bd-104">Channel extensions can implement new protocol functionality, such as security, or transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f03bd-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f03bd-105">In This Section</span></span>  

 [<span data-ttu-id="f03bd-106">Visão geral de modelo de canal</span><span class="sxs-lookup"><span data-stu-id="f03bd-106">Channel Model Overview</span></span>](channel-model-overview.md)  
 <span data-ttu-id="f03bd-107">Fornece uma visão geral de alto nível de quais canais são, os recursos que eles fornecem e como eles funcionam tanto em um serviço quanto em um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="f03bd-107">Provides a high-level overview of what channels are, the features that they provide and how they work both in a service and a client application.</span></span>  
  
 [<span data-ttu-id="f03bd-108">Canais de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="f03bd-108">Developing Channels</span></span>](developing-channels.md)  
 <span data-ttu-id="f03bd-109">Descreve detalhadamente as funções que os vários tipos de infraestrutura de canal desempenham, como funciona o ciclo de vida de estado e o mecanismo de estado, como lidar com exceções e falhas, como implementar o suporte a metadados e como os canais funcionam com codificadores de mensagem.</span><span class="sxs-lookup"><span data-stu-id="f03bd-109">Describes in depth the roles that the various channel infrastructure types play, how the state engine and state lifecycle works, how to handle exceptions and faults, how to implement metadata support, and how channels work with message encoders.</span></span>  
  
 [<span data-ttu-id="f03bd-110">Decodificadores personalizados</span><span class="sxs-lookup"><span data-stu-id="f03bd-110">Custom Encoders</span></span>](custom-encoders.md)  
 <span data-ttu-id="f03bd-111">Descreve a função que os codificadores de mensagem desempenham em canais e como criar um.</span><span class="sxs-lookup"><span data-stu-id="f03bd-111">Describes the role that message encoders play in channels and how to build one.</span></span>  
  
 [<span data-ttu-id="f03bd-112">Atualizações de fluxo personalizadas</span><span class="sxs-lookup"><span data-stu-id="f03bd-112">Custom Stream Upgrades</span></span>](custom-stream-upgrades.md)  
 <span data-ttu-id="f03bd-113">Descreve o processo de atualização dos fluxos fornecidos por transportes orientados a fluxo.</span><span class="sxs-lookup"><span data-stu-id="f03bd-113">Describes the process of upgrading the streams provided by stream-oriented transports.</span></span>
