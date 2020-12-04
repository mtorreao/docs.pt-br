---
title: Regras de documentação (análise de código)
description: Saiba mais sobre as regras de documentação da regra de análise de código
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96584812"
---
# <a name="documentation-rules"></a><span data-ttu-id="065b7-103">Regras de documentação</span><span class="sxs-lookup"><span data-stu-id="065b7-103">Documentation rules</span></span>

<span data-ttu-id="065b7-104">As regras de documentação dão suporte à gravação de bibliotecas bem documentadas por meio do uso correto de [comentários de documentação XML](../../../csharp/codedoc.md) para APIs visíveis externamente.</span><span class="sxs-lookup"><span data-stu-id="065b7-104">Documentation rules support writing well-documented libraries through the correct use of [XML documentation comments](../../../csharp/codedoc.md) for externally visible APIs.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="065b7-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="065b7-105">In this section</span></span>

| <span data-ttu-id="065b7-106">Regra</span><span class="sxs-lookup"><span data-stu-id="065b7-106">Rule</span></span> | <span data-ttu-id="065b7-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="065b7-107">Description</span></span> |
| - | - |
| [<span data-ttu-id="065b7-108">CA1200: Evitar o uso de marcas cref com um prefixo</span><span class="sxs-lookup"><span data-stu-id="065b7-108">CA1200: Avoid using cref tags with a prefix</span></span>](ca1200.md) | <span data-ttu-id="065b7-109">O atributo [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) em uma marca de documentação XML significa "referência de código".</span><span class="sxs-lookup"><span data-stu-id="065b7-109">The [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) attribute in an XML documentation tag means "code reference".</span></span> <span data-ttu-id="065b7-110">Ele especifica que o texto interno da marca é um elemento de código, como um tipo, método ou propriedade.</span><span class="sxs-lookup"><span data-stu-id="065b7-110">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="065b7-111">Evite usar `cref` marcas com prefixos, pois isso impede que o compilador Verifique as referências.</span><span class="sxs-lookup"><span data-stu-id="065b7-111">Avoid using `cref` tags with prefixes, because it prevents the compiler from verifying references.</span></span> <span data-ttu-id="065b7-112">Ele também impede que o IDE (ambiente de desenvolvimento integrado) do Visual Studio Localize e atualize essas referências de símbolo durante refatoração.</span><span class="sxs-lookup"><span data-stu-id="065b7-112">It also prevents the Visual Studio integrated development environment (IDE) from finding and updating these symbol references during refactorings.</span></span> |
