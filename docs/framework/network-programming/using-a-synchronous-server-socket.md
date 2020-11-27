---
title: Usando um soquete de servidor síncrono
description: Este exemplo mostra um soquete de servidor síncrono no .NET Framework, que suspende um aplicativo até que uma solicitação de conexão seja recebida no soquete.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 305feaa71304bef749f999a078b0b5f4fa7be3cc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278148"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="55629-103">Usando um soquete de servidor síncrono</span><span class="sxs-lookup"><span data-stu-id="55629-103">Using a Synchronous Server Socket</span></span>

<span data-ttu-id="55629-104">Os soquetes de servidor síncrono suspendem a execução do aplicativo até que uma solicitação de conexão seja recebida no soquete.</span><span class="sxs-lookup"><span data-stu-id="55629-104">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="55629-105">Os soquetes de servidor síncrono não são adequados para aplicativos que fazem uso intenso da rede em sua operação, mas podem ser adequados para aplicativos de rede simples.</span><span class="sxs-lookup"><span data-stu-id="55629-105">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="55629-106">Depois que um <xref:System.Net.Sockets.Socket> for definido para escutar em um ponto de extremidade usando os métodos <xref:System.Net.Sockets.Socket.Bind%2A> e <xref:System.Net.Sockets.Socket.Listen%2A>, ele estará pronto para aceitar solicitações de conexão de entrada usando o método <xref:System.Net.Sockets.Socket.Accept%2A>.</span><span class="sxs-lookup"><span data-stu-id="55629-106">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="55629-107">O aplicativo é suspenso até que uma solicitação de conexão seja recebida quando o método **Accept** é chamado.</span><span class="sxs-lookup"><span data-stu-id="55629-107">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="55629-108">Quando uma solicitação de conexão é recebida, **Accept** retorna uma nova instância de **Socket** associada ao cliente que se conecta.</span><span class="sxs-lookup"><span data-stu-id="55629-108">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="55629-109">O exemplo a seguir lê os dados do cliente, exibe-os no console e retorna os dados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="55629-109">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="55629-110">O **soquete** não especifica nenhum protocolo de mensagens, portanto, a cadeia de caracteres " \<EOF> " marca o final dos dados da mensagem.</span><span class="sxs-lookup"><span data-stu-id="55629-110">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="55629-111">Ele supõe que um **Socket** chamado `listener` foi inicializado e associado a um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="55629-111">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="55629-112">Veja também</span><span class="sxs-lookup"><span data-stu-id="55629-112">See also</span></span>

- [<span data-ttu-id="55629-113">Usando um soquete de servidor assíncrono</span><span class="sxs-lookup"><span data-stu-id="55629-113">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="55629-114">Exemplo de soquete de servidor síncrono</span><span class="sxs-lookup"><span data-stu-id="55629-114">Synchronous Server Socket Example</span></span>](synchronous-server-socket-example.md)
- [<span data-ttu-id="55629-115">Escutando com soquetes</span><span class="sxs-lookup"><span data-stu-id="55629-115">Listening with Sockets</span></span>](listening-with-sockets.md)
