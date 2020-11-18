---
title: Diretrizes de uso
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: d6ea7c7b9ada95e3d0c425aaea18be6cdbb4ce35
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828498"
---
# <a name="usage-guidelines"></a><span data-ttu-id="49522-102">Diretrizes de uso</span><span class="sxs-lookup"><span data-stu-id="49522-102">Usage guidelines</span></span>

<span data-ttu-id="49522-103">Esta seção contém diretrizes para o uso de tipos comuns em APIs acessíveis publicamente.</span><span class="sxs-lookup"><span data-stu-id="49522-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="49522-104">Ele trata do uso direto de tipos de estrutura internos (por exemplo, atributos de serialização) e sobrecarga de operadores comuns.</span><span class="sxs-lookup"><span data-stu-id="49522-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="49522-105">A <xref:System.IDisposable?displayProperty=nameWithType> interface não é abordada nesta seção, mas é discutida na seção [padrão Dispose](../garbage-collection/implementing-dispose.md) .</span><span class="sxs-lookup"><span data-stu-id="49522-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="49522-106">Para obter diretrizes e informações adicionais sobre outros tipos de .NET Framework internos comuns, consulte os tópicos de referência para o seguinte: <xref:System.DateTime?displayProperty=nameWithType> , <xref:System.DateTimeOffset?displayProperty=nameWithType> ,,,,, <xref:System.ICloneable?displayProperty=nameWithType> <xref:System.IComparable%601?displayProperty=nameWithType> <xref:System.IEquatable%601?displayProperty=nameWithType> <xref:System.Nullable%601?displayProperty=nameWithType> <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="49522-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="49522-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="49522-107">In this section</span></span>

[<span data-ttu-id="49522-108">matrizes</span><span class="sxs-lookup"><span data-stu-id="49522-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="49522-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="49522-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="49522-110">Coleções</span><span class="sxs-lookup"><span data-stu-id="49522-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="49522-111">Serialização</span><span class="sxs-lookup"><span data-stu-id="49522-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="49522-112"> Uso deSystem.Xml</span><span class="sxs-lookup"><span data-stu-id="49522-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="49522-113">Operadores de igualdade</span><span class="sxs-lookup"><span data-stu-id="49522-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="49522-114">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="49522-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="49522-115">*Reimpresso com permissão da Pearson Education, Inc. das [Diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicado em 22 de outubro de 2008 por Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="49522-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49522-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="49522-116">See also</span></span>

- [<span data-ttu-id="49522-117">Diretrizes de design de estrutura</span><span class="sxs-lookup"><span data-stu-id="49522-117">Framework Design Guidelines</span></span>](index.md)
