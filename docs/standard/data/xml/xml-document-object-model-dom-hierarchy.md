---
title: Hierarquia DOM (Document Object Model) XML
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 2a8bbd4f7cb3feb2a555af9862632a2fa493be32
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819247"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="20fc0-102">Hierarquia DOM (Document Object Model) XML</span><span class="sxs-lookup"><span data-stu-id="20fc0-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="20fc0-103">A ilustração a seguir mostra a hierarquia de classes para o DOM (Document Object Model) XML, com o nome do World Wide Web Consortium (W3C) entre parênteses junto com o nome da classe onde é relevante.</span><span class="sxs-lookup"><span data-stu-id="20fc0-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="20fc0-104">![Modelo de Objeto do Documento XML &#40;hierarquia de&#41; DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="20fc0-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="20fc0-105">Hierarquia DOM (Document Object Model) XML</span><span class="sxs-lookup"><span data-stu-id="20fc0-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="20fc0-106">As seguintes classes não herdam de **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="20fc0-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="20fc0-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="20fc0-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="20fc0-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="20fc0-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="20fc0-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="20fc0-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="20fc0-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="20fc0-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="20fc0-111">A classe **XmlImplementation** é usada para criar um documento XML.</span><span class="sxs-lookup"><span data-stu-id="20fc0-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="20fc0-112">Para saber mais, confira [Criação de documento XML](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="20fc0-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="20fc0-113">A classe **XmlNamedNodeMap** manipula um conjunto não ordenado de nós.</span><span class="sxs-lookup"><span data-stu-id="20fc0-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="20fc0-114">Para saber mais, confira [Recuperação não ordenada de nós por nome ou índice](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="20fc0-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="20fc0-115">A classe **XmlNodeList** manipula uma lista ordenada de nós.</span><span class="sxs-lookup"><span data-stu-id="20fc0-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="20fc0-116">Para saber mais, confira [Recuperação ordenada de nós por índice](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="20fc0-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="20fc0-117">A classe **XmlNodeChangedEventArgs** manipula os manipuladores de eventos registrados em **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="20fc0-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="20fc0-118">Para saber mais, confira [Manipulação de eventos em um documento XML usando XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="20fc0-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="20fc0-119">A classe **XmlLinkedNode** herda de **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="20fc0-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="20fc0-120">Sua finalidade é substituir dois métodos de **XmlNode**: os métodos **PreviousSibling** e **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="20fc0-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="20fc0-121">Esses métodos substituídos são então herdados e usados por **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, que são classes que têm irmãos anteriores e seguintes.</span><span class="sxs-lookup"><span data-stu-id="20fc0-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20fc0-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="20fc0-122">See also</span></span>

- [<span data-ttu-id="20fc0-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="20fc0-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
