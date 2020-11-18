---
title: Removendo os nós DOM
ms.date: 03/30/2017
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: ecda49960f51d807730cb44b966aa2dfcada22d7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823700"
---
# <a name="removing-nodes-from-the-dom"></a>Removendo os nós DOM
Para remover um nó de (DOM) modelo de objeto de documento, use o método de <xref:System.Xml.XmlNode.RemoveChild%2A> para remover um nó específico. Quando você remove um nó, o método remove a subárvore que pertence ao nó que está sendo removido; isto é, se não é um nó folha.  
  
 Para remover os vários nós DOM, use o método de <xref:System.Xml.XmlNode.RemoveAll%2A> para remover todos os filhos e atributos, se aplicável, do nó atual.  
  
 Se você estiver trabalhando com <xref:System.Xml.XmlNamedNodeMap>, você pode remover um nó usando o método <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> .  
  
 Para remover os atributos, confira [Removendo os atributos de um nó no elemento DOM](removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
