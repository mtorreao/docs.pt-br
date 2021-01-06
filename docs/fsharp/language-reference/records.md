---
title: Registros
description: 'Saiba como os registros F # representam agregações simples de valores nomeados, opcionalmente com membros.'
ms.date: 08/15/2020
ms.openlocfilehash: 2da31da0ec830d458a370e64ca105048181f5d74
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899633"
---
# <a name="records"></a><span data-ttu-id="cb087-103">Registros</span><span class="sxs-lookup"><span data-stu-id="cb087-103">Records</span></span>

<span data-ttu-id="cb087-104">Registros representam agregações simples de valores nomeados, opcionalmente com membros.</span><span class="sxs-lookup"><span data-stu-id="cb087-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="cb087-105">Eles podem ser structs ou tipos de referência.</span><span class="sxs-lookup"><span data-stu-id="cb087-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="cb087-106">Eles são tipos de referência por padrão.</span><span class="sxs-lookup"><span data-stu-id="cb087-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb087-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cb087-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="cb087-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="cb087-108">Remarks</span></span>

<span data-ttu-id="cb087-109">Na sintaxe anterior, *TypeName* é o nome do tipo de registro, *Label1* e *Label2* são nomes de valores, chamados de *Labels* e *type1* e *type2* são os tipos desses valores.</span><span class="sxs-lookup"><span data-stu-id="cb087-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="cb087-110">*lista* de membros é a lista opcional de membros para o tipo.</span><span class="sxs-lookup"><span data-stu-id="cb087-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="cb087-111">Você pode usar o `[<Struct>]` atributo para criar um registro de struct em vez de um registro que é um tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="cb087-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="cb087-112">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="cb087-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="cb087-113">Quando cada rótulo está em uma linha separada, o ponto e vírgula é opcional.</span><span class="sxs-lookup"><span data-stu-id="cb087-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="cb087-114">Você pode definir valores em expressões conhecidas como *expressões de registro*.</span><span class="sxs-lookup"><span data-stu-id="cb087-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="cb087-115">O compilador infere o tipo dos rótulos usados (se os rótulos forem suficientemente distintos dos outros tipos de registro).</span><span class="sxs-lookup"><span data-stu-id="cb087-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="cb087-116">As chaves ({}) incluem a expressão de registro.</span><span class="sxs-lookup"><span data-stu-id="cb087-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="cb087-117">O código a seguir mostra uma expressão de registro que inicializa um registro com três elementos float com rótulos `x` `y` e `z` .</span><span class="sxs-lookup"><span data-stu-id="cb087-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="cb087-118">Não use a forma reduzida se houver outro tipo que também tenha os mesmos rótulos.</span><span class="sxs-lookup"><span data-stu-id="cb087-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="cb087-119">Os rótulos do tipo declarado mais recentemente têm precedência sobre aqueles do tipo declarado anteriormente, portanto, no exemplo anterior, `mypoint3D` é inferido como `Point3D` .</span><span class="sxs-lookup"><span data-stu-id="cb087-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="cb087-120">Você pode especificar explicitamente o tipo de registro, como no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb087-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="cb087-121">Os métodos podem ser definidos para tipos de registro, assim como para tipos de classe.</span><span class="sxs-lookup"><span data-stu-id="cb087-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="cb087-122">Criando registros usando expressões de registro</span><span class="sxs-lookup"><span data-stu-id="cb087-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="cb087-123">Você pode inicializar registros usando os rótulos que são definidos no registro.</span><span class="sxs-lookup"><span data-stu-id="cb087-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="cb087-124">Uma expressão que faz isso é chamada de expressão de *registro*.</span><span class="sxs-lookup"><span data-stu-id="cb087-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="cb087-125">Use chaves para colocar a expressão de registro e usar o ponto e vírgula como um delimitador.</span><span class="sxs-lookup"><span data-stu-id="cb087-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="cb087-126">O exemplo a seguir mostra como criar um registro.</span><span class="sxs-lookup"><span data-stu-id="cb087-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="cb087-127">Os pontos-e-vírgulas após o último campo na expressão de registro e na definição de tipo são opcionais, independentemente de os campos estarem todos em uma linha.</span><span class="sxs-lookup"><span data-stu-id="cb087-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="cb087-128">Ao criar um registro, você deve fornecer valores para cada campo.</span><span class="sxs-lookup"><span data-stu-id="cb087-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="cb087-129">Você não pode fazer referência aos valores de outros campos na expressão de inicialização para qualquer campo.</span><span class="sxs-lookup"><span data-stu-id="cb087-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="cb087-130">No código a seguir, o tipo de `myRecord2` é inferido a partir dos nomes dos campos.</span><span class="sxs-lookup"><span data-stu-id="cb087-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="cb087-131">Opcionalmente, você pode especificar o nome do tipo explicitamente.</span><span class="sxs-lookup"><span data-stu-id="cb087-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="cb087-132">Outra forma de construção de registros pode ser útil quando você precisa copiar um registro existente e, possivelmente, alterar alguns dos valores de campo.</span><span class="sxs-lookup"><span data-stu-id="cb087-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="cb087-133">A linha de código a seguir ilustra isso.</span><span class="sxs-lookup"><span data-stu-id="cb087-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="cb087-134">Essa forma da expressão de registro é chamada de *expressão de registro de cópia e atualização*.</span><span class="sxs-lookup"><span data-stu-id="cb087-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="cb087-135">Os registros são imutáveis por padrão; no entanto, você pode facilmente criar registros modificados usando uma expressão de cópia e atualização.</span><span class="sxs-lookup"><span data-stu-id="cb087-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="cb087-136">Você também pode especificar explicitamente um campo mutável.</span><span class="sxs-lookup"><span data-stu-id="cb087-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="cb087-137">Não use o atributo DefaultValue com campos de registro.</span><span class="sxs-lookup"><span data-stu-id="cb087-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="cb087-138">Uma abordagem melhor é definir as instâncias padrão de registros com campos que são inicializados para valores padrão e, em seguida, usar uma expressão de registro de cópia e atualização para definir quaisquer campos que sejam diferentes dos valores padrão.</span><span class="sxs-lookup"><span data-stu-id="cb087-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="cb087-139">Criando registros recursivos mutuamente</span><span class="sxs-lookup"><span data-stu-id="cb087-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="cb087-140">Em algum momento ao criar um registro, talvez você queira fazer com que ele dependa de outro tipo que você gostaria de definir posteriormente.</span><span class="sxs-lookup"><span data-stu-id="cb087-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="cb087-141">Esse é um erro de compilação, a menos que você defina os tipos de registro a serem recursivos mutuamente.</span><span class="sxs-lookup"><span data-stu-id="cb087-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="cb087-142">A definição de registros recursivos mutuamente é feita com a `and` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="cb087-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="cb087-143">Isso permite que você vincule 2 ou mais tipos de registro juntos.</span><span class="sxs-lookup"><span data-stu-id="cb087-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="cb087-144">Por exemplo, o código a seguir define um `Person` e `Address` tipo como recursivo mutuamente:</span><span class="sxs-lookup"><span data-stu-id="cb087-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="cb087-145">Se você definiu o exemplo anterior sem a `and` palavra-chave, ele não será compilado.</span><span class="sxs-lookup"><span data-stu-id="cb087-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="cb087-146">A `and` palavra-chave é necessária para definições mutuamente recursivas.</span><span class="sxs-lookup"><span data-stu-id="cb087-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="cb087-147">Correspondência de padrões com registros</span><span class="sxs-lookup"><span data-stu-id="cb087-147">Pattern Matching with Records</span></span>

