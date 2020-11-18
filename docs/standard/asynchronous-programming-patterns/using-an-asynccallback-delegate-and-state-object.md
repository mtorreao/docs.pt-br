---
title: Usando um delegado AsyncCallback e um objeto de estado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: 0a33c852d822e7d25d14ab17324459ec005853f9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829135"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="02eaf-102">Usando um delegado AsyncCallback e um objeto de estado</span><span class="sxs-lookup"><span data-stu-id="02eaf-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="02eaf-103">Ao usar um representante <xref:System.AsyncCallback> para processar os resultados da operação assíncrona em um thread separado, você pode usar um objeto de estado para passar informações entre os retornos de chamada e recuperar um resultado final.</span><span class="sxs-lookup"><span data-stu-id="02eaf-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="02eaf-104">Este tópico demonstra essa prática expandindo o exemplo em [Usando um representante AsyncCallback para finalizar uma operação assíncrona](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="02eaf-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02eaf-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="02eaf-105">Example</span></span>  
 <span data-ttu-id="02eaf-106">O exemplo de código a seguir demonstra como usar métodos assíncronos na classe <xref:System.Net.Dns> para recuperar informações do DNS (Sistema de Nomes de Domínio) de computadores especificados pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="02eaf-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="02eaf-107">Este exemplo define e usa a classe `HostRequest` para armazenar informações de estado.</span><span class="sxs-lookup"><span data-stu-id="02eaf-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="02eaf-108">Um objeto `HostRequest` é criado para cada nome de computador inserido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="02eaf-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="02eaf-109">Este objeto é passado para o método <xref:System.Net.Dns.BeginGetHostByName%2A>.</span><span class="sxs-lookup"><span data-stu-id="02eaf-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="02eaf-110">O método `ProcessDnsInformation` é chamado sempre que uma solicitação é concluída.</span><span class="sxs-lookup"><span data-stu-id="02eaf-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="02eaf-111">O objeto `HostRequest` é recuperado usando a propriedade <xref:System.IAsyncResult.AsyncState%2A>.</span><span class="sxs-lookup"><span data-stu-id="02eaf-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="02eaf-112">O método `ProcessDnsInformation` usa o objeto `HostRequest` para armazenar o retornado <xref:System.Net.IPHostEntry> pela solicitação ou um <xref:System.Net.Sockets.SocketException> lançado pela solicitação.</span><span class="sxs-lookup"><span data-stu-id="02eaf-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="02eaf-113">Quando todas as solicitações são concluídas, o aplicativo faz a iteração pelos objetos `HostRequest` e exibe as informações de DNS ou a mensagem de erro <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="02eaf-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="02eaf-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="02eaf-114">See also</span></span>

- [<span data-ttu-id="02eaf-115">Padrão assíncrono baseado em evento (EAP)</span><span class="sxs-lookup"><span data-stu-id="02eaf-115">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="02eaf-116">Visão geral do padrão assíncrono baseado em evento</span><span class="sxs-lookup"><span data-stu-id="02eaf-116">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="02eaf-117">Usando um delegado AsyncCallback para finalizar uma operação assíncrona</span><span class="sxs-lookup"><span data-stu-id="02eaf-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
