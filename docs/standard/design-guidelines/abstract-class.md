---
title: Design de classe abstrata
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 6903e10c8695376d8ac5961461796c5413307f90
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821639"
---
# <a name="abstract-class-design"></a><span data-ttu-id="4ba15-102">Design de classe abstrata</span><span class="sxs-lookup"><span data-stu-id="4ba15-102">Abstract Class Design</span></span>

<span data-ttu-id="4ba15-103">❌ Não defina construtores internos públicos ou protegidos em tipos abstratos.</span><span class="sxs-lookup"><span data-stu-id="4ba15-103">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="4ba15-104">Os construtores só devem ser públicos se os usuários precisarem criar instâncias do tipo.</span><span class="sxs-lookup"><span data-stu-id="4ba15-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="4ba15-105">Como não é possível criar instâncias de um tipo abstrato, um tipo abstrato com um construtor público é projetado incorretamente e induzindo aos usuários.</span><span class="sxs-lookup"><span data-stu-id="4ba15-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="4ba15-106">✔️ definir um construtor protegido ou interno em classes abstratas.</span><span class="sxs-lookup"><span data-stu-id="4ba15-106">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="4ba15-107">Um construtor protegido é mais comum e simplesmente permite que a classe base faça sua própria inicialização quando os subtipos são criados.</span><span class="sxs-lookup"><span data-stu-id="4ba15-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="4ba15-108">Um construtor interno pode ser usado para limitar implementações concretas da classe abstrata ao assembly que define a classe.</span><span class="sxs-lookup"><span data-stu-id="4ba15-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="4ba15-109">✔️ fornece pelo menos um tipo concreto que herda de cada classe abstrata que você envia.</span><span class="sxs-lookup"><span data-stu-id="4ba15-109">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="4ba15-110">Fazer isso ajuda a validar o design da classe abstrata.</span><span class="sxs-lookup"><span data-stu-id="4ba15-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="4ba15-111">Por exemplo,  <xref:System.IO.FileStream?displayProperty=nameWithType> é uma implementação da <xref:System.IO.Stream?displayProperty=nameWithType> classe abstract.</span><span class="sxs-lookup"><span data-stu-id="4ba15-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="4ba15-112">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="4ba15-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4ba15-113">*Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4ba15-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4ba15-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ba15-114">See also</span></span>

- [<span data-ttu-id="4ba15-115">Diretrizes de design de tipo</span><span class="sxs-lookup"><span data-stu-id="4ba15-115">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="4ba15-116">Diretrizes de design de estrutura</span><span class="sxs-lookup"><span data-stu-id="4ba15-116">Framework Design Guidelines</span></span>](index.md)
