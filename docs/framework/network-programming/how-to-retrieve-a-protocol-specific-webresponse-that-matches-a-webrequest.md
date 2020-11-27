---
title: 'Como: Recuperar uma WebResponse específica de protocolo que corresponde a uma WebRequest'
description: Saiba como recuperar um WebResponse específico de protocolo que corresponde a um WebRequest no .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fd163c115dcd19c05f93f4c202b043440834ba9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266734"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="21668-103">Como: Recuperar uma WebResponse específica de protocolo que corresponde a uma WebRequest</span><span class="sxs-lookup"><span data-stu-id="21668-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="21668-104">Esse exemplo mostra como recuperar uma WebResponse específica de protocolo que corresponde a uma WebRequest.</span><span class="sxs-lookup"><span data-stu-id="21668-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21668-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="21668-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21668-106">Compilando o código</span><span class="sxs-lookup"><span data-stu-id="21668-106">Compiling the Code</span></span>  

 <span data-ttu-id="21668-107">Este exemplo requer:</span><span class="sxs-lookup"><span data-stu-id="21668-107">This example requires:</span></span>  
  
- <span data-ttu-id="21668-108">Referências ao namespace **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="21668-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21668-109">Veja também</span><span class="sxs-lookup"><span data-stu-id="21668-109">See also</span></span>

- [<span data-ttu-id="21668-110">Solicitando dados</span><span class="sxs-lookup"><span data-stu-id="21668-110">Requesting Data</span></span>](requesting-data.md)
