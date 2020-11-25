---
title: Bloqueando a execução de aplicativos com um AsyncWaitHandle
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
ms.openlocfilehash: 1e7fc71ef5a4a44b2bb4c039305e06c157c65f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716155"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="270d5-102">Bloqueando a execução de aplicativos com um AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="270d5-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>

<span data-ttu-id="270d5-103">Aplicativos que não continuem a executar outras tarefas enquanto aguardam os resultados de uma operação assíncrona devem bloquear até que a operação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="270d5-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="270d5-104">Use uma das opções a seguir para bloquear o thread principal do aplicativo ao aguardar a conclusão de uma operação assíncrona:</span><span class="sxs-lookup"><span data-stu-id="270d5-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="270d5-105">Use a <xref:System.IAsyncResult.AsyncWaitHandle%2A> Propriedade do <xref:System.IAsyncResult> retornada pelo método **begin**_OperationName_ da operação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="270d5-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="270d5-106">Esta abordagem será demonstrada neste tópico.</span><span class="sxs-lookup"><span data-stu-id="270d5-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="270d5-107">Chame o método **End**_OperationName_ da operação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="270d5-107">Call the asynchronous operation's **End**_OperationName_ method.</span></span> <span data-ttu-id="270d5-108">Veja um exemplo que demonstra essa abordagem em [Bloqueando a execução de um aplicativo ao encerrar uma operação assíncrona](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="270d5-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="270d5-109">Aplicativos que usam um ou mais objetos <xref:System.Threading.WaitHandle> para bloquear até a conclusão de uma operação assíncrona, tipicamente chamam o método **Begin**_OperationName_, executam qualquer trabalho que possa ser feito sem os resultados da operação e, em seguida, bloqueiam até a conclusão das operações assíncronas.</span><span class="sxs-lookup"><span data-stu-id="270d5-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="270d5-110">Um aplicativo pode bloquear em uma única operação ao chamar um dos métodos <xref:System.Threading.WaitHandle.WaitOne%2A> usando o <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="270d5-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="270d5-111">Para bloquear enquanto espera a conclusão de um conjunto de operações assíncronas, armazene os objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> associados em uma matriz e chame um dos métodos <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="270d5-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="270d5-112">Para bloquear enquanto espera a conclusão de um conjunto de operações assíncronas, armazene os objetos <xref:System.IAsyncResult.AsyncWaitHandle%2A> associados em uma matriz e chame um dos métodos <xref:System.Threading.WaitHandle.WaitAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="270d5-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="270d5-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="270d5-113">Example</span></span>  

 <span data-ttu-id="270d5-114">O exemplo de código a seguir demonstra como usar métodos assíncronos na classe DNS para recuperar informações do Sistema de Nomes de Domínio de computadores especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="270d5-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="270d5-115">O exemplo demonstra o bloqueio usando o <xref:System.Threading.WaitHandle> associado com a operação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="270d5-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="270d5-116">Observe que `null` (`Nothing` no Visual Basic) é passado para os parâmetros <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` e `stateObject` por não serem necessários ao usar essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="270d5-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="270d5-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="270d5-117">See also</span></span>

- [<span data-ttu-id="270d5-118">Padrão assíncrono baseado em evento (EAP)</span><span class="sxs-lookup"><span data-stu-id="270d5-118">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="270d5-119">Visão geral do padrão assíncrono baseado em evento</span><span class="sxs-lookup"><span data-stu-id="270d5-119">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
