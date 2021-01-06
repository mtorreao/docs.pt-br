---
title: Migrar serviços do WCF duplex para gRPC-gRPC para desenvolvedores do WCF
description: Saiba como migrar várias formas de serviços de duplex do WCF para serviços de streaming do gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: 4741e5ad5c12fa358853381d4f2c286add14f8f5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938020"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="6b8da-103">Migrar serviços duplex do WCF para gRPC</span><span class="sxs-lookup"><span data-stu-id="6b8da-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="6b8da-104">Agora que você tem uma noção dos conceitos básicos, nesta seção, você examinará os serviços gRPC de *streaming* mais complicados.</span><span class="sxs-lookup"><span data-stu-id="6b8da-104">Now that you have a sense of the basic concepts, in this section, you'll look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="6b8da-105">Há várias maneiras de usar os serviços duplex no Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6b8da-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="6b8da-106">Alguns serviços são iniciados pelo cliente e, em seguida, transmitem dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="6b8da-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="6b8da-107">Outros serviços Full duplex podem envolver uma comunicação bidirecional mais contínua, como o exemplo de calculadora clássica na documentação do WCF.</span><span class="sxs-lookup"><span data-stu-id="6b8da-107">Other full-duplex services might involve more ongoing two-way communication, like the classic Calculator example in the WCF documentation.</span></span> <span data-ttu-id="6b8da-108">Este capítulo usará duas implementações possíveis de cotação de ações do WCF e as migrará para o gRPC: uma que usa um RPC de streaming de servidor e outra que usa um RPC de streaming bidirecional.</span><span class="sxs-lookup"><span data-stu-id="6b8da-108">This chapter will take two possible WCF stock ticker implementations and migrate them to gRPC: one that uses a server streaming RPC and another one that uses a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="6b8da-109">RPC de streaming do servidor</span><span class="sxs-lookup"><span data-stu-id="6b8da-109">Server streaming RPC</span></span>

