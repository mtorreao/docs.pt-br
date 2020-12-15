---
title: Como substituir o método ToString – guia de programação C#
description: Saiba como substituir o método ToString em C#. Cada classe ou struct herda Object e obtém ToString, que retorna uma representação de cadeia de caracteres desse objeto.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 9573e6b97383d6f422c6a2802040fb9d6db709dd
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512737"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="fddbb-104">Como substituir o método ToString (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="fddbb-104">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="fddbb-105">Cada classe ou struct no C# herda implicitamente a classe <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="fddbb-105">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="fddbb-106">Portanto, cada objeto no C# obtém o método <xref:System.Object.ToString%2A>, que retorna uma representação de cadeia de caracteres desse objeto.</span><span class="sxs-lookup"><span data-stu-id="fddbb-106">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="fddbb-107">Por exemplo, todas as variáveis do tipo `int` tem um método `ToString`, que permite retornar seus conteúdos como uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="fddbb-107">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="fddbb-108">Ao criar uma classe ou struct personalizada, é necessário substituir o método <xref:System.Object.ToString%2A> a fim de fornecer informações sobre o tipo ao código cliente.</span><span class="sxs-lookup"><span data-stu-id="fddbb-108">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="fddbb-109">Para obter informações sobre como usar cadeias de caracteres de formato e outros tipos de formatação personalizada com o método `ToString`, consulte [Tipos de Formatação](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="fddbb-109">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fddbb-110">Ao decidir quais informações devem ser fornecidas por meio desse método, considere se a classe ou struct será utilizado por código não confiável.</span><span class="sxs-lookup"><span data-stu-id="fddbb-110">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="fddbb-111">Assegure-se de que nenhuma informação que possa ser explorada por código mal-intencionado seja fornecida.</span><span class="sxs-lookup"><span data-stu-id="fddbb-111">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="fddbb-112">Substituir o método `ToString` na classe ou struct:</span><span class="sxs-lookup"><span data-stu-id="fddbb-112">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="fddbb-113">Declare um método `ToString` com os seguintes modificadores e tipo retornado:</span><span class="sxs-lookup"><span data-stu-id="fddbb-113">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="fddbb-114">Implemente o método para que ele retorne uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="fddbb-114">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="fddbb-115">O exemplo a seguir retorna o nome da classe, além dos dados específicos de uma instância particular da classe.</span><span class="sxs-lookup"><span data-stu-id="fddbb-115">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="fddbb-116">É possível testar o método `ToString`, conforme mostrado no exemplo de código a seguir:</span><span class="sxs-lookup"><span data-stu-id="fddbb-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="fddbb-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fddbb-117">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="fddbb-118">Guia de programação C#</span><span class="sxs-lookup"><span data-stu-id="fddbb-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fddbb-119">Classes e structs</span><span class="sxs-lookup"><span data-stu-id="fddbb-119">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="fddbb-120">Cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="fddbb-120">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="fddbb-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fddbb-121">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="fddbb-122">override</span><span class="sxs-lookup"><span data-stu-id="fddbb-122">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="fddbb-123">virtuaisLUNs</span><span class="sxs-lookup"><span data-stu-id="fddbb-123">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="fddbb-124">Formatar tipos</span><span class="sxs-lookup"><span data-stu-id="fddbb-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
