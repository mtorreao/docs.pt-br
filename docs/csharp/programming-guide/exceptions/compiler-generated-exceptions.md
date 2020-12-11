---
title: Exceções geradas pelo compilador – Guia de Programação em C#
description: Saiba mais sobre as exceções geradas pelo compilador. Examine uma lista de exceções geradas automaticamente e suas condições de erro.
ms.date: 12/09/2020
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 43bacbb1025bc0af3a5f21979315b3d1b0d61066
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110345"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="ca801-104">Exceções geradas pelo compilador (Guia de Programação em C#)</span><span class="sxs-lookup"><span data-stu-id="ca801-104">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="ca801-105">Algumas exceções são geradas automaticamente pelo tempo de execução do .NET quando operações básicas falham.</span><span class="sxs-lookup"><span data-stu-id="ca801-105">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="ca801-106">Essas exceções e suas condições de erro são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ca801-106">These exceptions and their error conditions are listed in the following table.</span></span>

|<span data-ttu-id="ca801-107">Exceção</span><span class="sxs-lookup"><span data-stu-id="ca801-107">Exception</span></span>|<span data-ttu-id="ca801-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca801-108">Description</span></span>|
|---------------|-----------------|
|<xref:System.ArithmeticException>|<span data-ttu-id="ca801-109">Uma classe base para exceções que ocorrem durante operações aritméticas, tais como <xref:System.DivideByZeroException> e <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="ca801-109">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="ca801-110">Gerado quando uma matriz não pode armazenar um determinado elemento porque o tipo real do elemento é incompatível com o tipo real da matriz.</span><span class="sxs-lookup"><span data-stu-id="ca801-110">Thrown when an array can't store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|
|<xref:System.DivideByZeroException>|<span data-ttu-id="ca801-111">Lançada quando é feita uma tentativa de dividir um valor inteiro por zero.</span><span class="sxs-lookup"><span data-stu-id="ca801-111">Thrown when an attempt is made to divide an integral value by zero.</span></span>|
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="ca801-112">Lançada quando é feita uma tentativa de indexar uma matriz quando o índice é menor que zero ou fora dos limites da matriz.</span><span class="sxs-lookup"><span data-stu-id="ca801-112">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|
|<xref:System.InvalidCastException>|<span data-ttu-id="ca801-113">Gerada quando uma conversão explícita de um tipo base para uma interface ou um tipo derivado falha em runtime.</span><span class="sxs-lookup"><span data-stu-id="ca801-113">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|
|<xref:System.NullReferenceException>|<span data-ttu-id="ca801-114">Gerado quando é feita uma tentativa de fazer referência a um objeto cujo valor é [nulo](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="ca801-114">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|
|<xref:System.OutOfMemoryException>|<span data-ttu-id="ca801-115">Lançada quando uma tentativa de alocar memória usando o operador [new](../../language-reference/operators/new-operator.md) falha.</span><span class="sxs-lookup"><span data-stu-id="ca801-115">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="ca801-116">Essa exceção indica que a memória disponível para o Common Language Runtime foi esgotada.</span><span class="sxs-lookup"><span data-stu-id="ca801-116">This exception indicates that the memory available to the common language runtime has been exhausted.</span></span>|
|<xref:System.OverflowException>|<span data-ttu-id="ca801-117">Lançada quando uma operação aritmética em um contexto `checked` estoura.</span><span class="sxs-lookup"><span data-stu-id="ca801-117">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|
|<xref:System.StackOverflowException>|<span data-ttu-id="ca801-118">Lançada quando a pilha de execução acaba tendo muitas chamadas de método pendentes, normalmente indica uma recursão muito profunda ou infinita.</span><span class="sxs-lookup"><span data-stu-id="ca801-118">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|
|<xref:System.TypeInitializationException>|<span data-ttu-id="ca801-119">Lançada quando um construtor estático lança uma exceção e não há nenhuma cláusula `catch` compatível para capturá-la.</span><span class="sxs-lookup"><span data-stu-id="ca801-119">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ca801-120">Veja também</span><span class="sxs-lookup"><span data-stu-id="ca801-120">See also</span></span>

- [<span data-ttu-id="ca801-121">try-catch</span><span class="sxs-lookup"><span data-stu-id="ca801-121">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="ca801-122">try-finally</span><span class="sxs-lookup"><span data-stu-id="ca801-122">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="ca801-123">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="ca801-123">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
