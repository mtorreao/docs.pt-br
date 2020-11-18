---
title: Interoperabilidade de exceções
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830617"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Trabalhando com exceções de interoperabilidade em código não gerenciado

A interoperabilidade de exceção de código não gerenciado tem suporte apenas em plataformas Windows. Os problemas de portabilidade surgem em plataformas que não são do Windows. Como a ABI do Unix não tem nenhuma definição para tratamento de exceções, o código gerenciado não sabe como os mecanismos de exceção funcionam nos bastidores. Portanto, as exceções podem acabar resultando em comportamentos imprevisíveis e falhas.

## <a name="setjmplongjmp-behaviors"></a>Comportamentos de setjmp/longjmp

`setjmp` `longjmp` Não há suporte para as funções Interop com e C. Não é possível usar o `longjmp` para ignorar os quadros gerenciados.

Para obter mais informações, consulte a [documentação do longjmp](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Confira também

- [Exceções](index.md)
- [Interoperabilidade com bibliotecas nativas](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
