---
title: 'Como: abrir e anexar a um arquivo de log'
description: Abra e acrescente a um arquivo de log usando as classes StreamWriter e StreamReader no .NET, que gravam caracteres e lêem caracteres de fluxos.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: f92dd34b15ca79f229b365c7c2db4ace411d9353
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830747"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="aaf60-103">Como: abrir e anexar a um arquivo de log</span><span class="sxs-lookup"><span data-stu-id="aaf60-103">How to: Open and append to a log file</span></span>

<span data-ttu-id="aaf60-104"><xref:System.IO.StreamWriter> e <xref:System.IO.StreamReader> gravam caracteres e leem caracteres de fluxos.</span><span class="sxs-lookup"><span data-stu-id="aaf60-104"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="aaf60-105">O exemplo de código a seguir abre o arquivo *log.txt* para a entrada ou cria o arquivo caso ele ainda não exista e acrescenta informações de log ao final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="aaf60-105">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="aaf60-106">Em seguida, o exemplo grava o conteúdo do arquivo na saída padrão para exibição.</span><span class="sxs-lookup"><span data-stu-id="aaf60-106">The example then writes the contents of the file to standard output for display.</span></span>

<span data-ttu-id="aaf60-107">Como alternativa para esse exemplo, você pode armazenar as informações como uma única cadeia de caracteres ou uma matriz de cadeia de caracteres e usar o método <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> ou <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> para obter a mesma funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="aaf60-107">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aaf60-108">Os usuários do Visual Basic podem optar por usar os métodos e propriedades fornecidas pela classe <xref:Microsoft.VisualBasic.Logging.Log> ou pela classe <xref:Microsoft.VisualBasic.FileIO.FileSystem> para criar ou gravar em arquivos de log.</span><span class="sxs-lookup"><span data-stu-id="aaf60-108">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaf60-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="aaf60-109">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="aaf60-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="aaf60-110">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="aaf60-111">Como: enumerar diretórios e arquivos</span><span class="sxs-lookup"><span data-stu-id="aaf60-111">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="aaf60-112">Como: ler e gravar em um arquivo de dados recém-criado</span><span class="sxs-lookup"><span data-stu-id="aaf60-112">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="aaf60-113">Como: ler texto de um arquivo</span><span class="sxs-lookup"><span data-stu-id="aaf60-113">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="aaf60-114">Como: gravar texto em um arquivo</span><span class="sxs-lookup"><span data-stu-id="aaf60-114">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="aaf60-115">Como: ler caracteres de uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="aaf60-115">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="aaf60-116">Como: gravar caracteres em uma cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="aaf60-116">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="aaf60-117">Arquivo e e/s de fluxo</span><span class="sxs-lookup"><span data-stu-id="aaf60-117">File and stream I/O</span></span>](index.md)
