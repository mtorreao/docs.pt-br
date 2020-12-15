---
title: Como implementar uma classe leve com propriedades implementadas automaticamente – guia de programação em C#
description: Saiba como criar uma classe leve imutável em C# que encapsula propriedades implementadas automaticamente. Há duas abordagens de implementação.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 4b28ee17f4be2b933373cce0d3670cbfa9a12895
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513036"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="2f956-104">Como implementar uma classe leve com propriedades autoimplementadas (guia de programação C#)</span><span class="sxs-lookup"><span data-stu-id="2f956-104">How to implement a lightweight class with auto-implemented properties (C# Programming Guide)</span></span>

<span data-ttu-id="2f956-105">Este exemplo mostra como criar uma classe leve imutável que serve apenas para encapsular um conjunto de propriedades autoimplementadas.</span><span class="sxs-lookup"><span data-stu-id="2f956-105">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="2f956-106">Use esse tipo de constructo em vez de um struct quando for necessário usar a semântica do tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="2f956-106">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="2f956-107">É possível tornar uma propriedade imutável de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="2f956-107">You can make an immutable property in two ways:</span></span>

- <span data-ttu-id="2f956-108">É possível declarar o acessador [set](../../language-reference/keywords/set.md) como [privado](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="2f956-108">You can declare the [set](../../language-reference/keywords/set.md) accessor to be [private](../../language-reference/keywords/private.md).</span></span>  <span data-ttu-id="2f956-109">A propriedade será configurável somente dentro do tipo, mas será imutável para os consumidores.</span><span class="sxs-lookup"><span data-stu-id="2f956-109">The property is only settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="2f956-110">Ao declarar um acessador privado `set`, não é possível usar um inicializador de objeto para inicializar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="2f956-110">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="2f956-111">É necessário usar um construtor ou um método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="2f956-111">You must use a constructor or a factory method.</span></span>
- <span data-ttu-id="2f956-112">Você pode declarar somente o acessador [Get](../../language-reference/keywords/get.md) , que torna a propriedade imutável em qualquer lugar, exceto no construtor do tipo.</span><span class="sxs-lookup"><span data-stu-id="2f956-112">You can declare only the [get](../../language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type's constructor.</span></span>

<span data-ttu-id="2f956-113">O exemplo a seguir mostra como uma propriedade com somente acessador get difere de uma com Get e Private set.</span><span class="sxs-lookup"><span data-stu-id="2f956-113">The following example shows how a property with only get accessor differs than one with get and private set.</span></span>

```csharp
class Contact
{
    public string Name { get; }
    public string Address { get; private set; }

    public Contact(string contactName, string contactAddress)
    {
        // Both properties are accessible in the constructor.
        Name = contactName;
        Address = contactAddress;
    }

    // Name isn't assignable here. This will generate a compile error.
    //public void ChangeName(string newName) => Name = newName;

    // Address is assignable here.
    public void ChangeAddress(string newAddress) => Address = newAddress
}
```

## <a name="example"></a><span data-ttu-id="2f956-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2f956-114">Example</span></span>

<span data-ttu-id="2f956-115">O exemplo a seguir mostra duas maneiras de implementar uma classe imutável que tem propriedades autoimplementadas.</span><span class="sxs-lookup"><span data-stu-id="2f956-115">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="2f956-116">Entre essas maneiras, uma declara uma das propriedades com um `set` privado e outra declara uma das propriedades somente com um `get`.</span><span class="sxs-lookup"><span data-stu-id="2f956-116">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="2f956-117">A primeira classe usa um construtor somente para inicializar as propriedades e a segunda classe usa um método de fábrica estático que chama um construtor.</span><span class="sxs-lookup"><span data-stu-id="2f956-117">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only property.
    public string Name { get; }

    // Read-write property with a private set accessor.
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-write property with a private set accessor.
    public string Name { get; private set; }

    // Read-only property.
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

<span data-ttu-id="2f956-118">O compilador cria campos de suporte para cada propriedade autoimplementada.</span><span class="sxs-lookup"><span data-stu-id="2f956-118">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="2f956-119">Os campos não são acessíveis diretamente do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="2f956-119">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f956-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2f956-120">See also</span></span>

- [<span data-ttu-id="2f956-121">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2f956-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="2f956-122">struct</span><span class="sxs-lookup"><span data-stu-id="2f956-122">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="2f956-123">Inicializadores de objeto e coleção</span><span class="sxs-lookup"><span data-stu-id="2f956-123">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
