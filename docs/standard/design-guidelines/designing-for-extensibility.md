---
title: Designer voltado para extensibilidade
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 7b7b1bcfc907612be12e7f8ca7114183f7e830ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734446"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="118aa-102">Designer voltado para extensibilidade</span><span class="sxs-lookup"><span data-stu-id="118aa-102">Designing for Extensibility</span></span>

<span data-ttu-id="118aa-103">Um aspecto importante da criação de uma estrutura é garantir que a extensibilidade da estrutura tenha sido cuidadosamente considerada.</span><span class="sxs-lookup"><span data-stu-id="118aa-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="118aa-104">Isso exige que você compreenda os custos e os benefícios associados a vários mecanismos de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="118aa-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="118aa-105">Este capítulo ajuda você a decidir quais dos mecanismos de extensibilidade — a subclasse, os eventos, os membros virtuais, os retornos de chamada e assim por diante — pode atender melhor aos requisitos de sua estrutura.</span><span class="sxs-lookup"><span data-stu-id="118aa-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="118aa-106">Há várias maneiras de permitir a extensibilidade em estruturas.</span><span class="sxs-lookup"><span data-stu-id="118aa-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="118aa-107">Elas variam de menos poderosas, mas menos dispendiosas a muito poderosas, mas caras.</span><span class="sxs-lookup"><span data-stu-id="118aa-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="118aa-108">Para qualquer requisito de extensibilidade específico, você deve escolher o mecanismo de extensibilidade menos dispendioso que atenda aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="118aa-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="118aa-109">Tenha em mente que geralmente é possível adicionar mais extensibilidade posteriormente, mas você nunca pode descartar sem introduzir alterações significativas.</span><span class="sxs-lookup"><span data-stu-id="118aa-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="118aa-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="118aa-110">In This Section</span></span>  

 [<span data-ttu-id="118aa-111">Classes sem lacre</span><span class="sxs-lookup"><span data-stu-id="118aa-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="118aa-112">Membros protegidos</span><span class="sxs-lookup"><span data-stu-id="118aa-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="118aa-113">Eventos e retornos de chamada</span><span class="sxs-lookup"><span data-stu-id="118aa-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="118aa-114">Membros virtuais</span><span class="sxs-lookup"><span data-stu-id="118aa-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="118aa-115">Abstrações (tipos abstratos e interfaces)</span><span class="sxs-lookup"><span data-stu-id="118aa-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="118aa-116">Classes base para implementação de abstrações</span><span class="sxs-lookup"><span data-stu-id="118aa-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="118aa-117">Selar</span><span class="sxs-lookup"><span data-stu-id="118aa-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="118aa-118">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="118aa-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="118aa-119">*Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="118aa-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118aa-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="118aa-120">See also</span></span>

- [<span data-ttu-id="118aa-121">Diretrizes de design de estrutura</span><span class="sxs-lookup"><span data-stu-id="118aa-121">Framework Design Guidelines</span></span>](index.md)
