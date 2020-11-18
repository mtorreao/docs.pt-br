---
title: 'Como: encapsular padrões de EAP em uma tarefa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: 2d6788634fe03bed7a380184c0e954954e224aec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826678"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="0131b-102">Como: encapsular padrões de EAP em uma tarefa</span><span class="sxs-lookup"><span data-stu-id="0131b-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="0131b-103">O exemplo a seguir mostra como expor uma sequência arbitrária de operações de padrão assíncrono baseado em evento (EAP) como uma tarefa usando um <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span><span class="sxs-lookup"><span data-stu-id="0131b-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="0131b-104">O exemplo também mostra como usar um <xref:System.Threading.CancellationToken> para invocar os métodos de cancelamento internos nos objetos <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="0131b-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0131b-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0131b-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="0131b-106">Confira também</span><span class="sxs-lookup"><span data-stu-id="0131b-106">See also</span></span>

- [<span data-ttu-id="0131b-107">TPL e Programação Assíncrona do .NET Tradicional</span><span class="sxs-lookup"><span data-stu-id="0131b-107">TPL and Traditional .NET Asynchronous Programming</span></span>](tpl-and-traditional-async-programming.md)
