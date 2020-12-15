---
title: Como criar um novo método para uma enumeração – guia de programação C#
description: Saiba como usar métodos de extensão para adicionar funcionalidade a uma enumeração em C#. Este exemplo mostra um método de extensão chamado passagem de uma enumeração chamada notas.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 88afff854b8136bde837db8effb0e0eb512e1099
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513087"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="0803a-104">Como criar um novo método para uma enumeração (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="0803a-104">How to create a new method for an enumeration (C# Programming Guide)</span></span>

<span data-ttu-id="0803a-105">Você pode usar métodos de extensão para adicionar funcionalidades específica para um tipo de enumeração específico.</span><span class="sxs-lookup"><span data-stu-id="0803a-105">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0803a-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0803a-106">Example</span></span>  

 <span data-ttu-id="0803a-107">No exemplo a seguir, a enumeração `Grades` representa as letras possíveis que um aluno pode receber em uma classe.</span><span class="sxs-lookup"><span data-stu-id="0803a-107">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="0803a-108">Um método de extensão chamado `Passing` é adicionado ao tipo `Grades` de forma que cada instância desse tipo agora "sabe" se ele representa uma nota de aprovação ou não.</span><span class="sxs-lookup"><span data-stu-id="0803a-108">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="0803a-109">Observe que a classe `Extensions` também contém uma variável estática atualizada dinamicamente e que o valor retornado do método de extensão reflete o valor atual dessa variável.</span><span class="sxs-lookup"><span data-stu-id="0803a-109">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="0803a-110">Isso demonstra que, nos bastidores, os métodos de extensão são chamados diretamente na classe estática na qual eles são definidos.</span><span class="sxs-lookup"><span data-stu-id="0803a-110">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0803a-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0803a-111">See also</span></span>

- [<span data-ttu-id="0803a-112">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="0803a-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0803a-113">Métodos de Extensão</span><span class="sxs-lookup"><span data-stu-id="0803a-113">Extension Methods</span></span>](./extension-methods.md)
