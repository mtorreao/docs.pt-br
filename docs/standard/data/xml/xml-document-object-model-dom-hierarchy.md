---
title: Hierarquia DOM (Document Object Model) XML
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 24ef51a18392fe3034e64bd585d879941fca4b95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718352"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Hierarquia DOM (Document Object Model) XML

A ilustração a seguir mostra a hierarquia de classes para o DOM (Document Object Model) XML, com o nome do World Wide Web Consortium (W3C) entre parênteses junto com o nome da classe onde é relevante.  
  
 ![Modelo de Objeto do Documento XML &#40;hierarquia de&#41; DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Hierarquia DOM (Document Object Model) XML  
  
 As seguintes classes não herdam de **XmlNode**:  
  
- **XmlImplementation**  
  
- **XmlNamedNodeMap**  
  
- **XmlNodeList**  
  
- **XmlNodeChangedEventArgs**  
  
 A classe **XmlImplementation** é usada para criar um documento XML. Para saber mais, confira [Criação de documento XML](xml-document-creation.md).  
  
 A classe **XmlNamedNodeMap** manipula um conjunto não ordenado de nós. Para saber mais, confira [Recuperação não ordenada de nós por nome ou índice](unordered-node-retrieval-by-name-or-index.md).  
  
 A classe **XmlNodeList** manipula uma lista ordenada de nós. Para saber mais, confira [Recuperação ordenada de nós por índice](ordered-node-retrieval-by-index.md).  
  
 A classe **XmlNodeChangedEventArgs** manipula os manipuladores de eventos registrados em **XmlDocument**. Para saber mais, confira [Manipulação de eventos em um documento XML usando XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 A classe **XmlLinkedNode** herda de **XmlNode**. Sua finalidade é substituir dois métodos de **XmlNode**: os métodos **PreviousSibling** e **NextSibling**. Esses métodos substituídos são então herdados e usados por **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, que são classes que têm irmãos anteriores e seguintes.  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
