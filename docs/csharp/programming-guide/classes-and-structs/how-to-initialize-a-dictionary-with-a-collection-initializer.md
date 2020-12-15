---
title: Como inicializar um dicionário com um inicializador de coleção – Guia de Programação em C#
description: Saiba como inicializar um dicionário em C#, usando o método Add ou um inicializador de índice. Este exemplo mostra as duas opções.
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: bcb9c5af215ff468812d08e93d37eecc40d745ea
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513075"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="178f8-104">Como inicializar um dicionário com um inicializador de coleção (Guia de Programação em C#)</span><span class="sxs-lookup"><span data-stu-id="178f8-104">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="178f8-105">Um <xref:System.Collections.Generic.Dictionary%602> contém uma coleção de pares de chave-valor.</span><span class="sxs-lookup"><span data-stu-id="178f8-105">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="178f8-106">Seu método <xref:System.Collections.Generic.Dictionary%602.Add%2A> recebe dois parâmetros, um para a chave e outro para o valor.</span><span class="sxs-lookup"><span data-stu-id="178f8-106">Its <xref:System.Collections.Generic.Dictionary%602.Add%2A> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="178f8-107">Uma maneira de inicializar um <xref:System.Collections.Generic.Dictionary%602> ou qualquer coleção cujo método `Add` use vários parâmetros, é colocar cada conjunto de parâmetros entre chaves, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="178f8-107">One way to initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, is to enclose each set of parameters in braces as shown in the following example.</span></span> <span data-ttu-id="178f8-108">Outra opção é usar um inicializador de índice, também mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="178f8-108">Another option is to use an index initializer, also shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="178f8-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="178f8-109">Example</span></span>

<span data-ttu-id="178f8-110">No exemplo de código a seguir, um <xref:System.Collections.Generic.Dictionary%602> é inicializado com instâncias do tipo `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="178f8-110">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  <span data-ttu-id="178f8-111">A primeira inicialização usa o método `Add` com dois argumentos.</span><span class="sxs-lookup"><span data-stu-id="178f8-111">The first initialization uses the `Add` method with two arguments.</span></span> <span data-ttu-id="178f8-112">O compilador gera uma chamada para `Add` para cada um dos pares de chaves `int` e valores `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="178f8-112">The compiler generates a call to `Add` for each of the pairs of `int` keys and `StudentName` values.</span></span> <span data-ttu-id="178f8-113">A segunda usa um método de indexador público de leitura/gravação da classe `Dictionary`:</span><span class="sxs-lookup"><span data-stu-id="178f8-113">The second uses a public read / write indexer method of the `Dictionary` class:</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

<span data-ttu-id="178f8-114">Observe os dois pares de chaves em cada elemento da coleção na primeira declaração.</span><span class="sxs-lookup"><span data-stu-id="178f8-114">Note the two pairs of braces in each element of the collection in the first declaration.</span></span> <span data-ttu-id="178f8-115">As chaves mais internas incluem o inicializador de objeto para o `StudentName` e as chaves mais externas delimitam o inicializador para o par de chave/valor que será adicionado ao `students` <xref:System.Collections.Generic.Dictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="178f8-115">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="178f8-116">Por fim, todo o inicializador de coleção do dicionário é colocado entre chaves.</span><span class="sxs-lookup"><span data-stu-id="178f8-116">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span> <span data-ttu-id="178f8-117">Na segunda inicialização, o lado esquerdo da atribuição é a chave e o lado direito é o valor, usando um inicializador de objeto para `StudentName`.</span><span class="sxs-lookup"><span data-stu-id="178f8-117">In the second initialization, the left side of the assignment is the key and the right side is the value, using an object initializer for `StudentName`.</span></span>

## <a name="see-also"></a><span data-ttu-id="178f8-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="178f8-118">See also</span></span>

- [<span data-ttu-id="178f8-119">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="178f8-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="178f8-120">Inicializadores de objeto e coleção</span><span class="sxs-lookup"><span data-stu-id="178f8-120">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
