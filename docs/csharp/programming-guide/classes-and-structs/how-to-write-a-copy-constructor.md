---
title: Como escrever um construtor de cópia – guia de programação C#
description: Saiba como escrever um construtor de cópia em C# que usa uma instância da classe e retorna uma nova instância com os valores da entrada.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 85899d2de05312be921199387cc1155fa8e9d2f1
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098977"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="c2d25-103">Como escrever um construtor de cópia (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="c2d25-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="c2d25-104">O C# não fornece um construtor de cópia para objetos, mas é possível escrever um por conta própria.</span><span class="sxs-lookup"><span data-stu-id="c2d25-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d25-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c2d25-105">Example</span></span>  

 <span data-ttu-id="c2d25-106">No exemplo a seguir, a `Person`[class](../../language-reference/keywords/class.md) define um construtor de cópia que usa, como seu argumento, uma instância de `Person`.</span><span class="sxs-lookup"><span data-stu-id="c2d25-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="c2d25-107">Os valores das propriedades do argumento são atribuídos às propriedades da nova instância de `Person`.</span><span class="sxs-lookup"><span data-stu-id="c2d25-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="c2d25-108">O código contém um construtor de cópia alternativa que envia as propriedades `Name` e `Age` da instância que você deseja copiar para o construtor de instância da classe.</span><span class="sxs-lookup"><span data-stu-id="c2d25-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="c2d25-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="c2d25-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="c2d25-110">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="c2d25-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c2d25-111">Classes e structs</span><span class="sxs-lookup"><span data-stu-id="c2d25-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="c2d25-112">Construtores</span><span class="sxs-lookup"><span data-stu-id="c2d25-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="c2d25-113">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="c2d25-113">Finalizers</span></span>](./destructors.md)
