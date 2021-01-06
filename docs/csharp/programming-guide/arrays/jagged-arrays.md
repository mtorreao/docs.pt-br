---
title: Matrizes denteadas – Guia de Programação em C#
description: Uma matriz denteada em C# é uma matriz cujos elementos são matrizes de tamanhos diferentes. Saiba como declarar, inicializar e acessar matrizes denteadas.
ms.date: 12/18/2020
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 6d4fb939fb6594c7644a80eb688ea852ddf8a5c5
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737275"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="5043c-104">Matrizes denteadas (Guia de Programação em C#)</span><span class="sxs-lookup"><span data-stu-id="5043c-104">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="5043c-105">Uma matriz denteada é uma matriz cujos elementos são matrizes, possivelmente de tamanhos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5043c-105">A jagged array is an array whose elements are arrays, possibly of different sizes.</span></span> <span data-ttu-id="5043c-106">Às vezes, uma matriz denteada é chamada de uma "matriz de matrizes."</span><span class="sxs-lookup"><span data-stu-id="5043c-106">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="5043c-107">Os exemplos a seguir mostram como declarar, inicializar e acessar matrizes denteadas.</span><span class="sxs-lookup"><span data-stu-id="5043c-107">The following examples show how to declare, initialize, and access jagged arrays.</span></span>

 <span data-ttu-id="5043c-108">A seguir, há uma declaração de uma matriz unidimensional que tem três elementos, cada um do qual é uma matriz de dimensão única de inteiros:</span><span class="sxs-lookup"><span data-stu-id="5043c-108">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>

 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]

 <span data-ttu-id="5043c-109">Antes de usar `jaggedArray`, seus elementos devem ser inicializados.</span><span class="sxs-lookup"><span data-stu-id="5043c-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="5043c-110">É possível inicializar os elementos dessa forma:</span><span class="sxs-lookup"><span data-stu-id="5043c-110">You can initialize the elements like this:</span></span>

 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]

 <span data-ttu-id="5043c-111">Cada um dos elementos é uma matriz unidimensional de inteiros.</span><span class="sxs-lookup"><span data-stu-id="5043c-111">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="5043c-112">O primeiro elemento é uma matriz de 5 inteiros, o segundo é uma matriz de 4 inteiros e o terceiro é uma matriz de 2 inteiros.</span><span class="sxs-lookup"><span data-stu-id="5043c-112">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>

 <span data-ttu-id="5043c-113">Também é possível usar os inicializadores para preencher os elementos matriz com valores, caso em que não é necessário o tamanho da matriz.</span><span class="sxs-lookup"><span data-stu-id="5043c-113">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="5043c-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5043c-114">For example:</span></span>

 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]

 <span data-ttu-id="5043c-115">Também é possível inicializar a matriz mediante uma declaração como esta:</span><span class="sxs-lookup"><span data-stu-id="5043c-115">You can also initialize the array upon declaration like this:</span></span>

 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]

 <span data-ttu-id="5043c-116">É possível usar a seguinte forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="5043c-116">You can use the following shorthand form.</span></span> <span data-ttu-id="5043c-117">Observe que não é possível omitir o operador `new` da inicialização de elementos, porque não há nenhuma inicialização padrão para os elementos:</span><span class="sxs-lookup"><span data-stu-id="5043c-117">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>

 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]

 <span data-ttu-id="5043c-118">Uma matriz denteada é uma matriz de matrizes e, portanto, seus elementos são tipos de referência e são inicializados para `null`.</span><span class="sxs-lookup"><span data-stu-id="5043c-118">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>

 <span data-ttu-id="5043c-119">É possível acessar elementos de matrizes individuais como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="5043c-119">You can access individual array elements like these examples:</span></span>

 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]

 <span data-ttu-id="5043c-120">É possível misturar matrizes denteadas e multidimensionais.</span><span class="sxs-lookup"><span data-stu-id="5043c-120">It's possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="5043c-121">A seguir, há uma declaração e inicialização de uma matriz denteada unidimensional que contém três elementos de matriz bidimensional de tamanhos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5043c-121">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="5043c-122">Para obter mais informações, consulte [matrizes multidimensionais](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="5043c-122">For more information, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>

 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]

 <span data-ttu-id="5043c-123">É possível acessar elementos individuais conforme mostrado neste exemplo, que exibe o valor do elemento `[1,0]` da primeira matriz (valor `5`):</span><span class="sxs-lookup"><span data-stu-id="5043c-123">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>

 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]

 <span data-ttu-id="5043c-124">O método `Length` retorna inúmeros conjuntos contidos na matriz denteada.</span><span class="sxs-lookup"><span data-stu-id="5043c-124">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="5043c-125">Por exemplo, supondo que você tenha declarado a matriz anterior, esta linha:</span><span class="sxs-lookup"><span data-stu-id="5043c-125">For example, assuming you have declared the previous array, this line:</span></span>

 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]

 <span data-ttu-id="5043c-126">retorna um valor de 3.</span><span class="sxs-lookup"><span data-stu-id="5043c-126">returns a value of 3.</span></span>

## <a name="example"></a><span data-ttu-id="5043c-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5043c-127">Example</span></span>

 <span data-ttu-id="5043c-128">Este exemplo cria uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="5043c-128">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="5043c-129">Cada um dos elementos da matriz tem um tamanho diferente.</span><span class="sxs-lookup"><span data-stu-id="5043c-129">Each one of the array elements has a different size.</span></span>

 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]

## <a name="see-also"></a><span data-ttu-id="5043c-130">Veja também</span><span class="sxs-lookup"><span data-stu-id="5043c-130">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="5043c-131">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="5043c-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5043c-132">matrizes</span><span class="sxs-lookup"><span data-stu-id="5043c-132">Arrays</span></span>](./index.md)
- [<span data-ttu-id="5043c-133">Matrizes unidimensionais</span><span class="sxs-lookup"><span data-stu-id="5043c-133">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="5043c-134">Matrizes multidimensionais</span><span class="sxs-lookup"><span data-stu-id="5043c-134">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