<span data-ttu-id="6b8da-110">No [exemplo da solução SimpleStockTicker do WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, há um serviço duplex para o qual o cliente inicia a conexão com uma lista de símbolos de ações e o servidor usa a interface de retorno de *chamada* para enviar atualizações à medida que elas se tornam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6b8da-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, there's a duplex service for which the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="6b8da-111">O cliente implementa essa interface para responder a chamadas do servidor.</span><span class="sxs-lookup"><span data-stu-id="6b8da-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="6b8da-112">A solução WCF</span><span class="sxs-lookup"><span data-stu-id="6b8da-112">The WCF solution</span></span>

<span data-ttu-id="6b8da-113">A solução WCF é implementada como um servidor net. TCP auto-hospedado em um .NET Framework 4. *x* aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="6b8da-113">The WCF solution is implemented as a self-hosted Net.TCP server in a .NET Framework 4.*x* console application.</span></span>

#### <a name="servicecontract"></a><span data-ttu-id="6b8da-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="6b8da-114">ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="6b8da-115">O serviço tem um único método sem nenhum tipo de retorno porque ele usa a interface de retorno `ISimpleStockTickerCallback` de chamada para enviar dados para o cliente em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6b8da-115">The service has a single method with no return type because it uses the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="6b8da-116">A interface de retorno de chamada</span><span class="sxs-lookup"><span data-stu-id="6b8da-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="6b8da-117">Você pode encontrar as implementações dessas interfaces na solução, juntamente com dependências externas falsas para fornecer dados de teste.</span><span class="sxs-lookup"><span data-stu-id="6b8da-117">You can find the implementations of these interfaces in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6b8da-118">streaming de gRPC</span><span class="sxs-lookup"><span data-stu-id="6b8da-118">gRPC streaming</span></span>

<span data-ttu-id="6b8da-119">O processo de gRPC para lidar com dados em tempo real é diferente do processo do WCF.</span><span class="sxs-lookup"><span data-stu-id="6b8da-119">The gRPC process for handling real-time data is different from the WCF process.</span></span> <span data-ttu-id="6b8da-120">Uma chamada do cliente para o servidor pode criar um fluxo persistente, que pode ser monitorado para mensagens que chegam de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="6b8da-120">A call from client to server can create a persistent stream, which can be monitored for messages that arrive asynchronously.</span></span> <span data-ttu-id="6b8da-121">Apesar da diferença, os fluxos podem ser uma maneira mais intuitiva de lidar com esses dados e são mais relevantes na programação moderna, o que enfatiza os fluxos do LINQ, reativos, a programação funcional e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6b8da-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming, which emphasizes LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="6b8da-122">A definição de serviço precisa de duas mensagens: uma para a solicitação e outra para o fluxo.</span><span class="sxs-lookup"><span data-stu-id="6b8da-122">The service definition needs two messages: one for the request and one for the stream.</span></span> <span data-ttu-id="6b8da-123">O serviço retorna um fluxo da `StockTickerUpdate` mensagem com a `stream` palavra-chave em sua `return` declaração.</span><span class="sxs-lookup"><span data-stu-id="6b8da-123">The service returns a stream of the `StockTickerUpdate` message with the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="6b8da-124">Recomendamos que você adicione um `Timestamp` à atualização para mostrar a hora exata da alteração de preço.</span><span class="sxs-lookup"><span data-stu-id="6b8da-124">We recommend that you add a `Timestamp` to the update to show the exact time of the price change.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="6b8da-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="6b8da-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-simplestockticker"></a><span data-ttu-id="6b8da-126">Implementar SimpleStockTicker</span><span class="sxs-lookup"><span data-stu-id="6b8da-126">Implement SimpleStockTicker</span></span>

<span data-ttu-id="6b8da-127">Reutilize a falsificação `StockPriceSubscriber` do projeto do WCF copiando as três classes da `TraderSys.StockMarket` biblioteca de classes para uma nova biblioteca de classes .net Standard na solução de destino.</span><span class="sxs-lookup"><span data-stu-id="6b8da-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="6b8da-128">Para seguir melhor as práticas recomendadas, adicione um `Factory` tipo para criar instâncias dele e registre o `IStockPriceSubscriberFactory` com os serviços de injeção de dependência ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b8da-128">To better follow best practices, add a `Factory` type to create instances of it, and register the `IStockPriceSubscriberFactory` with the ASP.NET Core dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="6b8da-129">A implementação de fábrica</span><span class="sxs-lookup"><span data-stu-id="6b8da-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="register-the-factory"></a><span data-ttu-id="6b8da-130">Registrar a fábrica</span><span class="sxs-lookup"><span data-stu-id="6b8da-130">Register the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="6b8da-131">Essa classe agora pode ser usada para implementar o gRPC `StockTickerService` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-131">This class can now be used to implement the gRPC `StockTickerService`.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="6b8da-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="6b8da-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors caused by broken connection, etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="6b8da-133">Como você pode ver, embora a declaração no `.proto` arquivo diga que o método retorna um fluxo de `StockTickerUpdate` mensagens, ele realmente retorna um `Task` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-133">As you can see, although the declaration in the `.proto` file says the method returns a stream of `StockTickerUpdate` messages, it actually returns a `Task`.</span></span> <span data-ttu-id="6b8da-134">O trabalho de criar o fluxo é tratado pelo código gerado e pelas bibliotecas de tempo de execução gRPC, que fornecem o `IServerStreamWriter<StockTickerUpdate>` fluxo de resposta, pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="6b8da-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="6b8da-135">Ao contrário de um serviço do WCF duplex, em que a instância da classe de serviço é mantida ativa enquanto a conexão está aberta, o serviço gRPC usa a tarefa retornada para manter o serviço ativo.</span><span class="sxs-lookup"><span data-stu-id="6b8da-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned task to keep the service alive.</span></span> <span data-ttu-id="6b8da-136">A tarefa não deve ser concluída até que a conexão seja fechada.</span><span class="sxs-lookup"><span data-stu-id="6b8da-136">The task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="6b8da-137">O serviço pode informar quando o cliente fechou a conexão usando o `CancellationToken` do `ServerCallContext` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="6b8da-138">Um método estático simples, `AwaitCancellation` , é usado para criar uma tarefa que é concluída quando o token é cancelado.</span><span class="sxs-lookup"><span data-stu-id="6b8da-138">A simple static method, `AwaitCancellation`, is used to create a task that completes when the token is canceled.</span></span>

<span data-ttu-id="6b8da-139">No `Subscribe` método, em seguida, obtenha um `StockPriceSubscriber` e adicione um manipulador de eventos que grava no fluxo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6b8da-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="6b8da-140">Em seguida, aguarde até que a conexão seja fechada antes de descartar imediatamente o `subscriber` para impedir que ele tente gravar dados no fluxo fechado.</span><span class="sxs-lookup"><span data-stu-id="6b8da-140">Then wait for the connection to be closed before immediately disposing the `subscriber` to prevent it from trying to write data to the closed stream.</span></span>

<span data-ttu-id="6b8da-141">O `WriteUpdateAsync` método tem um `try` / `catch` bloco para tratar quaisquer erros que possam ocorrer quando uma mensagem é gravada no fluxo.</span><span class="sxs-lookup"><span data-stu-id="6b8da-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when a message is written to the stream.</span></span> <span data-ttu-id="6b8da-142">Essa consideração é importante em conexões persistentes em redes, que podem ser quebradas a qualquer milissegundo, intencionalmente ou devido a uma falha em algum lugar.</span><span class="sxs-lookup"><span data-stu-id="6b8da-142">This consideration is important in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="use-stocktickerservice-from-a-client-application"></a><span data-ttu-id="6b8da-143">Usar o StockTickerService de um aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="6b8da-143">Use StockTickerService from a client application</span></span>

<span data-ttu-id="6b8da-144">Siga as mesmas etapas na seção anterior para criar uma biblioteca de classes de cliente compartilhável a partir do `.proto` arquivo.</span><span class="sxs-lookup"><span data-stu-id="6b8da-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="6b8da-145">No exemplo, há um aplicativo de console .NET que demonstra como usar o cliente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-145">In the sample, there's a .NET console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="6b8da-146">Exemplo de Program.cs</span><span class="sxs-lookup"><span data-stu-id="6b8da-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="6b8da-147">Nesse caso, o `Subscribe` método no cliente gerado não é assíncrono.</span><span class="sxs-lookup"><span data-stu-id="6b8da-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="6b8da-148">O fluxo é criado e utilizável imediatamente porque seu `MoveNext` método é assíncrono e a primeira vez que ele é chamado não é concluído até que a conexão esteja ativa.</span><span class="sxs-lookup"><span data-stu-id="6b8da-148">The stream is created and usable right away because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="6b8da-149">O fluxo é passado para um `DisplayAsync` método assíncrono.</span><span class="sxs-lookup"><span data-stu-id="6b8da-149">The stream is passed to an asynchronous `DisplayAsync` method.</span></span> <span data-ttu-id="6b8da-150">Em seguida, o aplicativo aguarda que o usuário pressione uma tecla e, em seguida, cancela o `DisplayAsync` método e aguarda a conclusão da tarefa antes de sair.</span><span class="sxs-lookup"><span data-stu-id="6b8da-150">The application then waits for the user to press a key, and then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="6b8da-151">Esse código usa a nova sintaxe de `using` declaração C# 8 para descartar o fluxo e o canal quando o `Main` método é encerrado.</span><span class="sxs-lookup"><span data-stu-id="6b8da-151">This code uses the new C# 8 `using` declaration syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="6b8da-152">É uma pequena alteração, mas uma boa que reduz recuos e linhas vazias.</span><span class="sxs-lookup"><span data-stu-id="6b8da-152">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="6b8da-153">Consumir o fluxo</span><span class="sxs-lookup"><span data-stu-id="6b8da-153">Consume the stream</span></span>

<span data-ttu-id="6b8da-154">O WCF usa interfaces de retorno de chamada para permitir que o servidor Chame métodos diretamente no cliente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-154">WCF uses callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="6b8da-155">os fluxos de gRPC funcionam de maneira diferente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-155">gRPC streams work differently.</span></span> <span data-ttu-id="6b8da-156">O cliente itera sobre o fluxo retornado e processa as mensagens, assim como se elas fossem retornadas de um método local que retorna um `IEnumerable` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-156">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="6b8da-157">O `IAsyncStreamReader<T>` tipo funciona de forma muito semelhante a um `IEnumerator<T>` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-157">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`.</span></span> <span data-ttu-id="6b8da-158">Há um `MoveNext` método que retorna true, desde que haja mais dados e uma `Current` propriedade que retorne o valor mais recente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-158">There's a `MoveNext` method that returns true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="6b8da-159">A única diferença é que o `MoveNext` método retorna um `Task<bool>` em vez de apenas um `bool` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-159">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="6b8da-160">O `ReadAllAsync` método de extensão encapsula o fluxo em um C# 8 padrão `IAsyncEnumerable` que pode ser usado com a nova `await foreach` sintaxe.</span><span class="sxs-lookup"><span data-stu-id="6b8da-160">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="6b8da-161">Para os desenvolvedores que usam padrões de programação reativos, a seção sobre [bibliotecas de cliente](client-libraries.md#iobservable) no final deste capítulo mostra como adicionar um método e classes de extensão para encapsular `IAsyncStreamReader<T>` um `IObservable<T>` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-161">For developers using reactive programming patterns, the section on [client libraries](client-libraries.md#iobservable) at the end of this chapter shows how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>`.</span></span>

<span data-ttu-id="6b8da-162">Novamente, certifique-se de capturar exceções aqui devido à possibilidade de falha de rede e, por <xref:System.OperationCanceledException> isso, isso será inevitavelmente gerado porque o código está usando um <xref:System.Threading.CancellationToken> para interromper o loop.</span><span class="sxs-lookup"><span data-stu-id="6b8da-162">Again, be sure to catch exceptions here because of the possibility of network failure, and because of the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="6b8da-163">O `RpcException` tipo tem muitas informações úteis sobre erros de tempo de execução gRPC, incluindo o `StatusCode` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-163">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="6b8da-164">Para obter mais informações, consulte [ *tratamento de erros* no capítulo 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="6b8da-164">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="6b8da-165">Streaming bidirecional</span><span class="sxs-lookup"><span data-stu-id="6b8da-165">Bidirectional streaming</span></span>

<span data-ttu-id="6b8da-166">Um serviço do WCF Full-duplex permite mensagens assíncronas e em tempo real em ambas as direções.</span><span class="sxs-lookup"><span data-stu-id="6b8da-166">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="6b8da-167">No exemplo de transmissão de servidor, o cliente inicia uma solicitação e recebe um fluxo de atualizações.</span><span class="sxs-lookup"><span data-stu-id="6b8da-167">In the server streaming example, the client starts a request and then receives a stream of updates.</span></span> <span data-ttu-id="6b8da-168">Uma versão melhor desse serviço permitiria que o cliente adicionasse e removesse ações da lista sem precisar parar e criar uma nova assinatura.</span><span class="sxs-lookup"><span data-stu-id="6b8da-168">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="6b8da-169">Essa funcionalidade foi implementada na [solução de exemplo FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="6b8da-169">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="6b8da-170">A `IFullStockTickerService` interface fornece três métodos:</span><span class="sxs-lookup"><span data-stu-id="6b8da-170">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="6b8da-171">`Subscribe` inicia a conexão.</span><span class="sxs-lookup"><span data-stu-id="6b8da-171">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="6b8da-172">`AddSymbol` Adiciona um símbolo de ação a ser observado.</span><span class="sxs-lookup"><span data-stu-id="6b8da-172">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="6b8da-173">`RemoveSymbol` Remove um símbolo da lista observada.</span><span class="sxs-lookup"><span data-stu-id="6b8da-173">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="6b8da-174">A interface de retorno de chamada permanece a mesma.</span><span class="sxs-lookup"><span data-stu-id="6b8da-174">The callback interface remains the same.</span></span>

<span data-ttu-id="6b8da-175">A implementação desse padrão no gRPC é menos simples porque agora há dois fluxos de dados com mensagens sendo passadas: um do cliente para o servidor e outro do servidor para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-175">Implementing this pattern in gRPC is less straightforward because there are now two streams of data with messages being passed: one from client to server and another from server to client.</span></span> <span data-ttu-id="6b8da-176">Não é possível usar vários métodos para implementar as operações adicionar e remover, mas você pode passar mais de um tipo de mensagem em um único fluxo usando o `Any` tipo ou a `oneof` palavra-chave, que foram abordadas no [capítulo 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="6b8da-176">It isn't possible to use multiple methods to implement the add and remove operations, but you can pass more than one type of message on a single stream by using either the `Any` type or the `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="6b8da-177">Em um caso em que há um conjunto específico de tipos que são aceitáveis, `oneof` é uma maneira melhor de começar.</span><span class="sxs-lookup"><span data-stu-id="6b8da-177">In a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="6b8da-178">Use um `ActionMessage` que possa conter um `AddSymbolRequest` ou um `RemoveSymbolRequest` :</span><span class="sxs-lookup"><span data-stu-id="6b8da-178">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`:</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="6b8da-179">Declare um serviço de streaming bidirecional que usa um fluxo de `ActionMessage` mensagens:</span><span class="sxs-lookup"><span data-stu-id="6b8da-179">Declare a bidirectional streaming service that takes a stream of `ActionMessage` messages:</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="6b8da-180">A implementação para esse serviço é semelhante à do exemplo anterior, exceto que o primeiro parâmetro do `Subscribe` método agora é um `IAsyncStreamReader<ActionMessage>` , que pode ser usado para lidar com as `Add` solicitações e `Remove` :</span><span class="sxs-lookup"><span data-stu-id="6b8da-180">The implementation for this service is similar to that of the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests:</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors caused by broken connection, etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="6b8da-181">A `ActionMessage` classe que o gRPC gerou garante que apenas uma das `Add` Propriedades e `Remove` pode ser definida.</span><span class="sxs-lookup"><span data-stu-id="6b8da-181">The `ActionMessage` class that gRPC has generated guarantees that only one of the `Add` and `Remove` properties can be set.</span></span> <span data-ttu-id="6b8da-182">Descobrir qual deles não `null` é uma maneira válida de determinar qual tipo de mensagem é usado, mas há uma maneira melhor.</span><span class="sxs-lookup"><span data-stu-id="6b8da-182">Finding which one isn't `null` is a valid way to determine which type of message is used, but there's a better way.</span></span> <span data-ttu-id="6b8da-183">A geração de código também criou um `enum ActionOneOfCase` na `ActionMessage` classe, que tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="6b8da-183">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="6b8da-184">A propriedade `ActionCase` no `ActionMessage` objeto pode ser usada com uma `switch` instrução para determinar qual campo está definido:</span><span class="sxs-lookup"><span data-stu-id="6b8da-184">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set:</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="6b8da-185">A `switch` instrução tem um `default` caso que registra um aviso caso encontre um valor desconhecido `ActionOneOfCase` .</span><span class="sxs-lookup"><span data-stu-id="6b8da-185">The `switch` statement has a `default` case that logs a warning if it encounters an unknown `ActionOneOfCase` value.</span></span> <span data-ttu-id="6b8da-186">Isso pode ser útil para indicar que um cliente está usando uma versão posterior do `.proto` arquivo que adicionou mais ações.</span><span class="sxs-lookup"><span data-stu-id="6b8da-186">This could be useful to indicate that a client is using a later version of the `.proto` file that has added more actions.</span></span> <span data-ttu-id="6b8da-187">Essa é uma razão pela qual o uso de um `switch` é melhor do que o teste `null` em campos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="6b8da-187">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="6b8da-188">Usar o FullStockTickerService de um aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="6b8da-188">Use FullStockTickerService from a client application</span></span>

<span data-ttu-id="6b8da-189">Há um aplicativo .NET WPF simples que demonstra o uso desse cliente mais complexo.</span><span class="sxs-lookup"><span data-stu-id="6b8da-189">There's a simple .NET WPF application that demonstrates the use of this more complex client.</span></span> <span data-ttu-id="6b8da-190">Você pode encontrar o aplicativo completo no [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="6b8da-190">You can find the full application on [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="6b8da-191">O cliente é usado na `MainWindowViewModel` classe, que obtém uma instância do `FullStockTicker.FullStockTickerClient` tipo de injeção de dependência:</span><span class="sxs-lookup"><span data-stu-id="6b8da-191">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection:</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="6b8da-192">O objeto retornado pelo `client.Subscribe()` método agora é uma instância do tipo de biblioteca gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>` , que fornece um `RequestStream` para enviar solicitações ao servidor e um para lidar com as `ResponseStream` respostas.</span><span class="sxs-lookup"><span data-stu-id="6b8da-192">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="6b8da-193">O fluxo de solicitação é usado de alguns `ICommand` métodos do WPF para adicionar e remover símbolos.</span><span class="sxs-lookup"><span data-stu-id="6b8da-193">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="6b8da-194">Para cada operação, defina o campo relevante em um `ActionMessage` objeto:</span><span class="sxs-lookup"><span data-stu-id="6b8da-194">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="6b8da-195">Definir o `oneof` valor de um campo em uma mensagem limpa automaticamente todos os campos que foram definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-195">Setting a `oneof` field's value on a message automatically clears any fields that have been set previously.</span></span>

<span data-ttu-id="6b8da-196">O fluxo de respostas é tratado em um `async` método.</span><span class="sxs-lookup"><span data-stu-id="6b8da-196">The stream of responses is handled in an `async` method.</span></span> <span data-ttu-id="6b8da-197">O `Task` retorno de ti é mantido para ser Descartado quando a janela é fechada:</span><span class="sxs-lookup"><span data-stu-id="6b8da-197">The `Task` it returns is held to be disposed when the window is closed:</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-cleanup"></a><span data-ttu-id="6b8da-198">Limpeza do cliente</span><span class="sxs-lookup"><span data-stu-id="6b8da-198">Client cleanup</span></span>

<span data-ttu-id="6b8da-199">Quando a janela é fechada e o `MainWindowViewModel` é Descartado (do `Closed` evento de `MainWindow` ), é recomendável descartar o `AsyncDuplexStreamingCall` objeto corretamente.</span><span class="sxs-lookup"><span data-stu-id="6b8da-199">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), we recommend that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="6b8da-200">Em particular, o `CompleteAsync` método no `RequestStream` deve ser chamado para fechar o fluxo normalmente no servidor.</span><span class="sxs-lookup"><span data-stu-id="6b8da-200">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="6b8da-201">Este exemplo mostra o `DisposeAsync` método do modelo de exibição de exemplo:</span><span class="sxs-lookup"><span data-stu-id="6b8da-201">This example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="6b8da-202">O fechamento de fluxos de solicitação permite que o servidor descarte seus próprios recursos em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="6b8da-202">Closing request streams enables the server to dispose of its own resources in a timely way.</span></span> <span data-ttu-id="6b8da-203">Isso melhora a eficiência e a escalabilidade dos serviços e impede exceções.</span><span class="sxs-lookup"><span data-stu-id="6b8da-203">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6b8da-204">[Anterior](migrate-request-reply.md) 
> [Avançar](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="6b8da-204">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
