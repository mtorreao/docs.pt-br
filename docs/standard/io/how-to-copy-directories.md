---
title: Como copiar diretórios
description: Consulte como copiar diretórios usando classes de e/s que copiam de forma síncrona o conteúdo de um diretório para outro local.
ms.date: 12/27/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: b81723b9ed7067826692e8383bf64058d4295f0c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830825"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="45c98-103">Como copiar diretórios</span><span class="sxs-lookup"><span data-stu-id="45c98-103">How to: Copy directories</span></span>

<span data-ttu-id="45c98-104">Este artigo demonstra como usar as classes de e/s para copiar de forma síncrona o conteúdo de um diretório para outro local.</span><span class="sxs-lookup"><span data-stu-id="45c98-104">This article demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="45c98-105">Para obter um exemplo de cópia assíncrona de arquivo, confira [E/S assíncrona de arquivo](asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="45c98-105">For an example of asynchronous file copy, see [Asynchronous file I/O](asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="45c98-106">Este exemplo copia os subdiretórios definindo o `copySubDirs` do método `DirectoryCopy` como `true`.</span><span class="sxs-lookup"><span data-stu-id="45c98-106">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="45c98-107">O método `DirectoryCopy` copia os subdiretórios recursivamente chamando a si próprio em cada subdiretório até não existir nada mais para copiar.</span><span class="sxs-lookup"><span data-stu-id="45c98-107">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c98-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="45c98-108">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="45c98-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="45c98-109">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="45c98-110">Arquivo e e/s de fluxo</span><span class="sxs-lookup"><span data-stu-id="45c98-110">File and stream I/O</span></span>](index.md)
- [<span data-ttu-id="45c98-111">Tarefas comuns de E/S</span><span class="sxs-lookup"><span data-stu-id="45c98-111">Common I/O tasks</span></span>](common-i-o-tasks.md)
- [<span data-ttu-id="45c98-112">E/S de arquivo assíncrona</span><span class="sxs-lookup"><span data-stu-id="45c98-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)
