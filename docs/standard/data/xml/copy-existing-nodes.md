---
title: Copiar nós existentes
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: b4ae24f9776456033a876e8ae4d1515d2f669fe0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830942"
---
# <a name="copy-existing-nodes"></a>Copiar nós existentes
Há vários métodos e propriedades no modelo de objeto (DOM) de documento XML você pode usar para selecionar um nó, como **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**. Uma vez que o nó é selecionado, você pode inseri-lo na árvore usando um dos métodos de inserção que funcionam para esse tipo de nó específico. A única limitação para inserir um nó na árvore é que o documento ainda deve ser bem formado depois que o nó é inserido. Quando um nó existente é inserido na árvore DOM, é removido da sua posição original e adicionado à sua posição de destino.  
  
## <a name="see-also"></a>Confira também

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
