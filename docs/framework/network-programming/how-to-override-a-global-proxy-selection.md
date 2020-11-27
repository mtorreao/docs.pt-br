---
title: 'Como: Substituir uma seleção de proxy global'
description: Siga este exemplo para substituir a seleção de proxy global enviando uma WebRequest para uma URL, que substitui a seleção por um servidor proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265733"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="d7e87-103">Como: Substituir uma seleção de proxy global</span><span class="sxs-lookup"><span data-stu-id="d7e87-103">How to: Override a Global Proxy Selection</span></span>

<span data-ttu-id="d7e87-104">Este exemplo envia uma **WebRequest** para `www.contoso.com` que substitui a seleção de proxy global por um servidor proxy chamado `alternateproxy` na porta 80.</span><span class="sxs-lookup"><span data-stu-id="d7e87-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e87-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d7e87-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7e87-106">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="d7e87-106">Compiling the Code</span></span>  

 <span data-ttu-id="d7e87-107">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="d7e87-107">This example requires:</span></span>  
  
- <span data-ttu-id="d7e87-108">Uma [ `using` diretiva](../../csharp/language-reference/keywords/using-directive.md) para o namespace **System.net** .</span><span class="sxs-lookup"><span data-stu-id="d7e87-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e87-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="d7e87-109">See also</span></span>

- [<span data-ttu-id="d7e87-110">Usando protocolos de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d7e87-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="d7e87-111">Acessando a Internet por meio de um proxy</span><span class="sxs-lookup"><span data-stu-id="d7e87-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
