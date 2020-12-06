---
title: Propriedades
description: 'Saiba mais sobre as propriedades de F #, que são membros que representam valores associados a um objeto.'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740192"
---
# <a name="properties"></a><span data-ttu-id="2c61a-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2c61a-103">Properties</span></span>

<span data-ttu-id="2c61a-104">*As propriedades* são membros que representam valores associados a um objeto.</span><span class="sxs-lookup"><span data-stu-id="2c61a-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c61a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2c61a-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="2c61a-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="2c61a-106">Remarks</span></span>

<span data-ttu-id="2c61a-107">As propriedades representam a relação "tem um" na programação orientada a objeto, representando os dados associados a instâncias de objeto ou, para propriedades estáticas, com o tipo.</span><span class="sxs-lookup"><span data-stu-id="2c61a-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="2c61a-108">Você pode declarar Propriedades de duas maneiras, dependendo se você deseja especificar explicitamente o valor subjacente (também chamado de armazenamento de backup) para a propriedade ou se deseja permitir que o compilador gere automaticamente o repositório de backup para você.</span><span class="sxs-lookup"><span data-stu-id="2c61a-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="2c61a-109">Em geral, você deve usar a maneira mais explícita se a propriedade tiver uma implementação não trivial e a maneira automática quando a propriedade for apenas um wrapper simples para um valor ou variável.</span><span class="sxs-lookup"><span data-stu-id="2c61a-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="2c61a-110">Para declarar uma propriedade explicitamente, use a `member` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="2c61a-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="2c61a-111">Essa sintaxe declarativa é seguida pela sintaxe que especifica os `get` métodos e `set` , também *acessadores* nomeados.</span><span class="sxs-lookup"><span data-stu-id="2c61a-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="2c61a-112">As várias formas da sintaxe explícita mostradas na seção sintaxe são usadas para propriedades de leitura/gravação, somente leitura e somente gravação.</span><span class="sxs-lookup"><span data-stu-id="2c61a-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="2c61a-113">Para propriedades somente leitura, você define apenas um `get` método; para propriedades somente gravação, defina apenas um `set` método.</span><span class="sxs-lookup"><span data-stu-id="2c61a-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="2c61a-114">Observe que, quando uma propriedade tem ambos `get` e `set` acessadores, a sintaxe alternativa permite que você especifique atributos e modificadores de acessibilidade que são diferentes para cada acessador, como é mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="2c61a-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="2c61a-115">Para propriedades de leitura/gravação, que têm um `get` `set` método and, a ordem de `get` e `set` pode ser revertida.</span><span class="sxs-lookup"><span data-stu-id="2c61a-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="2c61a-116">Como alternativa, você pode fornecer a sintaxe mostrada `get` apenas para e a sintaxe mostrada `set` apenas em vez de usar a sintaxe combinada.</span><span class="sxs-lookup"><span data-stu-id="2c61a-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="2c61a-117">Isso torna mais fácil comentar o indivíduo `get` ou o `set` método, se isso for algo que talvez seja necessário fazer.</span><span class="sxs-lookup"><span data-stu-id="2c61a-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="2c61a-118">Essa alternativa ao uso da sintaxe combinada é mostrada no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="2c61a-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="2c61a-119">Os valores privados que contêm os dados para propriedades são chamados de *armazenamentos de backup*.</span><span class="sxs-lookup"><span data-stu-id="2c61a-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="2c61a-120">Para que o compilador crie o armazenamento de backup automaticamente, use as palavras-chave `member val` , omita o autoidentificador e, em seguida, forneça uma expressão para inicializar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c61a-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="2c61a-121">Se a propriedade for mutável, inclua `with get, set` .</span><span class="sxs-lookup"><span data-stu-id="2c61a-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="2c61a-122">Por exemplo, o tipo de classe a seguir inclui duas propriedades implementadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2c61a-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="2c61a-123">`Property1` é somente leitura e é inicializado para o argumento fornecido para o construtor primário e `Property2` é uma propriedade configurável inicializada para uma cadeia de caracteres vazia:</span><span class="sxs-lookup"><span data-stu-id="2c61a-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="2c61a-124">As propriedades implementadas automaticamente fazem parte da inicialização de um tipo, portanto, elas devem ser incluídas antes de qualquer outra definição de membro, assim como `let` associações e `do` associações em uma definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="2c61a-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="2c61a-125">Observe que a expressão que Inicializa uma propriedade implementada automaticamente só é avaliada na inicialização, e não toda vez que a propriedade é acessada.</span><span class="sxs-lookup"><span data-stu-id="2c61a-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="2c61a-126">Esse comportamento está em contraste com o comportamento de uma propriedade explicitamente implementada.</span><span class="sxs-lookup"><span data-stu-id="2c61a-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="2c61a-127">O que isso significa efetivamente é que o código para inicializar essas propriedades é adicionado ao construtor de uma classe.</span><span class="sxs-lookup"><span data-stu-id="2c61a-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="2c61a-128">Considere o seguinte código que mostra essa diferença:</span><span class="sxs-lookup"><span data-stu-id="2c61a-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

