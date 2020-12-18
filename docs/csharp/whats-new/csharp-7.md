---
title: Novidades no C# 7.0 – Guia do C#
description: Obtenha uma visão geral dos novos recursos na versão 7.0 da linguagem C#.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: c238439b0f435e579d932b3b1eb13e9b0061fa5f
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678229"
---
# <a name="whats-new-in-c-70-through-c-73"></a><span data-ttu-id="6a279-103">O que há de novo no C# 7,0 até C# 7,3</span><span class="sxs-lookup"><span data-stu-id="6a279-103">What's new in C# 7.0 through C# 7.3</span></span>

<span data-ttu-id="6a279-104">O c# 7,0 até o C# 7,3 trouxe vários recursos e aprimoramentos incrementais em sua experiência de desenvolvimento com o C#.</span><span class="sxs-lookup"><span data-stu-id="6a279-104">C# 7.0 through C# 7.3 brought a number of features and incremental improvements to your development experience with C#.</span></span> <span data-ttu-id="6a279-105">Este artigo fornece uma visão geral dos novos recursos de linguagem e opções de compilador.</span><span class="sxs-lookup"><span data-stu-id="6a279-105">This article provides an overview of the new language features and compiler options.</span></span> <span data-ttu-id="6a279-106">As descrições descrevem o comportamento do C# 7,3, que é a versão mais recente com suporte para aplicativos baseados em .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a279-106">The descriptions describe the behavior for C# 7.3, which is the most recent version supported for .NET Framework-based applications.</span></span>

<span data-ttu-id="6a279-107">O elemento de configuração de [seleção de versão de idioma](../language-reference/configure-language-version.md) foi adicionado com C# 7,1, que permite que você especifique a versão do idioma do compilador no arquivo do projeto.</span><span class="sxs-lookup"><span data-stu-id="6a279-107">The [language version selection](../language-reference/configure-language-version.md) configuration element was added with C# 7.1, which enables you to specify the compiler language version in your project file.</span></span>

<span data-ttu-id="6a279-108">O c# 7.0-7.3 adiciona esses recursos e temas à linguagem C#:</span><span class="sxs-lookup"><span data-stu-id="6a279-108">C# 7.0-7.3 adds these features and themes to the C# language:</span></span>

