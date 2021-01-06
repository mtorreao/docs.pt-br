---
title: Comparando o WCF com o gRPC-gRPC para desenvolvedores do WCF
description: Uma comparação das estruturas do WCF e do gRPC para a criação de aplicativos distribuídos.
ms.date: 12/15/2020
ms.openlocfilehash: 7dd41c3d6f248bb1ef5eacb323b1443c7bc575a7
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938488"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="49466-103">Comparando o WCF com o gRPC</span><span class="sxs-lookup"><span data-stu-id="49466-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="49466-104">O capítulo anterior forneceu uma boa visão sobre Protobuf e como o gRPC lida com mensagens.</span><span class="sxs-lookup"><span data-stu-id="49466-104">The previous chapter gave you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="49466-105">Antes de você trabalhar com uma conversão detalhada de Windows Communication Foundation (WCF) para gRPC, é importante saber como os recursos disponíveis no WCF são manipulados no gRPC e quais soluções alternativas você pode usar quando não há nenhum equivalente gRPC.</span><span class="sxs-lookup"><span data-stu-id="49466-105">Before you work through a detailed conversion from Windows Communication Foundation (WCF) to gRPC, it's important know how the features available in WCF are handled in gRPC and what workarounds you can use when there's no gRPC equivalent.</span></span> <span data-ttu-id="49466-106">Em particular, este capítulo abordará os seguintes assuntos:</span><span class="sxs-lookup"><span data-stu-id="49466-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="49466-107">Operações e métodos</span><span class="sxs-lookup"><span data-stu-id="49466-107">Operations and methods</span></span>
- <span data-ttu-id="49466-108">Associações e transportes</span><span class="sxs-lookup"><span data-stu-id="49466-108">Bindings and transports</span></span>
- <span data-ttu-id="49466-109">Tipos de RPC</span><span class="sxs-lookup"><span data-stu-id="49466-109">RPC types</span></span>
- <span data-ttu-id="49466-110">Metadados</span><span class="sxs-lookup"><span data-stu-id="49466-110">Metadata</span></span>
- <span data-ttu-id="49466-111">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="49466-111">Error handling</span></span>
- <span data-ttu-id="49466-112">WS- \* Protocols</span><span class="sxs-lookup"><span data-stu-id="49466-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="49466-113">exemplo de gRPC</span><span class="sxs-lookup"><span data-stu-id="49466-113">gRPC example</span></span>

<span data-ttu-id="49466-114">Quando você cria um novo projeto ASP.NET Core 5,0 gRPC no Visual Studio 2019 ou na linha de comando, o equivalente de gRPC de "Olá, Mundo" é gerado para você.</span><span class="sxs-lookup"><span data-stu-id="49466-114">When you create a new ASP.NET Core 5.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="49466-115">Ele consiste em um `greeter.proto` arquivo que define o serviço e suas mensagens, e um `GreeterService.cs` arquivo com uma implementação do serviço.</span><span class="sxs-lookup"><span data-stu-id="49466-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="49466-116">Este capítulo fará referência a este código de exemplo ao explicar diferentes conceitos e recursos do gRPC.</span><span class="sxs-lookup"><span data-stu-id="49466-116">This chapter will refer to this example code when explaining different concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="49466-117">[Anterior](protobuf-maps.md) 
> [Avançar](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="49466-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
