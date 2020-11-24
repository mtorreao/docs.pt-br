---
title: Referências a entidades são preservadas
ms.date: 03/30/2017
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
ms.openlocfilehash: 484eb5c874c6de05acae7dcd87a477c186b81482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687262"
---
# <a name="entity-references-are-preserved"></a>Referências a entidades são preservadas

Quando a referência de entidade não é expandida, mas é preservada, o modelo de objeto (DOM) de documento XML cria um nó de **XmlEntityReference** quando encontra uma referência de entidade.  
  
 Usando o seguinte XML,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 o DOM cria um nó **XmlEntityReference** quando encontra a referência `&publisher;`. **XmlEntityReference** contém os nós filho copiados de conteúdo na declaração de entidade. O exemplo de código anterior contém o texto na declaração de entidade. Assim, um nó **XmlText** é criado como o nó filho do nó de referência de entidade.  
  
 ![Estrutura de árvore para referências de entidade preservadas](media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Estrutura de árvore para as referências de entidade que são preservadas  
  
 Os nós filho de **XmlEntityReference** são cópias de todos os nós filho criados do nó **XmlEntity** quando a declaração de entidade foi encontrada.  
  
> [!NOTE]
> Os nós copiados de **XmlEntity** não são sempre cópias exatas quando colocados no nó de referência de entidade. Pode haver namespaces que estão no escopo no nó de referência de entidade, e que afetam a configuração final dos nós filho.  
  
 Por padrão, entidades gerais como `&abc;` são preservadas, e nós **XmlEntityReference** são sempre criados.  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
