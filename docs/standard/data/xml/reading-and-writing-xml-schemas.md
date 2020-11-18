---
title: Lendo e gravando esquemas XML
description: Ler e gravar esquemas XSD (linguagem de definição de esquema XML) a partir de arquivos ou outras fontes no .NET, usando a API de SOM do esquema de objetos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: ae951efafd68d0ddf4f74876edd4c12564d68dde
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830877"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bb426-103">Lendo e gravando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bb426-103">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="bb426-104">A API do SOM (Schema Object Model) pode ser usada para ler e gravar esquemas XSD de arquivos ou de outras origens e criar esquemas XML na memória usando as classes no namespace <xref:System.Xml.Schema?displayProperty=nameWithType> que mapeiam para as estruturas definidas na Recomendação de esquema XML do W3C (World Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="bb426-104">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="bb426-105">Lendo e gravando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bb426-105">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="bb426-106">A classe <xref:System.Xml.Schema.XmlSchema> fornece os métodos <xref:System.Xml.Schema.XmlSchema.Read%2A> e <xref:System.Xml.Schema.XmlSchema.Write%2A> para ler e gravar esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="bb426-106">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="bb426-107">O método <xref:System.Xml.Schema.XmlSchema.Read%2A> retorna um objeto <xref:System.Xml.Schema.XmlSchema> que representa o esquema XML e utiliza um <xref:System.Xml.Schema.ValidationEventHandler> opcional como um parâmetro para tratar avisos e erros de validação de esquema encontrados ao ler um esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bb426-107">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="bb426-108">O método <xref:System.Xml.Schema.XmlSchema.Write%2A> grava esquemas XML nos objetos <xref:System.IO.Stream>, <xref:System.IO.TextWriter> e <xref:System.Xml.XmlWriter> e pode utilizar um objeto opcional <xref:System.Xml.XmlNamespaceManager> como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="bb426-108">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="bb426-109">Um <xref:System.Xml.XmlNamespaceManager> é usado para tratar namespaces encontrados em um esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bb426-109">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="bb426-110">Para saber mais sobre a classe <xref:System.Xml.XmlNamespaceManager>, confira [Gerenciando namespaces em um documento XML](managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="bb426-110">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="bb426-111">O exemplo de código a seguir ilustra esquemas XML de leitura e gravação de um arquivo e para um arquivo.</span><span class="sxs-lookup"><span data-stu-id="bb426-111">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="bb426-112">O exemplo de código utiliza o arquivo `example.xsd`, lê-o em um objeto <xref:System.Xml.Schema.XmlSchema> usando o método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> e, em seguida, grava o arquivo no console e em um novo arquivo `new.xsd`.</span><span class="sxs-lookup"><span data-stu-id="bb426-112">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="bb426-113">O exemplo de código também fornece <xref:System.Xml.Schema.ValidationEventHandler> como um parâmetro para o método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> para tratar todos os avisos ou erros de validação de esquema encontrados ao ler o esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bb426-113">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="bb426-114">Se o <xref:System.Xml.Schema.ValidationEventHandler> não for especificado (`null`), nenhum aviso ou erro será relatado.</span><span class="sxs-lookup"><span data-stu-id="bb426-114">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="bb426-115">O exemplo utiliza o arquivo `example.xsd` como entrada.</span><span class="sxs-lookup"><span data-stu-id="bb426-115">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb426-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="bb426-116">See also</span></span>

- [<span data-ttu-id="bb426-117">Visão geral do modelo de objeto de esquema XML</span><span class="sxs-lookup"><span data-stu-id="bb426-117">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="bb426-118">Compilando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bb426-118">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="bb426-119">Percorrer esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bb426-119">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="bb426-120">Esquemas XML de edição</span><span class="sxs-lookup"><span data-stu-id="bb426-120">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="bb426-121">Incluindo ou importando um esquema XML</span><span class="sxs-lookup"><span data-stu-id="bb426-121">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="bb426-122">XmlSchemaSet para compilação de esquema</span><span class="sxs-lookup"><span data-stu-id="bb426-122">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="bb426-123">Compilação Infoset de pré esquema</span><span class="sxs-lookup"><span data-stu-id="bb426-123">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
- [<span data-ttu-id="bb426-124">Gerenciando namespaces em um documento XML</span><span class="sxs-lookup"><span data-stu-id="bb426-124">Managing Namespaces in an XML Document</span></span>](managing-namespaces-in-an-xml-document.md)
