---
title: Operações básicas de pipe no .NET
description: 'Saiba mais sobre as operações de pipe no .NET. Os pipes fornecem um meio de comunicação entre processos. Há dois tipos de Pipes: Pipes anônimos e pipes nomeados.'
ms.date: 03/30/2017
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 3ec4ee61bfd3a0a82eb0a0884b89c19a9300b078
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819091"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="230e6-105">Operações básicas de pipe no .NET</span><span class="sxs-lookup"><span data-stu-id="230e6-105">Pipe Operations in .NET</span></span>
<span data-ttu-id="230e6-106">Os pipes fornecem um meio de comunicação entre processos.</span><span class="sxs-lookup"><span data-stu-id="230e6-106">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="230e6-107">Existem dois tipos de pipes:</span><span class="sxs-lookup"><span data-stu-id="230e6-107">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="230e6-108">Pipes anônimos.</span><span class="sxs-lookup"><span data-stu-id="230e6-108">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="230e6-109">Os pipes anônimos fornecem comunicação entre processos em um computador local.</span><span class="sxs-lookup"><span data-stu-id="230e6-109">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="230e6-110">Os pipes anônimos exigem menos sobrecarga do que os pipes nomeados mas oferecem serviços limitados.</span><span class="sxs-lookup"><span data-stu-id="230e6-110">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="230e6-111">Os pipes anônimos são unidirecionais e não podem ser usados em uma rede.</span><span class="sxs-lookup"><span data-stu-id="230e6-111">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="230e6-112">Eles oferecem suporte a apenas uma única instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="230e6-112">They support only a single server instance.</span></span> <span data-ttu-id="230e6-113">Os pipes anônimos são úteis para a comunicação entre threads ou entre processos pai e filho em que os identificadores de pipe podem ser facilmente passados para o processo filho quando ele é criado.</span><span class="sxs-lookup"><span data-stu-id="230e6-113">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="230e6-114">No .NET, você implementa pipes anônimos usando as classes <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="230e6-114">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="230e6-115">Veja [Como usar pipes anônimos para a comunicação entre processos locais](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="230e6-115">See [How to: Use Anonymous Pipes for Local Interprocess Communication](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="230e6-116">Pipes nomeados.</span><span class="sxs-lookup"><span data-stu-id="230e6-116">Named pipes.</span></span>  
  
     <span data-ttu-id="230e6-117">Os pipes nomeados fornecem a comunicação entre processos entre um servidor de pipe e um ou mais clientes pipe.</span><span class="sxs-lookup"><span data-stu-id="230e6-117">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="230e6-118">Os pipes nomeados podem ser unidirecionais ou bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="230e6-118">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="230e6-119">Eles oferecem suporte à comunicação baseada em mensagens e permitem que vários clientes se conectem simultaneamente ao processo do servidor usando o mesmo nome de pipe.</span><span class="sxs-lookup"><span data-stu-id="230e6-119">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="230e6-120">Os pipes nomeados também oferecem suporte à representação, que permite aos processos de conexão usar suas próprias permissões em servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="230e6-120">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="230e6-121">No .NET, você implementa pipes nomeados usando as classes <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="230e6-121">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="230e6-122">Veja [Como usar pipes nomeados para comunicação entre processos na rede](how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="230e6-122">See [How to: Use Named Pipes for Network Interprocess Communication](how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230e6-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="230e6-123">See also</span></span>

- [<span data-ttu-id="230e6-124">E/S de arquivo e de fluxo</span><span class="sxs-lookup"><span data-stu-id="230e6-124">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="230e6-125">Como: Usar pipes anônimos para comunicação entre processos locais</span><span class="sxs-lookup"><span data-stu-id="230e6-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="230e6-126">Como: Usar pipes nomeados para comunicação entre processos na rede</span><span class="sxs-lookup"><span data-stu-id="230e6-126">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