<span data-ttu-id="cb087-148">Os registros podem ser usados com correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="cb087-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="cb087-149">Você pode especificar alguns campos explicitamente e fornecer variáveis para outros campos que serão atribuídos quando ocorrer uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="cb087-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="cb087-150">O exemplo de código a seguir ilustra isso.</span><span class="sxs-lookup"><span data-stu-id="cb087-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="cb087-151">A saída desse código é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="cb087-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a><span data-ttu-id="cb087-152">Registros e membros</span><span class="sxs-lookup"><span data-stu-id="cb087-152">Records and members</span></span>

<span data-ttu-id="cb087-153">Você pode especificar membros em registros assim como você pode com classes.</span><span class="sxs-lookup"><span data-stu-id="cb087-153">You can specify members on records much like you can with classes.</span></span> <span data-ttu-id="cb087-154">Não há suporte para campos.</span><span class="sxs-lookup"><span data-stu-id="cb087-154">There is no support for fields.</span></span> <span data-ttu-id="cb087-155">Uma abordagem comum é definir um `Default` membro estático para a construção de um registro fácil:</span><span class="sxs-lookup"><span data-stu-id="cb087-155">A common approach is to define a `Default` static member for easy record construction:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

<span data-ttu-id="cb087-156">Se você usar um autoidentifier, esse identificador se referirá à instância do registro cujo membro é chamado:</span><span class="sxs-lookup"><span data-stu-id="cb087-156">If you use a self identifier, that identifier refers to the instance of the record whose member is called:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123" }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="cb087-157">Diferenças entre registros e classes</span><span class="sxs-lookup"><span data-stu-id="cb087-157">Differences Between Records and Classes</span></span>

