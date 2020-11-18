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
# <a name="how-to-copy-directories"></a>Como copiar diretórios

Este artigo demonstra como usar as classes de e/s para copiar de forma síncrona o conteúdo de um diretório para outro local.

Para obter um exemplo de cópia assíncrona de arquivo, confira [E/S assíncrona de arquivo](asynchronous-file-i-o.md).

Este exemplo copia os subdiretórios definindo o `copySubDirs` do método `DirectoryCopy` como `true`. O método `DirectoryCopy` copia os subdiretórios recursivamente chamando a si próprio em cada subdiretório até não existir nada mais para copiar.  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Confira também

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [Arquivo e e/s de fluxo](index.md)
- [Tarefas comuns de E/S](common-i-o-tasks.md)
- [E/S de arquivo assíncrona](asynchronous-file-i-o.md)
