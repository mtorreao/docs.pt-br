---
title: Acesso thread-safe em expressões regulares
ms.date: 03/30/2017
helpviewer_keywords:
- .NET regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
ms.openlocfilehash: a10b5d01d308af3c808404608e6be1d77e6be8e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734160"
---
# <a name="thread-safety-in-regular-expressions"></a><span data-ttu-id="e0bd5-102">Acesso thread-safe em expressões regulares</span><span class="sxs-lookup"><span data-stu-id="e0bd5-102">Thread Safety in Regular Expressions</span></span>

<span data-ttu-id="e0bd5-103">A própria classe <xref:System.Text.RegularExpressions.Regex> é thread-safe e imutável (somente leitura).</span><span class="sxs-lookup"><span data-stu-id="e0bd5-103">The <xref:System.Text.RegularExpressions.Regex> class itself is thread safe and immutable (read-only).</span></span> <span data-ttu-id="e0bd5-104">Ou seja, os objetos de **Regex** podem ser criados em qualquer thread e compartilhados entre os threads. Métodos correspondentes podem ser chamados de qualquer thread e nunca alteram nenhum estado global.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-104">That is, **Regex** objects can be created on any thread and shared between threads; matching methods can be called from any thread and never alter any global state.</span></span>  
  
 <span data-ttu-id="e0bd5-105">No entanto, os objetos de resultado (**Match** e **MatchCollection**) retornados pela **Regex** devem ser usados em um único thread.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-105">However, result objects (**Match** and **MatchCollection**) returned by **Regex** should be used on a single thread.</span></span> <span data-ttu-id="e0bd5-106">Embora muitos desses objetos sejam logicamente imutáveis, suas implementações poderiam atrasar a computação de alguns resultados para melhorar o desempenho e, como resultado, os chamadores devem serializar o acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-106">Although many of these objects are logically immutable, their implementations could delay computation of some results to improve performance, and as a result, callers must serialize access to them.</span></span>  
  
 <span data-ttu-id="e0bd5-107">Se houver a necessidade de compartilhar os objetos de resultado da **Regex** em vários threads, esses objetos poderão ser convertidos em instâncias thread-safe chamando seus métodos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-107">If there is a need to share **Regex** result objects on multiple threads, these objects can be converted to thread-safe instances by calling their synchronized methods.</span></span> <span data-ttu-id="e0bd5-108">Com exceção dos enumeradores, todas as classes de expressões regulares são thread-safe ou podem ser convertidas em objetos thread-safe por um método sincronizado.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-108">With the exception of enumerators, all regular expression classes are thread safe or can be converted into thread-safe objects by a synchronized method.</span></span>  
  
 <span data-ttu-id="e0bd5-109">Os enumeradores são a única exceção.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-109">Enumerators are the only exception.</span></span> <span data-ttu-id="e0bd5-110">Um aplicativo precisa serializar as chamadas a enumeradores de coleções.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-110">An application must serialize calls to collection enumerators.</span></span> <span data-ttu-id="e0bd5-111">A regra é que se uma coleção pode ser enumerada em mais de um thread simultaneamente, você deve sincronizar os métodos do enumerador no objeto raiz da coleção percorrida pelo enumerador.</span><span class="sxs-lookup"><span data-stu-id="e0bd5-111">The rule is that if a collection can be enumerated on more than one thread simultaneously, you should synchronize enumerator methods on the root object of the collection traversed by the enumerator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bd5-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="e0bd5-112">See also</span></span>

- [<span data-ttu-id="e0bd5-113">Expressões regulares do .NET</span><span class="sxs-lookup"><span data-stu-id="e0bd5-113">.NET Regular Expressions</span></span>](regular-expressions.md)