<span data-ttu-id="cb087-158">Os campos de registro diferem dos campos de classe nos quais são expostos automaticamente como propriedades e são usados na criação e cópia de registros.</span><span class="sxs-lookup"><span data-stu-id="cb087-158">Record fields differ from class fields in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="cb087-159">A construção do registro também difere da construção da classe.</span><span class="sxs-lookup"><span data-stu-id="cb087-159">Record construction also differs from class construction.</span></span> <span data-ttu-id="cb087-160">Em um tipo de registro, você não pode definir um construtor.</span><span class="sxs-lookup"><span data-stu-id="cb087-160">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="cb087-161">Em vez disso, a sintaxe de construção descrita neste tópico se aplica.</span><span class="sxs-lookup"><span data-stu-id="cb087-161">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="cb087-162">Classes não têm relação direta entre parâmetros de construtor, campos e propriedades.</span><span class="sxs-lookup"><span data-stu-id="cb087-162">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="cb087-163">Como tipos de União e estrutura, os registros têm semântica de igualdade estrutural.</span><span class="sxs-lookup"><span data-stu-id="cb087-163">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="cb087-164">As classes têm semântica de igualdade de referência.</span><span class="sxs-lookup"><span data-stu-id="cb087-164">Classes have reference equality semantics.</span></span> <span data-ttu-id="cb087-165">O código de exemplo a seguir demonstra isso.</span><span class="sxs-lookup"><span data-stu-id="cb087-165">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="cb087-166">A saída desse código é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="cb087-166">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="cb087-167">Se você escrever o mesmo código com classes, os dois objetos de classe seriam desiguais porque os dois valores representariam dois objetos no heap e apenas os endereços seriam comparados (a menos que o tipo de classe substitua o `System.Object.Equals` método).</span><span class="sxs-lookup"><span data-stu-id="cb087-167">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="cb087-168">Se você precisar de igualdade de referência para registros, adicione o atributo `[<ReferenceEquality>]` acima do registro.</span><span class="sxs-lookup"><span data-stu-id="cb087-168">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb087-169">Veja também</span><span class="sxs-lookup"><span data-stu-id="cb087-169">See also</span></span>

- [<span data-ttu-id="cb087-170">Tipos F#</span><span class="sxs-lookup"><span data-stu-id="cb087-170">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="cb087-171">Classes</span><span class="sxs-lookup"><span data-stu-id="cb087-171">Classes</span></span>](classes.md)
- [<span data-ttu-id="cb087-172">Referência de linguagem F #</span><span class="sxs-lookup"><span data-stu-id="cb087-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cb087-173">Referência-igualdade</span><span class="sxs-lookup"><span data-stu-id="cb087-173">Reference-Equality</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-referenceequalityattribute.html)
- [<span data-ttu-id="cb087-174">Correspondência de padrões</span><span class="sxs-lookup"><span data-stu-id="cb087-174">Pattern Matching</span></span>](pattern-matching.md)
