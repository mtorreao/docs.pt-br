---
title: Processamento de Dados XML na memória
ms.date: 03/30/2017
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
ms.openlocfilehash: 878e008f5c7c3a018389e8666263269162989812
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686911"
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="a43d5-102">Processamento de Dados XML na memória</span><span class="sxs-lookup"><span data-stu-id="a43d5-102">Processing XML Data In-Memory</span></span>

<span data-ttu-id="a43d5-103">O Microsoft .NET Framework inclui três modelos para processar dados XML: as classes <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathDocument>, além de [LINQ to XML (C#)](../../linq/linq-xml-overview.md) e [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a43d5-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span></span>  
  
 <span data-ttu-id="a43d5-104">A classe <xref:System.Xml.XmlDocument> implementa o núcleo de nível 1 do DOM (Modelo de Objeto de Documento) do W3C e as recomendações de nível 2 do DOM principal.</span><span class="sxs-lookup"><span data-stu-id="a43d5-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="a43d5-105">O DOM é uma representação de árvore na memória (em cache) de um documento XML.</span><span class="sxs-lookup"><span data-stu-id="a43d5-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="a43d5-106">Com o <xref:System.Xml.XmlDocument> e suas classes relacionadas, você pode criar documentos XML, carregar e acessar dados, modificar dados e salvar alterações.</span><span class="sxs-lookup"><span data-stu-id="a43d5-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="a43d5-107">A classe <xref:System.Xml.XPath.XPathDocument> é um repositório de dados somente leitura e na memória que é baseado no modelo de dados XPath.</span><span class="sxs-lookup"><span data-stu-id="a43d5-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="a43d5-108">A classe <xref:System.Xml.XPath.XPathNavigator> oferece várias opções de edição e recursos de navegação usando um modelo de cursor em documentos XML contidos na classe <xref:System.Xml.XPath.XPathDocument> somente leitura bem como a classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a43d5-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="a43d5-109">[LINQ to XML](../../linq/linq-xml-overview.md) é um modelo introduzido no .NET Framework versão 3.5 para processar dados XML.</span><span class="sxs-lookup"><span data-stu-id="a43d5-109">[LINQ to XML](../../linq/linq-xml-overview.md) is a model introduced in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="a43d5-110">Ele é um modelo na memória que aproveita a [LINQ (consulta integrada à linguagem)](../../../csharp/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="a43d5-110">It's an in-memory model that leverages [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).</span></span> <span data-ttu-id="a43d5-111">O LINQ estende a sintaxe da linguagem C# e Visual Basic para fornecer novos recursos de consulta.</span><span class="sxs-lookup"><span data-stu-id="a43d5-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a43d5-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a43d5-112">In This Section</span></span>  

 [<span data-ttu-id="a43d5-113">Processar dados XML usando o modelo DOM</span><span class="sxs-lookup"><span data-stu-id="a43d5-113">Process XML Data Using the DOM Model</span></span>](process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="a43d5-114">Discute o uso <xref:System.Xml.XmlDocument> e suas classes relacionadas para processar dados XML.</span><span class="sxs-lookup"><span data-stu-id="a43d5-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="a43d5-115">Processar dados XML usando o modelo de dados XPath</span><span class="sxs-lookup"><span data-stu-id="a43d5-115">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="a43d5-116">Discute o uso das classes <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathNavigator> para processar dados XML.</span><span class="sxs-lookup"><span data-stu-id="a43d5-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="a43d5-117">Dados XML do processo usando LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a43d5-117">Process XML Data Using LINQ to XML</span></span>](process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="a43d5-118">Fornece uma visão geral do LINQ to XML e fornece links para a documentação do LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a43d5-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a43d5-119">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="a43d5-119">Related Sections</span></span>  

 [<span data-ttu-id="a43d5-120">Documentos e dados XML</span><span class="sxs-lookup"><span data-stu-id="a43d5-120">XML Documents and Data</span></span>](index.md)