- [<span data-ttu-id="6a279-109">Tuplas e Descartes</span><span class="sxs-lookup"><span data-stu-id="6a279-109">Tuples and discards</span></span>](#tuples-and-discards)
  - <span data-ttu-id="6a279-110">Você pode criar tipos simples e sem nome que contêm vários campos públicos.</span><span class="sxs-lookup"><span data-stu-id="6a279-110">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="6a279-111">Compiladores e ferramentas IDE entendem a semântica desses tipos.</span><span class="sxs-lookup"><span data-stu-id="6a279-111">Compilers and IDE tools understand the semantics of these types.</span></span>
  - <span data-ttu-id="6a279-112">Descartes são variáveis temporárias de somente gravação usadas em atribuições quando o valor atribuído não tem importância.</span><span class="sxs-lookup"><span data-stu-id="6a279-112">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="6a279-113">Eles são mais úteis ao desconstruir tuplas e tipos definidos pelo usuário, bem como ao chamar métodos com parâmetros `out`.</span><span class="sxs-lookup"><span data-stu-id="6a279-113">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
- [<span data-ttu-id="6a279-114">Correspondência de padrões</span><span class="sxs-lookup"><span data-stu-id="6a279-114">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="6a279-115">Você pode criar a lógica de ramificação com base em tipos e valores arbitrários dos membros desses tipos.</span><span class="sxs-lookup"><span data-stu-id="6a279-115">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
- [<span data-ttu-id="6a279-116">`async``Main`método</span><span class="sxs-lookup"><span data-stu-id="6a279-116">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="6a279-117">O ponto de entrada para um aplicativo pode ter o modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="6a279-117">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="6a279-118">Funções locais</span><span class="sxs-lookup"><span data-stu-id="6a279-118">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="6a279-119">Você pode aninhar funções dentro de outras funções para limitar seu escopo e visibilidade.</span><span class="sxs-lookup"><span data-stu-id="6a279-119">You can nest functions inside other functions to limit their scope and visibility.</span></span>
- [<span data-ttu-id="6a279-120">Mais membros aptos para expressão</span><span class="sxs-lookup"><span data-stu-id="6a279-120">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="6a279-121">A lista de membros que podem ser criados usando expressões cresceu.</span><span class="sxs-lookup"><span data-stu-id="6a279-121">The list of members that can be authored using expressions has grown.</span></span>
- [<span data-ttu-id="6a279-122">`throw` Expressões</span><span class="sxs-lookup"><span data-stu-id="6a279-122">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="6a279-123">Gere exceções em constructos de código que anteriormente não eram permitidos devido ao fato de `throw` ser uma instrução.</span><span class="sxs-lookup"><span data-stu-id="6a279-123">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
- [<span data-ttu-id="6a279-124">`default` expressões literais</span><span class="sxs-lookup"><span data-stu-id="6a279-124">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="6a279-125">Use expressões literais padrão em expressões de valor padrão quando o tipo de destino pode ser inferido.</span><span class="sxs-lookup"><span data-stu-id="6a279-125">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="6a279-126">Aprimoramentos da sintaxe de literais numéricos</span><span class="sxs-lookup"><span data-stu-id="6a279-126">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="6a279-127">Novos tokens aprimoram a legibilidade para constantes numéricas.</span><span class="sxs-lookup"><span data-stu-id="6a279-127">New tokens improve readability for numeric constants.</span></span>
- [<span data-ttu-id="6a279-128">`out` as</span><span class="sxs-lookup"><span data-stu-id="6a279-128">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="6a279-129">Declare valores `out` embutidos como argumentos para o método em que eles são usados.</span><span class="sxs-lookup"><span data-stu-id="6a279-129">You can declare `out` values inline as arguments to the method where they're used.</span></span>
- [<span data-ttu-id="6a279-130">Argumentos nomeados que não estejam à direita</span><span class="sxs-lookup"><span data-stu-id="6a279-130">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="6a279-131">Os argumentos nomeados podem ser seguidos por argumentos posicionais.</span><span class="sxs-lookup"><span data-stu-id="6a279-131">Named arguments can be followed by positional arguments.</span></span>
- [<span data-ttu-id="6a279-132">`private protected` modificador de acesso</span><span class="sxs-lookup"><span data-stu-id="6a279-132">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="6a279-133">O modificador de acesso `private protected` permite o acesso a classes derivadas no mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="6a279-133">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
- [<span data-ttu-id="6a279-134">Resolução de sobrecarga aprimorada</span><span class="sxs-lookup"><span data-stu-id="6a279-134">Improved overload resolution</span></span>](#improved-overload-candidates)
  - <span data-ttu-id="6a279-135">Novas regras para resolver ambiguidade na resolução de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="6a279-135">New rules to resolve overload resolution ambiguity.</span></span>
- [<span data-ttu-id="6a279-136">Técnicas para escrever código eficiente seguro</span><span class="sxs-lookup"><span data-stu-id="6a279-136">Techniques for writing safe efficient code</span></span>](#enabling-more-efficient-safe-code)
  - <span data-ttu-id="6a279-137">Uma combinação de aprimoramentos de sintaxe que permitem trabalhar com tipos de valor usando a semântica de referência.</span><span class="sxs-lookup"><span data-stu-id="6a279-137">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>

<span data-ttu-id="6a279-138">Por fim, o compilador tem novas opções:</span><span class="sxs-lookup"><span data-stu-id="6a279-138">Finally, the compiler has new options:</span></span>

- <span data-ttu-id="6a279-139">`-refout` e `-refonly` essa [geração de assembly de referência](#reference-assembly-generation)de controle.</span><span class="sxs-lookup"><span data-stu-id="6a279-139">`-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>
- <span data-ttu-id="6a279-140">`-publicsign` para habilitar a assinatura de Software de código aberto (OSS) de assemblies.</span><span class="sxs-lookup"><span data-stu-id="6a279-140">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="6a279-141">`-pathmap` para fornecer um mapeamento para diretórios de origem.</span><span class="sxs-lookup"><span data-stu-id="6a279-141">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="6a279-142">O restante deste artigo fornece uma visão geral de cada recurso.</span><span class="sxs-lookup"><span data-stu-id="6a279-142">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="6a279-143">Para cada recurso, você aprenderá o raciocínio por trás dele e a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="6a279-143">For each feature, you'll learn the reasoning behind it and the syntax.</span></span> <span data-ttu-id="6a279-144">Você pode explorar esses recursos em seu ambiente usando a ferramenta global `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="6a279-144">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="6a279-145">Instale a ferramenta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="6a279-145">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="6a279-146">Clone o repositório [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="6a279-146">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="6a279-147">Definir o diretório atual do subdiretório *csharp7* para o repositório *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="6a279-147">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="6a279-148">Execute `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="6a279-148">Run `dotnet try`.</span></span>

## <a name="tuples-and-discards"></a><span data-ttu-id="6a279-149">Tuplas e Descartes</span><span class="sxs-lookup"><span data-stu-id="6a279-149">Tuples and discards</span></span>

<span data-ttu-id="6a279-150">O C# fornece uma sintaxe avançada para classes e structs que são usados para explicar a intenção do design.</span><span class="sxs-lookup"><span data-stu-id="6a279-150">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="6a279-151">Mas, às vezes, essa sintaxe avançada requer trabalho adicional com poucas vantagens.</span><span class="sxs-lookup"><span data-stu-id="6a279-151">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="6a279-152">Geralmente, você pode escrever métodos que precisam de uma estrutura simples que contém mais de um elemento de dados.</span><span class="sxs-lookup"><span data-stu-id="6a279-152">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="6a279-153">Para dar suporte a esses cenários foram adicionadas *tuplas* ao C#.</span><span class="sxs-lookup"><span data-stu-id="6a279-153">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="6a279-154">As tuplas são estruturas de dados leves que contêm vários campos para representar os membros de dados.</span><span class="sxs-lookup"><span data-stu-id="6a279-154">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span> <span data-ttu-id="6a279-155">Os campos não são validados e você não pode definir seus próprios métodos.</span><span class="sxs-lookup"><span data-stu-id="6a279-155">The fields aren't validated, and you can't define your own methods.</span></span> <span data-ttu-id="6a279-156">Os tipos de tupla C# dão suporte a `==` e `!=` .</span><span class="sxs-lookup"><span data-stu-id="6a279-156">C# tuple types support `==` and `!=`.</span></span> <span data-ttu-id="6a279-157">Para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6a279-157">For more information.</span></span>

> [!NOTE]
> <span data-ttu-id="6a279-158">As tuplas estavam disponíveis antes do C# 7.0, mas elas eram ineficientes e não tinham nenhum suporte de linguagem.</span><span class="sxs-lookup"><span data-stu-id="6a279-158">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span> <span data-ttu-id="6a279-159">Isso significava que os elementos de tupla só podiam ser referenciados como `Item1`, `Item2` e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="6a279-159">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="6a279-160">O C# 7.0 introduz o suporte de linguagem para tuplas, que permite nomes semânticos para os campos de uma tupla, usando tipos de tupla novos e mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="6a279-160">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="6a279-161">Você pode criar uma tupla atribuindo um valor a cada membro e, opcionalmente, fornecendo nomes semânticos para cada um dos membros da tupla:</span><span class="sxs-lookup"><span data-stu-id="6a279-161">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="6a279-162">A tupla `namedLetters` contém campos denominados `Alpha` e `Beta`.</span><span class="sxs-lookup"><span data-stu-id="6a279-162">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="6a279-163">Esses nomes existem somente no momento da compilação e não são preservados, por exemplo, ao inspecionar a tupla usando reflexão em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="6a279-163">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at run time.</span></span>

<span data-ttu-id="6a279-164">Em uma atribuição de tupla, você também pode especificar os nomes dos campos no lado direito da atribuição:</span><span class="sxs-lookup"><span data-stu-id="6a279-164">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="6a279-165">Pode haver ocasiões em que você deseja descompactar os membros de uma tupla que foram retornados de um método.</span><span class="sxs-lookup"><span data-stu-id="6a279-165">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="6a279-166">Você pode fazer isso declarando variáveis separadas para cada um dos valores na tupla.</span><span class="sxs-lookup"><span data-stu-id="6a279-166">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="6a279-167">Essa descompactação é chamada *desconstrução* da tupla:</span><span class="sxs-lookup"><span data-stu-id="6a279-167">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="6a279-168">Você também pode fornecer uma desconstrução semelhante para qualquer tipo no .NET.</span><span class="sxs-lookup"><span data-stu-id="6a279-168">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="6a279-169">Escreva um método `Deconstruct` como um membro da classe.</span><span class="sxs-lookup"><span data-stu-id="6a279-169">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="6a279-170">esse método `Deconstruct` fornece um conjunto de argumentos `out` para cada uma das propriedades que você deseja extrair.</span><span class="sxs-lookup"><span data-stu-id="6a279-170">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="6a279-171">Considere essa classe `Point` que fornece um método desconstrutor que extrai as coordenadas `X` e `Y`:</span><span class="sxs-lookup"><span data-stu-id="6a279-171">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="6a279-172">Extraia os campos individuais atribuindo um `Point` a uma tupla:</span><span class="sxs-lookup"><span data-stu-id="6a279-172">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="6a279-173">Muitas vezes, quando você Inicializa uma tupla, as variáveis usadas para o lado direito da atribuição são as mesmas que os nomes desejados para os elementos de tupla: os nomes dos elementos de tupla podem ser inferidos das variáveis usadas para inicializar a tupla:</span><span class="sxs-lookup"><span data-stu-id="6a279-173">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements: The names of tuple elements can be inferred from the variables used to initialize the tuple:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="6a279-174">Você pode saber mais sobre esse recurso no artigo [tipos de tupla](../language-reference/builtin-types/value-tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="6a279-174">You can learn more about this feature in the [Tuple types](../language-reference/builtin-types/value-tuples.md) article.</span></span>

<span data-ttu-id="6a279-175">Geralmente, ao desconstruir uma tupla ou chamar um método com parâmetros `out`, você é forçado a definir uma variável cujo valor não é importante e você não pretende usar.</span><span class="sxs-lookup"><span data-stu-id="6a279-175">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="6a279-176">O C# adiciona suporte para *descartes* para lidar com esse cenário.</span><span class="sxs-lookup"><span data-stu-id="6a279-176">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="6a279-177">Um descarte é uma variável de somente gravação cujo nome é `_` (o caractere de sublinhado); você pode atribuir todos os valores que você pretende descartar à variável única.</span><span class="sxs-lookup"><span data-stu-id="6a279-177">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="6a279-178">Um descarte é como uma variável não atribuída. Além da instrução de atribuição, o descarte não pode ser usado no código.</span><span class="sxs-lookup"><span data-stu-id="6a279-178">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="6a279-179">Os descartes são compatíveis com os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="6a279-179">Discards are supported in the following scenarios:</span></span>

- <span data-ttu-id="6a279-180">Ao desconstruir tuplas ou tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="6a279-180">When deconstructing tuples or user-defined types.</span></span>
- <span data-ttu-id="6a279-181">Ao chamar métodos com parâmetros [out](../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-181">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="6a279-182">Em uma operação de correspondência de padrões com as instruções [is](../language-reference/keywords/is.md) e [switch](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-182">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
- <span data-ttu-id="6a279-183">Como um identificador autônomo quando você deseja identificar explicitamente o valor de uma atribuição como um descarte.</span><span class="sxs-lookup"><span data-stu-id="6a279-183">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="6a279-184">O exemplo a seguir define um método `QueryCityDataForYears` que retorna uma tupla de 6 que contém dados de dois anos diferentes para uma cidade.</span><span class="sxs-lookup"><span data-stu-id="6a279-184">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="6a279-185">A chamada do método no exemplo é relacionada somente com os dois valores de população retornados pelo método e, por isso, trata os valores restantes na tupla como descartes ao desconstruir a tupla.</span><span class="sxs-lookup"><span data-stu-id="6a279-185">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="6a279-186">Para obter mais informações, consulte [Descartes](../discards.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-186">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="6a279-187">Correspondência de padrões</span><span class="sxs-lookup"><span data-stu-id="6a279-187">Pattern matching</span></span>

<span data-ttu-id="6a279-188">*Correspondência de padrões* é um conjunto de recursos que permitem novas maneiras de expressar o fluxo de controle em seu código.</span><span class="sxs-lookup"><span data-stu-id="6a279-188">*Pattern matching* is a set of features that enable new ways to express control flow in your code.</span></span> <span data-ttu-id="6a279-189">Você pode testar variáveis para seus tipos, valores ou os valores de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="6a279-189">You can test variables for their type, values or the values of their properties.</span></span> <span data-ttu-id="6a279-190">Essas técnicas criam um fluxo de código mais legível.</span><span class="sxs-lookup"><span data-stu-id="6a279-190">These techniques create more readable code flow.</span></span>

<span data-ttu-id="6a279-191">A correspondência de padrões tem suporte a expressões `is` e `switch`.</span><span class="sxs-lookup"><span data-stu-id="6a279-191">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="6a279-192">Cada uma delas permite inspecionar um objeto e suas propriedades para determinar se esse objeto satisfaz o padrão procurado.</span><span class="sxs-lookup"><span data-stu-id="6a279-192">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="6a279-193">Você usa a palavra-chave `when` para especificar regras adicionais para o padrão.</span><span class="sxs-lookup"><span data-stu-id="6a279-193">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="6a279-194">A `is` expressão de padrão estende o [ `is` operador](../language-reference/keywords/is.md#pattern-matching-with-is) familiar para consultar um objeto sobre seu tipo e atribuir o resultado em uma instrução.</span><span class="sxs-lookup"><span data-stu-id="6a279-194">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="6a279-195">O seguinte código verifica se uma variável é um `int` e, nesse caso, adiciona-a à soma atual:</span><span class="sxs-lookup"><span data-stu-id="6a279-195">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="6a279-196">O pequeno exemplo anterior demonstra as melhorias na expressão `is`.</span><span class="sxs-lookup"><span data-stu-id="6a279-196">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="6a279-197">Você pode realizar o teste nos tipos de valor, bem como nos tipos de referência, e atribuir o resultado com êxito a uma nova variável do tipo correto.</span><span class="sxs-lookup"><span data-stu-id="6a279-197">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="6a279-198">A expressão de correspondência switch tem uma sintaxe conhecida, baseada na instrução `switch` que já faz parte da linguagem C#.</span><span class="sxs-lookup"><span data-stu-id="6a279-198">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="6a279-199">A instrução switch atualizada tem vários novos constructos:</span><span class="sxs-lookup"><span data-stu-id="6a279-199">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="6a279-200">O tipo controlador de uma expressão `switch` não está mais restrito a tipos integrais, tipos `Enum`, `string` ou a um tipo que permite valor nulo correspondente a um desses tipos.</span><span class="sxs-lookup"><span data-stu-id="6a279-200">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="6a279-201">Qualquer tipo pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="6a279-201">Any type may be used.</span></span>
- <span data-ttu-id="6a279-202">Teste o tipo da expressão `switch` em cada rótulo `case`.</span><span class="sxs-lookup"><span data-stu-id="6a279-202">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="6a279-203">Assim como ocorre com a expressão `is`, você pode atribuir uma nova variável a esse tipo.</span><span class="sxs-lookup"><span data-stu-id="6a279-203">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="6a279-204">Adicione uma cláusula `when` para testar mais condições de teste nessa variável.</span><span class="sxs-lookup"><span data-stu-id="6a279-204">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="6a279-205">A ordem dos rótulos `case` agora é importante.</span><span class="sxs-lookup"><span data-stu-id="6a279-205">The order of `case` labels is now important.</span></span> <span data-ttu-id="6a279-206">O primeiro branch para correspondência é executado; os outros são ignorados.</span><span class="sxs-lookup"><span data-stu-id="6a279-206">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="6a279-207">O seguinte código demonstra esses novos recursos:</span><span class="sxs-lookup"><span data-stu-id="6a279-207">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="6a279-208">`case 0:` é o padrão de constante conhecido.</span><span class="sxs-lookup"><span data-stu-id="6a279-208">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="6a279-209">`case IEnumerable<int> childSequence:` é um padrão de tipo.</span><span class="sxs-lookup"><span data-stu-id="6a279-209">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="6a279-210">`case int n when n > 0:` é um padrão de tipo com uma condição `when` adicional.</span><span class="sxs-lookup"><span data-stu-id="6a279-210">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="6a279-211">`case null:` é o padrão de nulo.</span><span class="sxs-lookup"><span data-stu-id="6a279-211">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="6a279-212">`default:` é o caso padrão conhecido.</span><span class="sxs-lookup"><span data-stu-id="6a279-212">`default:` is the familiar default case.</span></span>

<span data-ttu-id="6a279-213">A partir do C# 7.1, a expressão de padrão para o padrão de tipo `is` e `switch` pode ter o tipo de um parâmetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="6a279-213">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="6a279-214">Isso pode ser mais útil ao verificar tipos que podem ser do tipo `struct` ou `class` e você deseja evitar conversão boxing.</span><span class="sxs-lookup"><span data-stu-id="6a279-214">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

<span data-ttu-id="6a279-215">Saiba mais sobre a correspondência de padrões em [Correspondência de padrões em C#](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-215">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="async-main"></a><span data-ttu-id="6a279-216">Async main</span><span class="sxs-lookup"><span data-stu-id="6a279-216">Async main</span></span>

<span data-ttu-id="6a279-217">Um método *async main* permite que você use `await` no método `Main`.</span><span class="sxs-lookup"><span data-stu-id="6a279-217">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="6a279-218">Anteriormente, você precisava escrever:</span><span class="sxs-lookup"><span data-stu-id="6a279-218">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="6a279-219">Agora, você pode escrever:</span><span class="sxs-lookup"><span data-stu-id="6a279-219">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="6a279-220">Se o programa não retorna um código de saída, declare um método `Main` que retorna um <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="6a279-220">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="6a279-221">Leia mais sobre os detalhes no tópico [async main](../programming-guide/main-and-command-args/index.md) no guia de programação.</span><span class="sxs-lookup"><span data-stu-id="6a279-221">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="local-functions"></a><span data-ttu-id="6a279-222">Funções locais</span><span class="sxs-lookup"><span data-stu-id="6a279-222">Local functions</span></span>

<span data-ttu-id="6a279-223">Muitos designs para classes incluem métodos que são chamados de apenas um local.</span><span class="sxs-lookup"><span data-stu-id="6a279-223">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="6a279-224">Esses métodos privados adicionais mantêm cada método pequeno e focado.</span><span class="sxs-lookup"><span data-stu-id="6a279-224">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="6a279-225">As *funções locais* permitem que você declare métodos dentro do contexto de outro método.</span><span class="sxs-lookup"><span data-stu-id="6a279-225">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="6a279-226">Funções locais tornam mais fácil para os leitores da classe verem que o método local é chamado apenas do contexto em que é declarado.</span><span class="sxs-lookup"><span data-stu-id="6a279-226">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="6a279-227">Há dois casos de uso muito comuns para funções locais: métodos iteradores públicos e métodos assíncronos públicos.</span><span class="sxs-lookup"><span data-stu-id="6a279-227">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="6a279-228">Ambos os tipos de métodos de geram código que relata os erros mais tarde do que os programadores podem esperar.</span><span class="sxs-lookup"><span data-stu-id="6a279-228">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="6a279-229">Em métodos iteradores, as exceções são observadas apenas ao chamar o código que enumera a sequência retornada.</span><span class="sxs-lookup"><span data-stu-id="6a279-229">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="6a279-230">Em métodos assíncronos, as exceções são observadas apenas quando a `Task` retornada é aguardada.</span><span class="sxs-lookup"><span data-stu-id="6a279-230">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="6a279-231">O seguinte exemplo demonstra a validação de parâmetro de separação da implementação do iterador usando uma função local:</span><span class="sxs-lookup"><span data-stu-id="6a279-231">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="6a279-232">A mesma técnica pode ser empregada com métodos `async` para garantir que as exceções decorrentes da validação de argumento sejam lançadas antes de o trabalho assíncrono começar:</span><span class="sxs-lookup"><span data-stu-id="6a279-232">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="6a279-233">Agora há suporte para esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="6a279-233">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="6a279-234">O atributo `SomeThingAboutFieldAttribute` é aplicado ao campo de suporte gerado pelo compilador para `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="6a279-234">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="6a279-235">Para saber mais, confira [atributos](../programming-guide/concepts/attributes/index.md) no guia de programação em C#.</span><span class="sxs-lookup"><span data-stu-id="6a279-235">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

> [!NOTE]
> <span data-ttu-id="6a279-236">Alguns dos designs com suporte das funções locais também podem ser realizados usando *expressões lambda*.</span><span class="sxs-lookup"><span data-stu-id="6a279-236">Some of the designs that are supported by local functions can also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="6a279-237">Para obter mais informações, consulte [funções locais versus expressões lambda](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span><span class="sxs-lookup"><span data-stu-id="6a279-237">For more information, see [Local functions vs. lambda expressions](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="6a279-238">Mais membros aptos para expressão</span><span class="sxs-lookup"><span data-stu-id="6a279-238">More expression-bodied members</span></span>

<span data-ttu-id="6a279-239">O C# 6 introduziu Membros Expression-apto para para funções membro e propriedades somente leitura.</span><span class="sxs-lookup"><span data-stu-id="6a279-239">C# 6 introduced expression-bodied members for member functions and read-only properties.</span></span> <span data-ttu-id="6a279-240">O C# 7.0 expande os membros permitidos que podem ser implementados como expressões.</span><span class="sxs-lookup"><span data-stu-id="6a279-240">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="6a279-241">No C# 7.0, você pode implementar *construtores*, *finalizadores* e acessadores `get` e `set` em *propriedades* e *indexadores*.</span><span class="sxs-lookup"><span data-stu-id="6a279-241">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="6a279-242">O código a seguir mostra exemplos de cada um:</span><span class="sxs-lookup"><span data-stu-id="6a279-242">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="6a279-243">Este exemplo não precisa de um finalizador, mas ele é mostrado para demonstrar a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="6a279-243">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="6a279-244">Você não deve implementar um finalizador em sua classe a menos que seja necessário para liberar recursos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="6a279-244">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="6a279-245">Você também deve considerar o uso da classe <xref:System.Runtime.InteropServices.SafeHandle> em vez de gerenciar recursos não gerenciados diretamente.</span><span class="sxs-lookup"><span data-stu-id="6a279-245">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="6a279-246">Esses novos locais para membros aptos para expressão representam uma etapa importante para a linguagem C#: esses recursos foram implementados por membros da comunidade trabalhando no projeto [Roslyn](https://github.com/dotnet/Roslyn) de software livre.</span><span class="sxs-lookup"><span data-stu-id="6a279-246">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="6a279-247">A alteração de um método para um membro de corpo da expressão é uma [alteração compatível com binário](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-247">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="6a279-248">Expressões throw</span><span class="sxs-lookup"><span data-stu-id="6a279-248">Throw expressions</span></span>

<span data-ttu-id="6a279-249">No C#, `throw` sempre foi uma instrução.</span><span class="sxs-lookup"><span data-stu-id="6a279-249">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="6a279-250">Como `throw` é uma instrução, não uma expressão, havia constructos do C# em que não era possível usá-la.</span><span class="sxs-lookup"><span data-stu-id="6a279-250">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="6a279-251">Eles incluíam expressões condicionais, expressões de união nulas e algumas expressões lambda.</span><span class="sxs-lookup"><span data-stu-id="6a279-251">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="6a279-252">A adição de membros aptos para expressão inclui mais locais em que as expressões `throw` seriam úteis.</span><span class="sxs-lookup"><span data-stu-id="6a279-252">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="6a279-253">Para que você possa escrever qualquer um desses construtos, o C# 7.0 apresenta [*expressões throw*](../language-reference/keywords/throw.md#the-throw-expression).</span><span class="sxs-lookup"><span data-stu-id="6a279-253">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="6a279-254">Essa adição facilita a escrita de um código mais baseado em expressão.</span><span class="sxs-lookup"><span data-stu-id="6a279-254">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="6a279-255">Você não precisa de instruções adicionais para a verificação de erros.</span><span class="sxs-lookup"><span data-stu-id="6a279-255">You don't need additional statements for error checking.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="6a279-256">Expressões literais padrão</span><span class="sxs-lookup"><span data-stu-id="6a279-256">Default literal expressions</span></span>

<span data-ttu-id="6a279-257">Expressões literais padrão são uma melhoria das expressões de valor padrão.</span><span class="sxs-lookup"><span data-stu-id="6a279-257">Default literal expressions are an enhancement to default value expressions.</span></span> <span data-ttu-id="6a279-258">Essas expressões inicializam uma variável com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="6a279-258">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="6a279-259">Nos casos em que você anteriormente escrevia:</span><span class="sxs-lookup"><span data-stu-id="6a279-259">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="6a279-260">Agora você pode omitir o tipo no lado direito da inicialização:</span><span class="sxs-lookup"><span data-stu-id="6a279-260">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="6a279-261">Para saber mais, confira a seção [Literais padrão](../language-reference/operators/default.md#default-literal) do artigo do [operador padrão](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-261">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="6a279-262">Aprimoramentos da sintaxe de literais numéricos</span><span class="sxs-lookup"><span data-stu-id="6a279-262">Numeric literal syntax improvements</span></span>

<span data-ttu-id="6a279-263">A leitura incorreta das constantes numéricas pode fazer com que seja difícil entender o código ao lê-lo pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6a279-263">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="6a279-264">Bitmasks ou outros valores simbólicos são propensos a equívocos.</span><span class="sxs-lookup"><span data-stu-id="6a279-264">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="6a279-265">O C# 7.0 inclui dois novos recursos para a escrita de números da maneira mais legível possível para o uso pretendido: *literais binários* e *separadores de dígito*.</span><span class="sxs-lookup"><span data-stu-id="6a279-265">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="6a279-266">Para ocasiões em que você estiver criando bitmasks ou sempre que uma representação binária de um número tornar o código mais legível, escreva esse número em binário:</span><span class="sxs-lookup"><span data-stu-id="6a279-266">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="6a279-267">O `0b` no início da constante indica que o número é escrito como um número binário.</span><span class="sxs-lookup"><span data-stu-id="6a279-267">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="6a279-268">Os números binários podem chegar longos e, em geral, é mais fácil ver os padrões de bit introduzindo o `_` como um separador de dígito, conforme mostrado na constante binária no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="6a279-268">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown in the binary constant in the preceding example.</span></span> <span data-ttu-id="6a279-269">O separador de dígitos pode aparecer em qualquer lugar na constante.</span><span class="sxs-lookup"><span data-stu-id="6a279-269">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="6a279-270">Para números de base 10, é comum usá-lo como separador de milhar.</span><span class="sxs-lookup"><span data-stu-id="6a279-270">For base 10 numbers, it is common to use it as a thousands separator.</span></span> <span data-ttu-id="6a279-271">Os literais numéricos hexadecimais e binários podem começar com um `_` :</span><span class="sxs-lookup"><span data-stu-id="6a279-271">Hex and binary numeric literals may begin with an `_`:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="6a279-272">O separador de dígito pode ser usado com os tipos `decimal`, `float` e `double` também:</span><span class="sxs-lookup"><span data-stu-id="6a279-272">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="6a279-273">Juntos, você pode declarar constantes numéricas com muito mais facilidade de leitura.</span><span class="sxs-lookup"><span data-stu-id="6a279-273">Taken together, you can declare numeric constants with much more readability.</span></span>

## <a name="out-variables"></a><span data-ttu-id="6a279-274">Variáveis `out`</span><span class="sxs-lookup"><span data-stu-id="6a279-274">`out` variables</span></span>

<span data-ttu-id="6a279-275">A sintaxe existente que dá suporte a `out` parâmetros foi aprimorada no C# 7.</span><span class="sxs-lookup"><span data-stu-id="6a279-275">The existing syntax that supports `out` parameters has been improved in C# 7.</span></span> <span data-ttu-id="6a279-276">Agora você pode declarar variáveis `out` na lista de argumentos de uma chamada de método, em vez de escrever uma instrução de declaração separada:</span><span class="sxs-lookup"><span data-stu-id="6a279-276">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="6a279-277">Talvez você queira especificar o tipo da `out` variável para fins de clareza, conforme mostrado no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="6a279-277">You may want to specify the type of the `out` variable for clarity, as shown in the preceding example.</span></span> <span data-ttu-id="6a279-278">No entanto, a linguagem dá suporte ao uso de variável local de tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="6a279-278">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- <span data-ttu-id="6a279-279">O código é mais fácil de ler.</span><span class="sxs-lookup"><span data-stu-id="6a279-279">The code is easier to read.</span></span>
  - <span data-ttu-id="6a279-280">Você declara a variável out onde você a usa, não em uma linha de código anterior.</span><span class="sxs-lookup"><span data-stu-id="6a279-280">You declare the out variable where you use it, not on a preceding line of code.</span></span>
- <span data-ttu-id="6a279-281">Não é necessário atribuir um valor inicial.</span><span class="sxs-lookup"><span data-stu-id="6a279-281">No need to assign an initial value.</span></span>
  - <span data-ttu-id="6a279-282">Ao declarar a variável `out` no local em que ela é usada em uma chamada de método, você não pode usá-la acidentalmente antes de ela ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="6a279-282">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="6a279-283">A sintaxe adicionada no C# 7.0 para permitir declarações de variável `out` foi estendida para incluir inicializadores de campo, inicializadores de propriedade, inicializadores de construtor e cláusulas de consulta.</span><span class="sxs-lookup"><span data-stu-id="6a279-283">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="6a279-284">Ela permite código como no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="6a279-284">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="6a279-285">Argumentos nomeados que não estejam à direita</span><span class="sxs-lookup"><span data-stu-id="6a279-285">Non-trailing named arguments</span></span>

<span data-ttu-id="6a279-286">Agora as chamadas de método podem usar argumentos nomeados que precedem argumentos posicionais quando esses argumentos nomeados estão nas posições corretas.</span><span class="sxs-lookup"><span data-stu-id="6a279-286">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="6a279-287">Para obter mais informações, consulte [argumentos nomeados e opcionais](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-287">For more information, see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="private-protected-access-modifier"></a><span data-ttu-id="6a279-288">modificador de acesso *protegido privado*</span><span class="sxs-lookup"><span data-stu-id="6a279-288">*private protected* access modifier</span></span>

<span data-ttu-id="6a279-289">Um novo modificador de acesso composto: `private protected` indica que um membro pode ser acessado pela classe que o contém ou por classes derivadas que são declaradas no mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="6a279-289">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="6a279-290">Enquanto que `protected internal` permite o acesso por classes derivadas ou classes que estejam no mesmo assembly, o `private protected` limita o acesso a tipos derivados declarados no mesmo assembly.</span><span class="sxs-lookup"><span data-stu-id="6a279-290">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="6a279-291">Para obter mais informações, consulte [modificadores de acesso](../language-reference/keywords/access-modifiers.md) na referência de linguagem.</span><span class="sxs-lookup"><span data-stu-id="6a279-291">For more information, see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="improved-overload-candidates"></a><span data-ttu-id="6a279-292">Candidatos de sobrecarga aprimorados</span><span class="sxs-lookup"><span data-stu-id="6a279-292">Improved overload candidates</span></span>

<span data-ttu-id="6a279-293">Em cada versão, as regras de resolução de sobrecarga são atualizadas para resolver situações em que as chamadas de método ambíguas têm uma opção "óbvia".</span><span class="sxs-lookup"><span data-stu-id="6a279-293">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="6a279-294">Esta versão adiciona três novas regras para ajudar o compilador a escolher a opção óbvia:</span><span class="sxs-lookup"><span data-stu-id="6a279-294">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="6a279-295">Quando um grupo de métodos contém membros de instância e estáticos, o compilador descartará os membros da instância se o método tiver sido chamado sem um receptor ou contexto de instância.</span><span class="sxs-lookup"><span data-stu-id="6a279-295">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="6a279-296">O compilador descartará os membros estáticos se o método tiver sido chamado com um receptor de instância.</span><span class="sxs-lookup"><span data-stu-id="6a279-296">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="6a279-297">Quando não há receptor, o compilador inclui apenas membros estáticos em um contexto estático, caso contrário, membros estáticos e de instância.</span><span class="sxs-lookup"><span data-stu-id="6a279-297">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="6a279-298">Quando o receptor é ambiguamente uma instância ou um tipo, o compilador inclui ambos.</span><span class="sxs-lookup"><span data-stu-id="6a279-298">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="6a279-299">Um contexto estático, em que não é possível usar um receptor de instância `this` implícito, inclui o corpo de membros em que nenhum `this` é definido, como membros estáticos, bem como locais onde `this` não pode ser usado, como inicializadores de campo e inicializadores de construtor.</span><span class="sxs-lookup"><span data-stu-id="6a279-299">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="6a279-300">Quando um grupo de métodos contém alguns métodos genéricos cujos argumentos de tipo não satisfazem suas restrições, esses membros são removidos do conjunto de candidatos.</span><span class="sxs-lookup"><span data-stu-id="6a279-300">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="6a279-301">Para uma conversão de grupo de métodos, os métodos candidatos cujo tipo de retorno não corresponda ao tipo de retorno do delegado são removidos do conjunto.</span><span class="sxs-lookup"><span data-stu-id="6a279-301">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="6a279-302">Você notará essa mudança somente porque encontrará menos erros de compilador para sobrecargas de métodos ambíguos quando tiver certeza de qual método é melhor.</span><span class="sxs-lookup"><span data-stu-id="6a279-302">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="6a279-303">Como habilitar código seguro mais eficiente</span><span class="sxs-lookup"><span data-stu-id="6a279-303">Enabling more efficient safe code</span></span>

<span data-ttu-id="6a279-304">Você deve ser capaz de escrever um código C# de forma segurança que seja executado tão bem quanto o código não seguro.</span><span class="sxs-lookup"><span data-stu-id="6a279-304">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="6a279-305">O código seguro evita classes de erros, como estouros de buffer, ponteiros perdidos e outros erros de acesso à memória.</span><span class="sxs-lookup"><span data-stu-id="6a279-305">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="6a279-306">Esses novos recursos expandem as capacidades do código seguro verificável.</span><span class="sxs-lookup"><span data-stu-id="6a279-306">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="6a279-307">Tente escrever mais partes do seu código usando construções seguras.</span><span class="sxs-lookup"><span data-stu-id="6a279-307">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="6a279-308">Esses recursos tornam isso mais fácil.</span><span class="sxs-lookup"><span data-stu-id="6a279-308">These features make that easier.</span></span>

<span data-ttu-id="6a279-309">Os novos recursos a seguir são compatíveis com o tema de melhor desempenho para código seguro:</span><span class="sxs-lookup"><span data-stu-id="6a279-309">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="6a279-310">Você pode acessar campos fixos sem fixação.</span><span class="sxs-lookup"><span data-stu-id="6a279-310">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="6a279-311">Você pode reatribuir variáveis locais `ref`.</span><span class="sxs-lookup"><span data-stu-id="6a279-311">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="6a279-312">Você pode usar inicializadores em matrizes `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="6a279-312">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="6a279-313">Você pode usar instruções `fixed` com qualquer tipo compatível com um padrão.</span><span class="sxs-lookup"><span data-stu-id="6a279-313">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="6a279-314">Você pode usar restrições genéricas adicionais.</span><span class="sxs-lookup"><span data-stu-id="6a279-314">You can use additional generic constraints.</span></span>
- <span data-ttu-id="6a279-315">O modificador `in` em parâmetros, para especificar que um argumento é passado por referência, mas não modificado pelo método chamado.</span><span class="sxs-lookup"><span data-stu-id="6a279-315">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="6a279-316">Adicionar o modificador `in` a um argumento é uma [alteração compatível com a origem](version-update-considerations.md#source-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-316">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="6a279-317">O modificador `ref readonly` nos retornos de método, para indicar que um método retorna seu valor por referência, mas não permite gravações nesse objeto.</span><span class="sxs-lookup"><span data-stu-id="6a279-317">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="6a279-318">Adicionar o modificador `ref readonly` é uma [alteração compatível com a origem](version-update-considerations.md#source-compatible-changes) se o retorno é atribuído a um valor.</span><span class="sxs-lookup"><span data-stu-id="6a279-318">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="6a279-319">Adicionar o modificador `readonly` a uma instrução de retorno `ref` existente é uma [alteração incompatível](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-319">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="6a279-320">Ela requer que os chamadores atualizem a declaração de `ref` variáveis locais para incluir o modificador `readonly`.</span><span class="sxs-lookup"><span data-stu-id="6a279-320">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="6a279-321">A declaração `readonly struct`, para indicar que uma struct é imutável e deve ser passado como um parâmetro `in` para seus métodos de membro.</span><span class="sxs-lookup"><span data-stu-id="6a279-321">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="6a279-322">Adicionar o modificador `readonly` a uma declaração struct existente é uma [alteração compatível com binário](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-322">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="6a279-323">A declaração `ref struct`, para indicar que um tipo de struct acessa a memória gerenciada diretamente e deve sempre ser alocado por pilha.</span><span class="sxs-lookup"><span data-stu-id="6a279-323">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="6a279-324">Adicionar o modificador `ref` a uma declaração `struct` existente é uma [alteração incompatível](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-324">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="6a279-325">Um `ref struct` não pode ser um membro de uma classe ou usado em outros locais em que ele pode ser alocado no heap.</span><span class="sxs-lookup"><span data-stu-id="6a279-325">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="6a279-326">Você pode ler mais sobre todas essas alterações em [Escrever código eficiente seguro](../write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-326">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

### <a name="ref-locals-and-returns"></a><span data-ttu-id="6a279-327">Locais e retornos de ref</span><span class="sxs-lookup"><span data-stu-id="6a279-327">Ref locals and returns</span></span>

<span data-ttu-id="6a279-328">Esse recurso permite que os algoritmos que usam e retornam referências para as variáveis definidas em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="6a279-328">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="6a279-329">Um exemplo é trabalhar com matrizes grandes e localizar um único local com determinadas características.</span><span class="sxs-lookup"><span data-stu-id="6a279-329">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="6a279-330">O seguinte método retorna uma **referência** a esse armazenamento na matriz:</span><span class="sxs-lookup"><span data-stu-id="6a279-330">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="6a279-331">Você pode declarar o valor retornado como uma `ref` e modificar esse valor na matriz, conforme mostrado no seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6a279-331">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="6a279-332">A linguagem C# tem várias regras que protegem contra o uso indevido de locais e retornos de `ref`:</span><span class="sxs-lookup"><span data-stu-id="6a279-332">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

- <span data-ttu-id="6a279-333">É necessário adicionar a palavra-chave `ref` à assinatura do método e a todas as instruções `return` em um método.</span><span class="sxs-lookup"><span data-stu-id="6a279-333">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="6a279-334">Isso torna claro que o método é retornado por referência em todo o método.</span><span class="sxs-lookup"><span data-stu-id="6a279-334">That makes it clear the method returns by reference throughout the method.</span></span>
- <span data-ttu-id="6a279-335">Um `ref return` pode ser atribuído a uma variável de valor ou a uma variável `ref`.</span><span class="sxs-lookup"><span data-stu-id="6a279-335">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="6a279-336">O chamador controla se o valor retornado é copiado ou não.</span><span class="sxs-lookup"><span data-stu-id="6a279-336">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="6a279-337">A omissão do modificador `ref` ao atribuir o valor retornado indica que o chamador deseja obter uma cópia do valor, não uma referência ao armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6a279-337">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
- <span data-ttu-id="6a279-338">Não é possível atribuir um valor retornado do método padrão a uma variável local de `ref`.</span><span class="sxs-lookup"><span data-stu-id="6a279-338">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="6a279-339">Isso proíbe que instruções como `ref int i = sequence.Count();`</span><span class="sxs-lookup"><span data-stu-id="6a279-339">That disallows statements like `ref int i = sequence.Count();`</span></span>
- <span data-ttu-id="6a279-340">Não é possível retornar um `ref` para uma variável cujo tempo de vida não se estende para além da execução do método.</span><span class="sxs-lookup"><span data-stu-id="6a279-340">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="6a279-341">Isso significa que não é possível retornar uma referência a uma variável local ou a uma variável com um escopo semelhante.</span><span class="sxs-lookup"><span data-stu-id="6a279-341">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
- <span data-ttu-id="6a279-342">O locais e retornos de `ref` não podem ser usados com métodos assíncronos.</span><span class="sxs-lookup"><span data-stu-id="6a279-342">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="6a279-343">O compilador não consegue saber se a variável referenciada foi definida com o valor final quando o método assíncrono retorna.</span><span class="sxs-lookup"><span data-stu-id="6a279-343">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="6a279-344">A adição de locais e retornos de ref permite algoritmos que são mais eficientes evitando a cópia de valores ou a execução múltipla de operações de desreferenciamento.</span><span class="sxs-lookup"><span data-stu-id="6a279-344">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="6a279-345">Adicionar `ref` ao valor retornado é uma [alteração compatível com a origem](version-update-considerations.md#source-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-345">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="6a279-346">O código existente é compilado, mas o valor retornado ref é copiado quando atribuído.</span><span class="sxs-lookup"><span data-stu-id="6a279-346">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="6a279-347">Os chamadores devem atualizar o armazenamento para o valor retornado para uma variável local `ref` para armazenar o retorno como uma referência.</span><span class="sxs-lookup"><span data-stu-id="6a279-347">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="6a279-348">Agora, as variáveis locais `ref` podem ser reatribuídas para se referir a diferentes instâncias depois de serem inicializadas.</span><span class="sxs-lookup"><span data-stu-id="6a279-348">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="6a279-349">O comando a seguir agora compila:</span><span class="sxs-lookup"><span data-stu-id="6a279-349">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="6a279-350">Para obter mais informações, consulte o artigo sobre [ `ref` retornos e `ref` locais](../programming-guide/classes-and-structs/ref-returns.md)e o artigo sobre [`foreach`](../language-reference/keywords/foreach-in.md) .</span><span class="sxs-lookup"><span data-stu-id="6a279-350">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

<span data-ttu-id="6a279-351">Para saber mais, confira o artigo [Palavra-chave ref](../language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-351">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

### <a name="conditional-ref-expressions"></a><span data-ttu-id="6a279-352">Expressões `ref` condicionais</span><span class="sxs-lookup"><span data-stu-id="6a279-352">Conditional `ref` expressions</span></span>

<span data-ttu-id="6a279-353">Por fim, a expressão condicional pode produzir um resultado ref em vez de um resultado de valor.</span><span class="sxs-lookup"><span data-stu-id="6a279-353">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="6a279-354">Por exemplo, você gravaria o seguinte para recuperar uma referência ao primeiro elemento em uma de duas matrizes:</span><span class="sxs-lookup"><span data-stu-id="6a279-354">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="6a279-355">A variável `r` é uma referência ao primeiro valor em `arr` ou `otherArr`.</span><span class="sxs-lookup"><span data-stu-id="6a279-355">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="6a279-356">Para saber mais, confira [Operador condicional (?:)](../language-reference/operators/conditional-operator.md) na referência da linguagem.</span><span class="sxs-lookup"><span data-stu-id="6a279-356">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>

### <a name="in-parameter-modifier"></a><span data-ttu-id="6a279-357">`in` modificador de parâmetro</span><span class="sxs-lookup"><span data-stu-id="6a279-357">`in` parameter modifier</span></span>

<span data-ttu-id="6a279-358">A `in` palavra-chave complementa as palavras-chaves ref e out existentes para passar argumentos por referência.</span><span class="sxs-lookup"><span data-stu-id="6a279-358">The `in` keyword complements the existing ref and out keywords to pass arguments by reference.</span></span> <span data-ttu-id="6a279-359">A palavra-chave `in` especifica a passagem do argumento por referência, mas o método chamado não modifica o valor.</span><span class="sxs-lookup"><span data-stu-id="6a279-359">The `in` keyword specifies passing the argument by reference, but the called method doesn't modify the value.</span></span>

<span data-ttu-id="6a279-360">Você pode declarar sobrecargas que passam por valor ou por referência ReadOnly, conforme mostrado no código a seguir:</span><span class="sxs-lookup"><span data-stu-id="6a279-360">You may declare overloads that pass by value or by readonly reference, as shown in the following code:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="6a279-361">A sobrecarga por valor (primeiro no exemplo anterior) é melhor do que a versão de referência ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="6a279-361">The by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="6a279-362">Para chamar a versão com o argumento de referência somente leitura, inclua o modificador `in` ao chamar o método.</span><span class="sxs-lookup"><span data-stu-id="6a279-362">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

<span data-ttu-id="6a279-363">Para obter mais informações, consulte o artigo sobre o [ `in` modificador de parâmetro](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-363">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="6a279-364">Mais tipos são compatíveis com a instrução `fixed`</span><span class="sxs-lookup"><span data-stu-id="6a279-364">More types support the `fixed` statement</span></span>

<span data-ttu-id="6a279-365">A instrução `fixed` era compatível com um conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="6a279-365">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="6a279-366">A partir do C# 7.3, qualquer tipo que contenha um método `GetPinnableReference()` que retorna `ref T` ou `ref readonly T` pode ser `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6a279-366">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="6a279-367">A adição desse recurso significa que `fixed` pode ser usado com <xref:System.Span%601?displayProperty=nameWithType> e tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="6a279-367">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="6a279-368">Para obter mais informações, consulte o artigo da [ `fixed` instrução](../language-reference/keywords/fixed-statement.md) na referência de linguagem.</span><span class="sxs-lookup"><span data-stu-id="6a279-368">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="6a279-369">A indexação de campos `fixed` não requer fixação</span><span class="sxs-lookup"><span data-stu-id="6a279-369">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="6a279-370">Considere este struct:</span><span class="sxs-lookup"><span data-stu-id="6a279-370">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="6a279-371">Em versões anteriores do C#, era preciso fixar uma variável para acessar um dos números inteiros que fazem parte de `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="6a279-371">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="6a279-372">Agora, o código a seguir compila sem fixar a variável `p` dentro de uma instrução `fixed` separada:</span><span class="sxs-lookup"><span data-stu-id="6a279-372">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="6a279-373">A variável `p` acessa um elemento em `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="6a279-373">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="6a279-374">Não é necessário declarar uma variável `int*` separada.</span><span class="sxs-lookup"><span data-stu-id="6a279-374">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="6a279-375">Você ainda precisa de um `unsafe` contexto.</span><span class="sxs-lookup"><span data-stu-id="6a279-375">You still need an `unsafe` context.</span></span> <span data-ttu-id="6a279-376">Em versões anteriores do C#, é necessário declarar um segundo ponteiro fixo:</span><span class="sxs-lookup"><span data-stu-id="6a279-376">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="6a279-377">Para obter mais informações, consulte o artigo na [ `fixed` instrução](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-377">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="6a279-378">Matrizes `stackalloc` são compatíveis com inicializadores</span><span class="sxs-lookup"><span data-stu-id="6a279-378">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="6a279-379">Você conseguiu especificar os valores dos elementos em uma matriz ao inicializá-la:</span><span class="sxs-lookup"><span data-stu-id="6a279-379">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="6a279-380">Agora, essa mesma sintaxe pode ser aplicada a matrizes declaradas com `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="6a279-380">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="6a279-381">Para obter mais informações, consulte o artigo do [ `stackalloc` operador](../language-reference/operators/stackalloc.md) .</span><span class="sxs-lookup"><span data-stu-id="6a279-381">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="6a279-382">Restrições genéricas aprimoradas</span><span class="sxs-lookup"><span data-stu-id="6a279-382">Enhanced generic constraints</span></span>

<span data-ttu-id="6a279-383">Agora é possível especificar o tipo <xref:System.Enum?displayProperty=nameWithType> ou <xref:System.Delegate?displayProperty=nameWithType> como restrições de classe base para um parâmetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="6a279-383">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="6a279-384">Você também pode usar a nova `unmanaged` restrição para especificar que um parâmetro de tipo deve ser um tipo não- [gerenciado](../language-reference/builtin-types/unmanaged-types.md)não anulável.</span><span class="sxs-lookup"><span data-stu-id="6a279-384">You can also use the new `unmanaged` constraint, to specify that a type parameter must be a non-nullable [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span>

<span data-ttu-id="6a279-385">Para obter mais informações, consulte os artigos sobre [ `where` restrições genéricas](../language-reference/keywords/where-generic-type-constraint.md) e [restrições em parâmetros de tipo](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-385">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="6a279-386">Adicionar essas restrições a tipos existentes é uma [alteração incompatível](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="6a279-386">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="6a279-387">Tipos genéricos fechados podem não atender mais a essas novas restrições.</span><span class="sxs-lookup"><span data-stu-id="6a279-387">Closed generic types may no longer meet these new constraints.</span></span>

### <a name="generalized-async-return-types"></a><span data-ttu-id="6a279-388">Tipos de retorno assíncrono generalizado</span><span class="sxs-lookup"><span data-stu-id="6a279-388">Generalized async return types</span></span>

<span data-ttu-id="6a279-389">Retornar um objeto `Task` de métodos assíncronos pode introduzir gargalos de desempenho em determinados caminhos.</span><span class="sxs-lookup"><span data-stu-id="6a279-389">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="6a279-390">`Task` é um tipo de referência, portanto, usá-lo significa alocar um objeto.</span><span class="sxs-lookup"><span data-stu-id="6a279-390">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="6a279-391">Em casos em que um método declarado com o modificador `async` retorna um resultado armazenado em cache ou é concluído de forma síncrona, as alocações extras podem se tornar um custo de tempo significativo em seções críticas de desempenho de código.</span><span class="sxs-lookup"><span data-stu-id="6a279-391">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="6a279-392">Isso pode se tornar caro se essas alocações ocorrem em loops rígidos.</span><span class="sxs-lookup"><span data-stu-id="6a279-392">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="6a279-393">O novo recurso de linguagem significa que os tipos de retorno do método assíncrono não se limitam a `Task`, `Task<T>` e `void`.</span><span class="sxs-lookup"><span data-stu-id="6a279-393">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="6a279-394">O tipo retornado ainda deve satisfazer o padrão assíncrono, o que significa que um método `GetAwaiter` deve ser acessível.</span><span class="sxs-lookup"><span data-stu-id="6a279-394">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="6a279-395">Como um exemplo concreto, o `ValueTask` tipo foi adicionado ao .net para fazer uso desse novo recurso de linguagem:</span><span class="sxs-lookup"><span data-stu-id="6a279-395">As one concrete example, the `ValueTask` type has been added to .NET to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="6a279-396">Você precisa adicionar o pacote NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) > para usar o <xref:System.Threading.Tasks.ValueTask%601> tipo.</span><span class="sxs-lookup"><span data-stu-id="6a279-396">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) > in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="6a279-397">Essa melhoria é mais útil para autores de biblioteca impedirem a alocação de uma `Task` em um código crítico para o desempenho.</span><span class="sxs-lookup"><span data-stu-id="6a279-397">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="6a279-398">Novas opções do compilador</span><span class="sxs-lookup"><span data-stu-id="6a279-398">New compiler options</span></span>

<span data-ttu-id="6a279-399">Novas opções do compilador são compatíveis com novos cenários de build e DevOps para programas C#.</span><span class="sxs-lookup"><span data-stu-id="6a279-399">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="reference-assembly-generation"></a><span data-ttu-id="6a279-400">Geração de assembly de referência</span><span class="sxs-lookup"><span data-stu-id="6a279-400">Reference assembly generation</span></span>

<span data-ttu-id="6a279-401">Há duas novas opções de compilador que geram *assemblies somente de referência*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) e [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-401">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="6a279-402">Os artigos vinculados explicam essas opções e os assemblies de referência mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="6a279-402">The linked articles explain these options and reference assemblies in more detail.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="6a279-403">Assinatura pública ou de código aberto</span><span class="sxs-lookup"><span data-stu-id="6a279-403">Public or Open Source signing</span></span>

<span data-ttu-id="6a279-404">A opção de compilador `-publicsign` instrui o compilador a assinar o assembly usando uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="6a279-404">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="6a279-405">O assembly é marcado como assinado, mas a assinatura é obtida da chave pública.</span><span class="sxs-lookup"><span data-stu-id="6a279-405">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="6a279-406">Essa opção permite criar crie assemblies assinados a partir de projetos de código aberto usando uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="6a279-406">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="6a279-407">Para saber mais, confira o artigo [Opção do compilador -publicsign](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-407">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="6a279-408">pathmap</span><span class="sxs-lookup"><span data-stu-id="6a279-408">pathmap</span></span>

<span data-ttu-id="6a279-409">A opção de compilador `-pathmap` instrui o compilador a substituir os caminhos de origem do ambiente de build com caminhos de origem mapeados.</span><span class="sxs-lookup"><span data-stu-id="6a279-409">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="6a279-410">A opção `-pathmap` controla o caminho de origem gravado pelo compilador para arquivos PDB ou para o <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6a279-410">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="6a279-411">Para saber mais, confira o artigo [Opção do compilador -pathmap](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6a279-411">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
