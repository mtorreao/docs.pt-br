---
title: Migrar uma solução WCF para o gRPC-gRPC para desenvolvedores do WCF
description: Como migrar diferentes tipos de serviços WCF para o equivalente em gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: 3bd35cb6119368ff3db3be9ab5fabf89f2652b29
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937955"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="7dc15-103">Migrar uma solução WCF para o gRPC</span><span class="sxs-lookup"><span data-stu-id="7dc15-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="7dc15-104">Este capítulo descreverá como trabalhar com projetos ASP.NET Core 5,0 gRPC e demonstrar a migração de diferentes tipos de serviços de Windows Communication Foundation (WCF) para o equivalente gRPC:</span><span class="sxs-lookup"><span data-stu-id="7dc15-104">This chapter will describe how to work with ASP.NET Core 5.0 gRPC projects and demonstrate migrating different types of Windows Communication Foundation (WCF) services to the gRPC equivalent:</span></span>

- <span data-ttu-id="7dc15-105">Crie um projeto ASP.NET Core gRPC 5,0.</span><span class="sxs-lookup"><span data-stu-id="7dc15-105">Create an ASP.NET Core 5.0 gRPC project.</span></span>
- <span data-ttu-id="7dc15-106">Operações simples de solicitação-resposta para RPC unário gRPC.</span><span class="sxs-lookup"><span data-stu-id="7dc15-106">Simple request-reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="7dc15-107">Operações unidirecionais para RPC de streaming de cliente gRPC.</span><span class="sxs-lookup"><span data-stu-id="7dc15-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="7dc15-108">Serviços Full duplex para RPC de streaming bidirecional gRPC.</span><span class="sxs-lookup"><span data-stu-id="7dc15-108">Full-duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="7dc15-109">Também há uma comparação entre usar os serviços de streaming versus campos repetidos para retornar conjuntos de valores, e há uma discussão sobre o uso de bibliotecas de cliente no final do capítulo.</span><span class="sxs-lookup"><span data-stu-id="7dc15-109">There's also a comparison of using streaming services versus repeated fields for returning datasets, and there's a discussion of the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="7dc15-110">O aplicativo WCF de exemplo é um stub mínimo de um conjunto de serviços de comércio de estoque.</span><span class="sxs-lookup"><span data-stu-id="7dc15-110">The sample WCF application is a minimal stub of a set of stock trading services.</span></span> <span data-ttu-id="7dc15-111">Ele usa a biblioteca de contêineres IoC (inversão de controle de código aberto) chamada Autofac para injeção de dependência.</span><span class="sxs-lookup"><span data-stu-id="7dc15-111">It uses the open-source Inversion of Control (IoC) container library called Autofac for dependency injection.</span></span> <span data-ttu-id="7dc15-112">Ele inclui três serviços, um para cada tipo de serviço do WCF.</span><span class="sxs-lookup"><span data-stu-id="7dc15-112">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="7dc15-113">Os serviços serão discutidos mais detalhadamente nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7dc15-113">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="7dc15-114">Você pode baixar as soluções de [dotnet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) no github.</span><span class="sxs-lookup"><span data-stu-id="7dc15-114">You can download the solutions from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="7dc15-115">Os serviços usam dados falsos para minimizar dependências externas.</span><span class="sxs-lookup"><span data-stu-id="7dc15-115">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="7dc15-116">Os exemplos incluem as implementações do WCF e do gRPC de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="7dc15-116">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7dc15-117">[Anterior](ws-protocols.md) 
> [Avançar](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="7dc15-117">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
