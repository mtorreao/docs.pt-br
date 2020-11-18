---
title: 'Como: percorrer uma árvore binária com tarefas paralelas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: ca70021c7d071abe480cb4ed866e34f171cc3b45
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825527"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="25700-102">Como: percorrer uma árvore binária com tarefas paralelas</span><span class="sxs-lookup"><span data-stu-id="25700-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="25700-103">O exemplo a seguir mostra duas maneiras pelas quais tarefas paralelas podem ser usadas para percorrer uma estrutura de dados de árvore.</span><span class="sxs-lookup"><span data-stu-id="25700-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="25700-104">A criação da árvore em si permanece como um exercício.</span><span class="sxs-lookup"><span data-stu-id="25700-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25700-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25700-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="25700-106">Os dois métodos mostrados são funcionalmente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="25700-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="25700-107">Usando o método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> para criar e executar as tarefas, você obter um identificador de tarefas que pode ser usado para aguardar as tarefas e manipular exceções.</span><span class="sxs-lookup"><span data-stu-id="25700-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25700-108">Confira também</span><span class="sxs-lookup"><span data-stu-id="25700-108">See also</span></span>

- [<span data-ttu-id="25700-109">Biblioteca de tarefas paralelas (TPL)</span><span class="sxs-lookup"><span data-stu-id="25700-109">Task Parallel Library (TPL)</span></span>](task-parallel-library-tpl.md)
