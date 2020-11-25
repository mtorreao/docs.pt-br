---
title: Diretrizes de design para exceções
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: 28a3e40443c9f1be14243816b347da773705ff02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734719"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="61b65-102">Diretrizes de design para exceções</span><span class="sxs-lookup"><span data-stu-id="61b65-102">Design Guidelines for Exceptions</span></span>

<span data-ttu-id="61b65-103">O tratamento de exceções tem muitas vantagens sobre o relatório de erros baseado em valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="61b65-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="61b65-104">Um bom design de estrutura ajuda o desenvolvedor de aplicativos a obter os benefícios das exceções.</span><span class="sxs-lookup"><span data-stu-id="61b65-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="61b65-105">Esta seção aborda os benefícios das exceções e apresenta as diretrizes para usá-las com eficiência.</span><span class="sxs-lookup"><span data-stu-id="61b65-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61b65-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="61b65-106">In This Section</span></span>  

 [<span data-ttu-id="61b65-107">Lançamento de exceção</span><span class="sxs-lookup"><span data-stu-id="61b65-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="61b65-108">Usar tipos de exceção padrão</span><span class="sxs-lookup"><span data-stu-id="61b65-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="61b65-109">Exceções e desempenho</span><span class="sxs-lookup"><span data-stu-id="61b65-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="61b65-110">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="61b65-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="61b65-111">*Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="61b65-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b65-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="61b65-112">See also</span></span>

- [<span data-ttu-id="61b65-113">Diretrizes de design de estrutura</span><span class="sxs-lookup"><span data-stu-id="61b65-113">Framework Design Guidelines</span></span>](index.md)