<span data-ttu-id="2c61a-129">**Saída**</span><span class="sxs-lookup"><span data-stu-id="2c61a-129">**Output**</span></span>

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="2c61a-130">A saída do código anterior mostra que o valor de autoproperty é inalterado quando chamado repetidamente, enquanto o Explicitproperty muda a cada vez que é chamado.</span><span class="sxs-lookup"><span data-stu-id="2c61a-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="2c61a-131">Isso demonstra que a expressão para uma propriedade implementada automaticamente não é avaliada a cada vez, como é o método getter para a propriedade explícita.</span><span class="sxs-lookup"><span data-stu-id="2c61a-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="2c61a-132">Há algumas bibliotecas, como a Entity Framework ( `System.Data.Entity` ) que executam operações personalizadas em construtores de classe base que não funcionam bem com a inicialização de propriedades implementadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2c61a-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="2c61a-133">Nesses casos, tente usar propriedades explícitas.</span><span class="sxs-lookup"><span data-stu-id="2c61a-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="2c61a-134">As propriedades podem ser membros de classes, estruturas, uniões discriminadas, registros, interfaces e extensões de tipo e também podem ser definidas em expressões de objeto.</span><span class="sxs-lookup"><span data-stu-id="2c61a-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="2c61a-135">Atributos podem ser aplicados a propriedades.</span><span class="sxs-lookup"><span data-stu-id="2c61a-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="2c61a-136">Para aplicar um atributo a uma propriedade, grave o atributo em uma linha separada antes da propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c61a-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="2c61a-137">Para obter mais informações, consulte [Atributos](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2c61a-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="2c61a-138">Por padrão, as propriedades são públicas.</span><span class="sxs-lookup"><span data-stu-id="2c61a-138">By default, properties are public.</span></span> <span data-ttu-id="2c61a-139">Os modificadores de acessibilidade também podem ser aplicados às propriedades.</span><span class="sxs-lookup"><span data-stu-id="2c61a-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="2c61a-140">Para aplicar um modificador de acessibilidade, adicione-o imediatamente antes do nome da propriedade se ela for para ser aplicada aos `get` `set` métodos e; adicione-o antes `get` das `set` palavras-chave e se for necessária uma acessibilidade diferente para cada acessador.</span><span class="sxs-lookup"><span data-stu-id="2c61a-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="2c61a-141">O *modificador de acessibilidade* pode ser um dos seguintes: `public` , `private` , `internal` .</span><span class="sxs-lookup"><span data-stu-id="2c61a-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="2c61a-142">Para mais informações, consulte [Controle de acesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="2c61a-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="2c61a-143">Implementações de propriedade são executadas cada vez que uma propriedade é acessada.</span><span class="sxs-lookup"><span data-stu-id="2c61a-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="2c61a-144">Propriedades de instância e estática</span><span class="sxs-lookup"><span data-stu-id="2c61a-144">Static and Instance Properties</span></span>

<span data-ttu-id="2c61a-145">As propriedades podem ser propriedades estáticas ou de instância.</span><span class="sxs-lookup"><span data-stu-id="2c61a-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="2c61a-146">As propriedades estáticas podem ser chamadas sem uma instância e são usadas para valores associados ao tipo, não com objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="2c61a-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="2c61a-147">Para propriedades estáticas, omita o próprio identificador.</span><span class="sxs-lookup"><span data-stu-id="2c61a-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="2c61a-148">O autoidentificador é necessário para as propriedades de instância.</span><span class="sxs-lookup"><span data-stu-id="2c61a-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="2c61a-149">A definição de propriedade estática a seguir se baseia em um cenário no qual você tem um campo estático `myStaticValue` que é o repositório de backup para a propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c61a-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="2c61a-150">As propriedades também podem ser do tipo matriz; nesse caso, elas são chamadas de *Propriedades indexadas*.</span><span class="sxs-lookup"><span data-stu-id="2c61a-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="2c61a-151">Para obter mais informações, consulte [Propriedades indexadas](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2c61a-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="2c61a-152">Digitar anotação para propriedades</span><span class="sxs-lookup"><span data-stu-id="2c61a-152">Type Annotation for Properties</span></span>

<span data-ttu-id="2c61a-153">Em muitos casos, o compilador tem informações suficientes para inferir o tipo de uma propriedade do tipo de armazenamento de backup, mas você pode definir o tipo explicitamente adicionando uma anotação de tipo.</span><span class="sxs-lookup"><span data-stu-id="2c61a-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="2c61a-154">Usando acessadores de conjunto de propriedades</span><span class="sxs-lookup"><span data-stu-id="2c61a-154">Using Property set Accessors</span></span>

<span data-ttu-id="2c61a-155">Você pode definir propriedades que fornecem `set` acessadores usando o `<-` operador.</span><span class="sxs-lookup"><span data-stu-id="2c61a-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="2c61a-156">A saída é **20**.</span><span class="sxs-lookup"><span data-stu-id="2c61a-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="2c61a-157">Propriedades abstratas</span><span class="sxs-lookup"><span data-stu-id="2c61a-157">Abstract Properties</span></span>

<span data-ttu-id="2c61a-158">As propriedades podem ser abstratas.</span><span class="sxs-lookup"><span data-stu-id="2c61a-158">Properties can be abstract.</span></span> <span data-ttu-id="2c61a-159">Assim como acontece com métodos, `abstract` apenas significa que há um despacho virtual associado à propriedade.</span><span class="sxs-lookup"><span data-stu-id="2c61a-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="2c61a-160">As propriedades abstratas podem ser realmente abstratas, ou seja, sem uma definição na mesma classe.</span><span class="sxs-lookup"><span data-stu-id="2c61a-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="2c61a-161">A classe que contém essa propriedade é, portanto, uma classe abstrata.</span><span class="sxs-lookup"><span data-stu-id="2c61a-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="2c61a-162">Como alternativa, abstract pode significar apenas que uma propriedade é virtual e, nesse caso, uma definição deve estar presente na mesma classe.</span><span class="sxs-lookup"><span data-stu-id="2c61a-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="2c61a-163">Observe que as propriedades abstratas não devem ser particulares e, se um acessador for abstrato, o outro também deverá ser abstrato.</span><span class="sxs-lookup"><span data-stu-id="2c61a-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="2c61a-164">Para obter mais informações sobre classes abstratas, consulte [classes abstratas](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2c61a-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="2c61a-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c61a-165">See also</span></span>

- [<span data-ttu-id="2c61a-166">Membros</span><span class="sxs-lookup"><span data-stu-id="2c61a-166">Members</span></span>](index.md)
- [<span data-ttu-id="2c61a-167">Métodos</span><span class="sxs-lookup"><span data-stu-id="2c61a-167">Methods</span></span>](methods.md)
