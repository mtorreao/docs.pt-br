---
title: Uso de System.XML
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: a01799bd130de0222d4d66dee4955375c1a1911f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828589"
---
# <a name="systemxml-usage"></a><span data-ttu-id="d0bd3-102">Uso de System.XML</span><span class="sxs-lookup"><span data-stu-id="d0bd3-102">System.Xml Usage</span></span>
<span data-ttu-id="d0bd3-103">Esta seção fala sobre o uso de vários tipos que residem em <xref:System.Xml?displayProperty=nameWithType> namespaces que podem ser usados para representar dados XML.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="d0bd3-104">❌ Não use <xref:System.Xml.XmlNode> ou <xref:System.Xml.XmlDocument> para representar dados XML.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="d0bd3-105">Favorecer o uso de instâncias de <xref:System.Xml.XPath.IXPathNavigable> , <xref:System.Xml.XmlReader> , <xref:System.Xml.XmlWriter> ou subtipos de <xref:System.Xml.Linq.XNode> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="d0bd3-106">`XmlNode` e `XmlDocument` não são projetados para exposição em APIs públicas.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="d0bd3-107">✔️ usar `XmlReader` , `IXPathNavigable` ou subtipos de `XNode` como entrada ou saída de membros que aceitam ou retornam XML.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="d0bd3-108">Use essas abstrações em vez de `XmlDocument` , `XmlNode` ou <xref:System.Xml.XPath.XPathDocument> , porque isso dissocia os métodos de implementações específicas de um documento XML na memória e permite que eles trabalhem com fontes de dados XML virtuais que expõem `XNode` , `XmlReader` ou <xref:System.Xml.XPath.XPathNavigator> .</span><span class="sxs-lookup"><span data-stu-id="d0bd3-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="d0bd3-109">❌ Não crie a subclasse `XmlDocument` se você quiser criar um tipo que represente uma exibição XML de um modelo de objeto subjacente ou fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d0bd3-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="d0bd3-110">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="d0bd3-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d0bd3-111">*Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d0bd3-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d0bd3-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="d0bd3-112">See also</span></span>

- [<span data-ttu-id="d0bd3-113">Diretrizes de design de estrutura</span><span class="sxs-lookup"><span data-stu-id="d0bd3-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d0bd3-114">Diretrizes de uso</span><span class="sxs-lookup"><span data-stu-id="d0bd3-114">Usage Guidelines</span></span>](usage-guidelines.md)
