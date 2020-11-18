---
title: Lendo um documento XML no DOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
ms.openlocfilehash: 40efccba86f1bca8af838961dccdc7f98f8c93c2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820391"
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="8c205-102">Lendo um documento XML no DOM</span><span class="sxs-lookup"><span data-stu-id="8c205-102">Reading an XML Document into the DOM</span></span>
<span data-ttu-id="8c205-103">As informações XML são lidas na memória em diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="8c205-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="8c205-104">Podem ser lidas de uma cadeia de caracteres, de um fluxo, de uma URL, de um leitor de texto ou de uma classe derivada de <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8c205-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="8c205-105">O método <xref:System.Xml.XmlDocument.Load%2A> leva o documento para a memória e tem métodos sobrecarregados disponíveis para utilizar dados de cada um dos diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="8c205-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="8c205-106">Existe também um método <xref:System.Xml.XmlDocument.LoadXml%2A> que lê XML de uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="8c205-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="8c205-107">Diferentes métodos de <xref:System.Xml.XmlDocument.Load%2A> afetam os nós que são criados quando o DOM (Document Object Model) é carregado.</span><span class="sxs-lookup"><span data-stu-id="8c205-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="8c205-108">A tabela a seguir lista as diferenças entre alguns dos métodos de <xref:System.Xml.XmlDocument.Load%2A> e os tópicos que os abordam.</span><span class="sxs-lookup"><span data-stu-id="8c205-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="8c205-109">Assunto</span><span class="sxs-lookup"><span data-stu-id="8c205-109">Subject</span></span>|<span data-ttu-id="8c205-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="8c205-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="8c205-111">Criação de nós de espaços em branco</span><span class="sxs-lookup"><span data-stu-id="8c205-111">Creation of white space nodes</span></span>|<span data-ttu-id="8c205-112">O objeto usado para carregar o DOM tem um efeito no espaço em branco e nos nós de espaço em branco significativos gerados no DOM.</span><span class="sxs-lookup"><span data-stu-id="8c205-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="8c205-113">Para saber mais, confira [Espaço em branco e tratamento de espaço em branco significativo ao carregar o DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="8c205-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="8c205-114">Carregando o XML a partir de um nó específico ou carregando todo o documento XML</span><span class="sxs-lookup"><span data-stu-id="8c205-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="8c205-115">Ao usar o método <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType>, os dados podem ser carregados de um nó específico no DOM.</span><span class="sxs-lookup"><span data-stu-id="8c205-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="8c205-116">Confira mais informações em [Carregar dados de um leitor](load-data-from-a-reader.md).</span><span class="sxs-lookup"><span data-stu-id="8c205-116">For more information, see [Load Data from a Reader](load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="8c205-117">Validando o XML à medida que é carregado</span><span class="sxs-lookup"><span data-stu-id="8c205-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="8c205-118">Os dados XML carregados no DOM podem ser validados à medida que são carregados.</span><span class="sxs-lookup"><span data-stu-id="8c205-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="8c205-119">Isso é feito usando um <xref:System.Xml.XmlReader> de validação.</span><span class="sxs-lookup"><span data-stu-id="8c205-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8c205-120">Confira mais informações sobre como validar um XML quando ele é carregado em [Validando um documento XML no DOM](validating-an-xml-document-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="8c205-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="8c205-121">O exemplo a seguir mostra o XML que está sendo carregado com o método <xref:System.Xml.XmlDocument.LoadXml%2A> e os dados salvos subsequentemente em um arquivo de texto chamado `data.xml`.</span><span class="sxs-lookup"><span data-stu-id="8c205-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c205-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c205-122">See also</span></span>

- [<span data-ttu-id="8c205-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="8c205-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
