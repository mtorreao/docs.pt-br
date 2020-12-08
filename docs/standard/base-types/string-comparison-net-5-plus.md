---
title: Alterações de comportamento ao comparar cadeias de caracteres no .NET 5 +
description: Saiba mais sobre alterações de comportamento de comparação de cadeia de caracteres no .NET 5 e versões posteriores no Windows.
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851745"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a><span data-ttu-id="b8c3f-103">Alterações de comportamento ao comparar cadeias de caracteres no .NET 5 +</span><span class="sxs-lookup"><span data-stu-id="b8c3f-103">Behavior changes when comparing strings on .NET 5+</span></span>

<span data-ttu-id="b8c3f-104">O .NET 5,0 apresenta uma alteração comportamental de tempo de execução em que as APIs de globalização [agora usam o ICU por padrão](../../core/compatibility/globalization/5.0/icu-globalization-api.md) em todas as plataformas com suporte.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-104">.NET 5.0 introduces a runtime behavioral change where globalization APIs [now use ICU by default](../../core/compatibility/globalization/5.0/icu-globalization-api.md) across all supported platforms.</span></span> <span data-ttu-id="b8c3f-105">Essa é uma partida de versões anteriores do .NET Core e da .NET Framework, que utiliza a funcionalidade NLS (suporte ao idioma nacional) do sistema operacional quando executada no Windows.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-105">This is a departure from earlier versions of .NET Core and from .NET Framework, which utilize the operating system's national language support (NLS) functionality when running on Windows.</span></span> <span data-ttu-id="b8c3f-106">Para obter mais informações sobre essas alterações, incluindo opções de compatibilidade que podem reverter a alteração de comportamento, consulte [.net Globalization and ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-106">For more information on these changes, including compatibility switches that can revert the behavior change, see [.NET globalization and ICU](../globalization-localization/globalization-icu.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b8c3f-107">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="b8c3f-107">Reason for change</span></span>

<span data-ttu-id="b8c3f-108">Essa alteração foi introduzida para unificar. Comportamento de globalização da rede em todos os sistemas operacionais com suporte.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-108">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="b8c3f-109">Ele também fornece a capacidade de os aplicativos agruparem suas próprias bibliotecas de globalização em vez de depender das bibliotecas internas do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-109">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the OS's built-in libraries.</span></span> <span data-ttu-id="b8c3f-110">Para obter mais informações, consulte [a notificação de alteração significativa](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-110">For more information, see [the breaking change notification](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="b8c3f-111">Diferenças de comportamento</span><span class="sxs-lookup"><span data-stu-id="b8c3f-111">Behavioral differences</span></span>

<span data-ttu-id="b8c3f-112">Se você usar funções como `string.IndexOf(string)` sem chamar a sobrecarga que usa um <xref:System.StringComparison> argumento, Talvez pretenda executar uma pesquisa *ordinal* , mas, em vez disso, você assume inadvertidamente uma dependência do comportamento específico da cultura.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-112">If you use functions like `string.IndexOf(string)` without calling the overload that takes a <xref:System.StringComparison> argument, you might intend to perform an *ordinal* search, but instead you inadvertently take a dependency on culture-specific behavior.</span></span> <span data-ttu-id="b8c3f-113">Como NLS e ICU implementam lógicas diferentes em seus comparadores lingüísticos, os resultados de métodos como `string.IndexOf(string)` podem retornar valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-113">Since NLS and ICU implement different logic in their linguistic comparers, the results of methods like `string.IndexOf(string)` can return unexpected values.</span></span>

<span data-ttu-id="b8c3f-114">Isso pode se manifestar mesmo em locais onde você nem sempre está esperando que as instalações de globalização estejam ativas.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-114">This can manifest itself even in places where you aren't always expecting globalization facilities to be active.</span></span> <span data-ttu-id="b8c3f-115">Por exemplo, o código a seguir pode produzir uma resposta diferente dependendo do tempo de execução atual.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-115">For example, the following code can produce a different answer depending on the current runtime.</span></span>

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a><span data-ttu-id="b8c3f-116">Proteção contra comportamento inesperado</span><span class="sxs-lookup"><span data-stu-id="b8c3f-116">Guard against unexpected behavior</span></span>

<span data-ttu-id="b8c3f-117">Esta seção fornece duas opções para lidar com alterações de comportamento inesperadas no .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-117">This section provides two options for dealing with unexpected behavior changes in .NET 5.0.</span></span>

### <a name="enable-code-analyzers"></a><span data-ttu-id="b8c3f-118">Habilitar analisadores de código</span><span class="sxs-lookup"><span data-stu-id="b8c3f-118">Enable code analyzers</span></span>

<span data-ttu-id="b8c3f-119">[Analisadores de código](../../fundamentals/code-analysis/overview.md) podem detectar sites de chamada possivelmente com bugs.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-119">[Code analyzers](../../fundamentals/code-analysis/overview.md) can detect possibly buggy call sites.</span></span> <span data-ttu-id="b8c3f-120">Para ajudar a proteger contra qualquer comportamento surpreendente, recomendamos habilitar os analisadores de Roslyn (plataforma de compilador .NET) em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-120">To help guard against any surprising behaviors, we recommend enabling .NET compiler platform (Roslyn) analyzers in your project.</span></span> <span data-ttu-id="b8c3f-121">Os analisadores ajudam a codificar o código que pode usar inadvertidamente um comparador lingüístico quando um comparador ordinal era provavelmente pretendido.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-121">The analyzers help flag code that might inadvertently be using a linguistic comparer when an ordinal comparer was likely intended.</span></span> <span data-ttu-id="b8c3f-122">As regras a seguir devem ajudar a sinalizar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="b8c3f-122">The following rules should help flag these issues:</span></span>

- [<span data-ttu-id="b8c3f-123">CA1307: Especificar StringComparison para garantir a clareza</span><span class="sxs-lookup"><span data-stu-id="b8c3f-123">CA1307: Specify StringComparison for clarity</span></span>](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [<span data-ttu-id="b8c3f-124">CA1309: Usar StringComparison ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-124">CA1309: Use ordinal StringComparison</span></span>](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [<span data-ttu-id="b8c3f-125">CA1310: Especificar StringComparison para garantir a exatidão</span><span class="sxs-lookup"><span data-stu-id="b8c3f-125">CA1310: Specify StringComparison for correctness</span></span>](../../fundamentals/code-analysis/quality-rules/ca1310.md)

<span data-ttu-id="b8c3f-126">Essas regras específicas não são habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-126">These specific rules aren't enabled by default.</span></span> <span data-ttu-id="b8c3f-127">Para habilitá-los e mostrar quaisquer violações como erros de compilação, defina as seguintes propriedades em seu arquivo de projeto:</span><span class="sxs-lookup"><span data-stu-id="b8c3f-127">To enable them and show any violations as build errors, set the following properties in your project file:</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="b8c3f-128">O trecho a seguir mostra exemplos de código que produz os avisos ou erros relevantes do analisador de código.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-128">The following snippet shows examples of code that produces the relevant code analyzer warnings or errors.</span></span>

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

<span data-ttu-id="b8c3f-129">Da mesma forma, ao criar uma instância de uma coleção classificada de cadeias de caracteres ou classificar uma coleção baseada em cadeia existente, especifique um comparador explícito.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-129">Similarly, when instantiating a sorted collection of strings or sorting an existing string-based collection, specify an explicit comparer.</span></span>

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a><span data-ttu-id="b8c3f-130">Reverter para os comportamentos NLS</span><span class="sxs-lookup"><span data-stu-id="b8c3f-130">Revert back to NLS behaviors</span></span>

<span data-ttu-id="b8c3f-131">Para reverter os aplicativos do .NET 5 para os comportamentos NLS mais antigos ao executar no Windows, siga as etapas em [.net Globalization e ICU](../globalization-localization/globalization-icu.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-131">To revert .NET 5 applications back to older NLS behaviors when running on Windows, follow the steps in [.NET Globalization and ICU](../globalization-localization/globalization-icu.md).</span></span> <span data-ttu-id="b8c3f-132">Essa opção de compatibilidade em todo o aplicativo deve ser definida no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-132">This application-wide compatibility switch must be set at the application level.</span></span> <span data-ttu-id="b8c3f-133">Bibliotecas individuais não podem aceitar ou recusar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-133">Individual libraries cannot opt-in or opt-out of this behavior.</span></span>

> [!TIP]
> <span data-ttu-id="b8c3f-134">É altamente recomendável que você habilite as regras de análise de código [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md)e [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) para ajudar a melhorar a higienização de código e descobrir quaisquer bugs latentes existentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-134">We strongly recommend you enable the [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), and [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) code analysis rules to help improve code hygiene and discover any existing latent bugs.</span></span> <span data-ttu-id="b8c3f-135">Para obter mais informações, consulte [habilitar analisadores de código](#enable-code-analyzers).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-135">For more information, see [Enable code analyzers](#enable-code-analyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b8c3f-136">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="b8c3f-136">Affected APIs</span></span>

<span data-ttu-id="b8c3f-137">A maioria dos aplicativos .NET não encontrará comportamentos inesperados devido às alterações no .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-137">Most .NET applications won't encounter any unexpected behaviors due to the changes in .NET 5.0.</span></span> <span data-ttu-id="b8c3f-138">No entanto, devido ao número de APIs afetadas e à forma como as bases dessas APIs são para o ecossistema mais amplo do .NET, você deve estar ciente do potencial para que o .NET 5,0 Introduza comportamentos indesejados ou expor bugs latentes que já existem em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-138">However, due to the number of affected APIs and how foundational these APIs are to the wider .NET ecosystem, you should be aware of the potential for .NET 5.0 to introduce unwanted behaviors or to expose latent bugs that already exist in your application.</span></span>

<span data-ttu-id="b8c3f-139">As APIs afetadas incluem:</span><span class="sxs-lookup"><span data-stu-id="b8c3f-139">The affected APIs include:</span></span>

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <span data-ttu-id="b8c3f-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (a maioria dos membros)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="b8c3f-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (a maioria dos membros)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="b8c3f-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (ao classificar matrizes de cadeias de caracteres)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting arrays of strings)</span></span>
- <span data-ttu-id="b8c3f-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (quando os elementos da lista são cadeias de caracteres)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="b8c3f-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (quando as chaves são cadeias de caracteres)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="b8c3f-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (quando as chaves são cadeias de caracteres)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="b8c3f-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (quando o conjunto contém cadeias de caracteres)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

> [!NOTE]
> <span data-ttu-id="b8c3f-147">Esta não é uma lista completa de APIs afetadas.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-147">This is not an exhaustive list of affected APIs.</span></span>

<span data-ttu-id="b8c3f-148">Todas as APIs acima usam a pesquisa de cadeia de caracteres *linguística* e a comparação usando a [cultura atual](xref:System.Threading.Thread.CurrentCulture)do thread, por padrão.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-148">All of the above APIs use *linguistic* string searching and comparison using the thread's [current culture](xref:System.Threading.Thread.CurrentCulture), by default.</span></span> <span data-ttu-id="b8c3f-149">As diferenças entre a pesquisa *lingüística* e a *ordinal* e a comparação são chamadas na [pesquisa e comparação de ordinais e linguísticas](#ordinal-vs-linguistic-search-and-comparison).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-149">The differences between *linguistic* and *ordinal* search and comparison are called out in the [Ordinal vs. linguistic search and comparison](#ordinal-vs-linguistic-search-and-comparison).</span></span>

<span data-ttu-id="b8c3f-150">Como o ICU implementa comparações lingüísticas de cadeias de caracteres de forma diferente de NLS, os aplicativos baseados no Windows que são atualizados para o .NET 5,0 de uma versão anterior do .NET Core ou .NET Framework e que chamam uma das APIs afetadas podem notar que as APIs começam a apresentar comportamentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-150">Because ICU implements linguistic string comparisons differently from NLS, Windows-based applications that upgrade to .NET 5.0 from an earlier version of .NET Core or .NET Framework and that call one of the affected APIs may notice that the APIs begin exhibiting different behaviors.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b8c3f-151">Exceções</span><span class="sxs-lookup"><span data-stu-id="b8c3f-151">Exceptions</span></span>

* <span data-ttu-id="b8c3f-152">Se uma API aceitar um `StringComparison` parâmetro ou explícito `CultureInfo` , esse parâmetro substituirá o comportamento padrão da API.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-152">If an API accepts an explicit `StringComparison` or `CultureInfo` parameter, that parameter overrides the API's default behavior.</span></span>
* <span data-ttu-id="b8c3f-153">`System.String` os membros em que o primeiro parâmetro é do tipo `char` (por exemplo, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType> ) usam a pesquisa ordinal, a menos que o chamador passe um `StringComparison` argumento explícito que especifica `CurrentCulture[IgnoreCase]` ou `InvariantCulture[IgnoreCase]` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-153">`System.String` members where the first parameter is of type `char` (for example, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) use ordinal searching, unless the caller passes an explicit `StringComparison` argument that specifies `CurrentCulture[IgnoreCase]` or `InvariantCulture[IgnoreCase]`.</span></span>

<span data-ttu-id="b8c3f-154">Para obter uma análise mais detalhada do comportamento padrão de cada <xref:System.String> API, consulte a seção [padrão pesquisa e tipos de comparação](#default-search-and-comparison-types) .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-154">For a more detailed analysis of the default behavior of each <xref:System.String> API, see the [Default search and comparison types](#default-search-and-comparison-types) section.</span></span>

## <a name="ordinal-vs-linguistic-search-and-comparison"></a><span data-ttu-id="b8c3f-155">Pesquisa e comparação de ordinal vs. linguística</span><span class="sxs-lookup"><span data-stu-id="b8c3f-155">Ordinal vs. linguistic search and comparison</span></span>

<span data-ttu-id="b8c3f-156">A pesquisa e a comparação de *ordinal* (também conhecida como *não lingüística*) decompõem uma cadeia de caracteres em seus `char` elementos individuais e executa uma pesquisa Char-por-char ou uma comparação.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-156">*Ordinal* (also known as *non-linguistic*) search and comparison decomposes a string into its individual `char` elements and performs a char-by-char search or comparison.</span></span> <span data-ttu-id="b8c3f-157">Por exemplo, as cadeias de caracteres `"dog"` e `"dog"` comparar como *iguais* em um comparador `Ordinal` , já que as duas cadeias de caracteres consistem na mesma sequência exata de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-157">For example, the strings `"dog"` and `"dog"` compare as *equal* under an `Ordinal` comparer, since the two strings consist of the exact same sequence of chars.</span></span> <span data-ttu-id="b8c3f-158">No entanto, `"dog"` e `"Dog"` comparar como *não igual* em um comparador `Ordinal` , porque eles não consistem na mesma sequência exata de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-158">However, `"dog"` and `"Dog"` compare as *not equal* under an `Ordinal` comparer, because they don't consist of the exact same sequence of chars.</span></span> <span data-ttu-id="b8c3f-159">Ou seja, o `'D'` ponto de código de maiúsculas `U+0044` ocorre antes `'d'` do ponto de código de minúsculas `U+0064` , resultando na `"dog"` classificação antes `"Dog"` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-159">That is, uppercase `'D'`'s code point `U+0044` occurs before lowercase `'d'`'s code point `U+0064`, resulting in `"dog"` sorting before `"Dog"`.</span></span>

<span data-ttu-id="b8c3f-160">Um comparador `OrdinalIgnoreCase` ainda opera com base Char-por-Char, mas elimina diferenças de maiúsculas e minúsculas ao executar a operação.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-160">An `OrdinalIgnoreCase` comparer still operates on a char-by-char basis, but it eliminates case differences while performing the operation.</span></span> <span data-ttu-id="b8c3f-161">Em um `OrdinalIgnoreCase` comparador, os pares de caracteres `'d'` e `'D'` comparar como *iguais*, assim como os pares de caracteres `'á'` e `'Á'` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-161">Under an `OrdinalIgnoreCase` comparer, the char pairs `'d'` and `'D'` compare as *equal*, as do the char pairs `'á'` and `'Á'`.</span></span> <span data-ttu-id="b8c3f-162">Mas o caractere não acentuado `'a'` compara como *não igual* ao caractere acentuado `'á'` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-162">But the unaccented char `'a'` compares as *not equal* to the accented char `'á'`.</span></span>

<span data-ttu-id="b8c3f-163">Alguns exemplos disso são fornecidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8c3f-163">Some examples of this are provided in the following table:</span></span>

| <span data-ttu-id="b8c3f-164">Cadeia de caracteres 1</span><span class="sxs-lookup"><span data-stu-id="b8c3f-164">String 1</span></span> | <span data-ttu-id="b8c3f-165">Cadeia de caracteres 2</span><span class="sxs-lookup"><span data-stu-id="b8c3f-165">String 2</span></span> | <span data-ttu-id="b8c3f-166">`Ordinal` comparação</span><span class="sxs-lookup"><span data-stu-id="b8c3f-166">`Ordinal` comparison</span></span> | <span data-ttu-id="b8c3f-167">`OrdinalIgnoreCase` comparação</span><span class="sxs-lookup"><span data-stu-id="b8c3f-167">`OrdinalIgnoreCase` comparison</span></span> |
|---|---|---|---|
| `"dog"` | `"dog"` | <span data-ttu-id="b8c3f-168">equal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-168">equal</span></span> | <span data-ttu-id="b8c3f-169">equal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-169">equal</span></span> |
| `"dog"` | `"Dog"` | <span data-ttu-id="b8c3f-170">diferente de</span><span class="sxs-lookup"><span data-stu-id="b8c3f-170">not equal</span></span> | <span data-ttu-id="b8c3f-171">equal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-171">equal</span></span> |
| `"resume"` | `"Resume"` | <span data-ttu-id="b8c3f-172">diferente de</span><span class="sxs-lookup"><span data-stu-id="b8c3f-172">not equal</span></span> | <span data-ttu-id="b8c3f-173">equal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-173">equal</span></span> |
| `"resume"` | `"résumé"` | <span data-ttu-id="b8c3f-174">diferente de</span><span class="sxs-lookup"><span data-stu-id="b8c3f-174">not equal</span></span> | <span data-ttu-id="b8c3f-175">diferente de</span><span class="sxs-lookup"><span data-stu-id="b8c3f-175">not equal</span></span> |

<span data-ttu-id="b8c3f-176">O Unicode também permite que as cadeias de caracteres tenham várias representações na memória diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-176">Unicode also allows strings to have several different in-memory representations.</span></span> <span data-ttu-id="b8c3f-177">Por exemplo, um e-agudo (é) pode ser representado de duas maneiras possíveis:</span><span class="sxs-lookup"><span data-stu-id="b8c3f-177">For example, an e-acute (é) can be represented in two possible ways:</span></span>

* <span data-ttu-id="b8c3f-178">Um único `'é'` caractere literal (também escrito como `'\u00E9'` ).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-178">A single literal `'é'` character (also written as `'\u00E9'`).</span></span>
* <span data-ttu-id="b8c3f-179">Um caractere literal não acentuado `'e'` , seguido por um caractere de modificador de acentuação de acento `'\u0301'` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-179">A literal unaccented `'e'` character, followed by a combining accent modifier character `'\u0301'`.</span></span>

<span data-ttu-id="b8c3f-180">Isso significa que todas as _quatro_ cadeias de caracteres a seguir resultam em `"résumé"` quando exibidas, embora suas partes constituintes sejam diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-180">This means that the following _four_ strings all result in `"résumé"` when displayed, even though their constituent pieces are different.</span></span> <span data-ttu-id="b8c3f-181">As strings usam uma combinação de caracteres literais `'é'` ou caracteres literais não acentuados, `'e'` além do modificador de acentuação combinável `'\u0301'` .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-181">The strings use a combination of literal `'é'` characters or literal unaccented `'e'` characters plus the combining accent modifier `'\u0301'`.</span></span>

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

<span data-ttu-id="b8c3f-182">Em um comparador ordinal, nenhuma dessas cadeias de caracteres é comparada como igual uma da outra.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-182">Under an ordinal comparer, none of these strings compare as equal to each other.</span></span> <span data-ttu-id="b8c3f-183">Isso ocorre porque todos contêm sequências de caracteres subjacentes diferentes, mesmo quando são renderizados na tela, todos têm a mesma aparência.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-183">This is because they all contain different underlying char sequences, even though when they're rendered to the screen, they all look the same.</span></span>

<span data-ttu-id="b8c3f-184">Ao executar uma `string.IndexOf(..., StringComparison.Ordinal)` operação, o tempo de execução procura uma correspondência exata de subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-184">When performing a `string.IndexOf(..., StringComparison.Ordinal)` operation, the runtime looks for an exact substring match.</span></span> <span data-ttu-id="b8c3f-185">Os resultados são os seguintes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-185">The results are as follows.</span></span>

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

<span data-ttu-id="b8c3f-186">As rotinas de pesquisa e de comparação ordinais nunca são afetadas pela configuração de cultura do thread atual.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-186">Ordinal search and comparison routines are never affected by the current thread's culture setting.</span></span>

<span data-ttu-id="b8c3f-187">As rotinas de pesquisa e de comparação *linguística* decompõem uma cadeia de caracteres em *elementos de agrupamento* e realizam pesquisas ou comparações nesses elementos.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-187">*Linguistic* search and comparison routines decompose a string into *collation elements* and perform searches or comparisons on these elements.</span></span> <span data-ttu-id="b8c3f-188">Não há necessariamente um mapeamento 1:1 entre os caracteres de uma cadeia e seus elementos de agrupamento constituintes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-188">There's not necessarily a 1:1 mapping between a string's characters and its constituent collation elements.</span></span> <span data-ttu-id="b8c3f-189">Por exemplo, uma cadeia de caracteres de comprimento 2 pode consistir apenas de um único elemento de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-189">For example, a string of length 2 may consist of only a single collation element.</span></span> <span data-ttu-id="b8c3f-190">Quando duas cadeias de caracteres são comparadas de forma linguística, o comparador verifica se os elementos de agrupamento das duas cadeias de caracteres têm o mesmo significado semântico, mesmo que os caracteres literais da cadeia sejam diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-190">When two strings are compared in a linguistic-aware fashion, the comparer checks whether the two strings' collation elements have the same semantic meaning, even if the string's literal characters are different.</span></span>

<span data-ttu-id="b8c3f-191">Considere novamente a cadeia de caracteres `"résumé"` e suas quatro representações diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-191">Consider again the string `"résumé"` and its four different representations.</span></span> <span data-ttu-id="b8c3f-192">A tabela a seguir mostra cada representação dividida em seus elementos de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-192">The following table shows each representation broken down into its collation elements.</span></span>

| <span data-ttu-id="b8c3f-193">String</span><span class="sxs-lookup"><span data-stu-id="b8c3f-193">String</span></span> | <span data-ttu-id="b8c3f-194">Como elementos de agrupamento</span><span class="sxs-lookup"><span data-stu-id="b8c3f-194">As collation elements</span></span> |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

<span data-ttu-id="b8c3f-195">Um elemento de agrupamento corresponde livremente ao que os leitores consideram como um único caractere ou cluster de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-195">A collation element corresponds loosely to what readers would think of as a single character or cluster of characters.</span></span> <span data-ttu-id="b8c3f-196">Ele é conceitualmente semelhante a um [cluster grafemas](character-encoding-introduction.md#grapheme-clusters) , mas abrange uma proteção um pouco maior.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-196">It's conceptually similar to a [grapheme cluster](character-encoding-introduction.md#grapheme-clusters) but encompasses a somewhat larger umbrella.</span></span>

<span data-ttu-id="b8c3f-197">Em um comparador linguístico, as correspondências exatas não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-197">Under a linguistic comparer, exact matches aren't necessary.</span></span> <span data-ttu-id="b8c3f-198">Em vez disso, os elementos de agrupamento são comparados com base no significado semântico.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-198">Collation elements are instead compared based on their semantic meaning.</span></span> <span data-ttu-id="b8c3f-199">Por exemplo, um comparador linguístico trata as subcadeias de caracteres `"\u00E9"` e `"e\u0301"` como iguais, uma vez que ambas significam semanticamente "um e minúsculo com um modificador de acentos agudos".</span><span class="sxs-lookup"><span data-stu-id="b8c3f-199">For example, a linguistic comparer treats the substrings `"\u00E9"` and `"e\u0301"` as equal since they both semantically mean "a lowercase e with an acute accent modifier."</span></span> <span data-ttu-id="b8c3f-200">Isso permite que o `IndexOf` método coincida com a subcadeia de caracteres `"e\u0301"` em uma cadeia de caracteres maior que contém a subcadeia de caracteres semanticamente equivalente `"\u00E9"` , como mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-200">This allows the `IndexOf` method to match the substring `"e\u0301"` within a larger string that contains the semantically equivalent substring `"\u00E9"`, as shown in the following code sample.</span></span>

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

<span data-ttu-id="b8c3f-201">Como consequência disso, duas cadeias de caracteres de comprimentos diferentes podem ser comparadas como iguais se uma comparação linguística for usada.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-201">As a consequence of this, two strings of different lengths may compare as equal if a linguistic comparison is used.</span></span> <span data-ttu-id="b8c3f-202">Os chamadores devem tomar cuidado para não ser uma lógica de caso especial que lida com o comprimento da cadeia de caracteres nesses cenários.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-202">Callers should take care not to special-case logic that deals with string length in such scenarios.</span></span>

<span data-ttu-id="b8c3f-203">As rotinas de comparação e pesquisa *com reconhecimento de cultura* são uma forma especial de pesquisa linguística e rotinas de comparação.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-203">*Culture-aware* search and comparison routines are a special form of linguistic search and comparison routines.</span></span> <span data-ttu-id="b8c3f-204">Em um comparador com reconhecimento de cultura, o conceito de um elemento de agrupamento é estendido para incluir informações específicas para a cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-204">Under a culture-aware comparer, the concept of a collation element is extended to include information specific to the specified culture.</span></span>

<span data-ttu-id="b8c3f-205">Por exemplo, [no alfabeto húngaro](https://en.wikipedia.org/wiki/Hungarian_alphabet), quando os dois caracteres \<dz\> aparecem de volta para trás, eles são considerados sua própria letra exclusiva distinta de \<d\> ou \<z\> .</span><span class="sxs-lookup"><span data-stu-id="b8c3f-205">For example, [in the Hungarian alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet), when the two characters \<dz\> appear back-to-back, they are considered their own unique letter distinct from either \<d\> or \<z\>.</span></span> <span data-ttu-id="b8c3f-206">Isso significa que \<dz\> , quando é visto em uma cadeia de caracteres, um comparador com reconhecimento de cultura húngaro trata isso como um único elemento de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-206">This means that when \<dz\> is seen in a string, a Hungarian culture-aware comparer treats it as a single collation element.</span></span>

| <span data-ttu-id="b8c3f-207">String</span><span class="sxs-lookup"><span data-stu-id="b8c3f-207">String</span></span> | <span data-ttu-id="b8c3f-208">Como elementos de agrupamento</span><span class="sxs-lookup"><span data-stu-id="b8c3f-208">As collation elements</span></span> | <span data-ttu-id="b8c3f-209">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8c3f-209">Remarks</span></span> |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | <span data-ttu-id="b8c3f-210">(usando um comparador linguístico padrão)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-210">(using a standard linguistic comparer)</span></span> |
| `"endz"` | `"e" + "n" + "dz"` | <span data-ttu-id="b8c3f-211">(usando um comparador com reconhecimento de cultura húngaro)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-211">(using a Hungarian culture-aware comparer)</span></span> |

<span data-ttu-id="b8c3f-212">Ao usar um comparador com reconhecimento de cultura húngaro, isso significa que a cadeia de caracteres `"endz"` *não* termina com a subcadeia de caracteres `"z"` , pois < \dz \> e < \Z \> são considerados elementos de agrupamento com significado semântico diferente.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-212">When using a Hungarian culture-aware comparer, this means that the string `"endz"` *does not* end with the substring `"z"`, as <\dz\> and <\z\> are considered collation elements with different semantic meaning.</span></span>

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - <span data-ttu-id="b8c3f-213">Comportamento: os comparadores lingüísticas e com reconhecimento de cultura podem sofrer ajustes de comportamento de tempos em tempos.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-213">Behavior: Linguistic and culture-aware comparers can undergo behavioral adjustments from time to time.</span></span> <span data-ttu-id="b8c3f-214">O ICU e o recurso NLS mais antigo do Windows são atualizados para considerar como as linguagens do mundo mudam.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-214">Both ICU and the older Windows NLS facility are updated to account for how world languages change.</span></span> <span data-ttu-id="b8c3f-215">Para obter mais informações, consulte a variação de dados de localidade da postagem do blog [(cultura)](/archive/blogs/shawnste/locale-culture-data-churn).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-215">For more information, see the blog post [Locale (culture) data churn](/archive/blogs/shawnste/locale-culture-data-churn).</span></span> <span data-ttu-id="b8c3f-216">O comportamento do comparador *ordinal* nunca será alterado, já que ele executa a comparação e a pesquisa de bits exatas.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-216">The *Ordinal* comparer's behavior will never change since it performs exact bitwise searching and comparison.</span></span> <span data-ttu-id="b8c3f-217">No entanto, o comportamento do comparador de *OrdinalIgnoreCase* pode mudar conforme o Unicode cresce para abranger mais conjuntos de caracteres e corrigir omissões em dados de maiúsculas e minúsculas existentes.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-217">However, the *OrdinalIgnoreCase* comparer's behavior may change as Unicode grows to encompass more character sets and corrects omissions in existing casing data.</span></span>
> - <span data-ttu-id="b8c3f-218">Uso: os comparadores `StringComparison.InvariantCulture` e `StringComparison.InvariantCultureIgnoreCase` são comparadores lingüísticos que não reconhecem a cultura.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-218">Usage: The comparers `StringComparison.InvariantCulture` and `StringComparison.InvariantCultureIgnoreCase` are linguistic comparers that are not culture-aware.</span></span> <span data-ttu-id="b8c3f-219">Ou seja, esses comparadores entendem conceitos como o caractere acentuado é ter várias representações subjacentes possíveis e que todas essas representações devem ser tratadas iguais.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-219">That is, these comparers understand concepts such as the accented character é having multiple possible underlying representations, and that all such representations should be treated equal.</span></span> <span data-ttu-id="b8c3f-220">Mas os comparadores lingüísticos que não reconhecem a cultura não conterão tratamento especial para \<dz\> o as \<d\> \<z\> , conforme mostrado acima.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-220">But non-culture-aware linguistic comparers won't contain special handling for \<dz\> as distinct from \<d\> or \<z\>, as shown above.</span></span> <span data-ttu-id="b8c3f-221">Eles também não são caracteres especiais como o alemão Eszett (ß).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-221">They also won't special-case characters like the German Eszett (ß).</span></span>

<span data-ttu-id="b8c3f-222">O .NET também oferece o *modo de globalização invariável*.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-222">.NET also offers the *invariant globalization mode*.</span></span> <span data-ttu-id="b8c3f-223">Esse modo de aceitação desabilita caminhos de código que lidam com rotinas de comparação e pesquisa linguística.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-223">This opt-in mode disables code paths that deal with linguistic search and comparison routines.</span></span> <span data-ttu-id="b8c3f-224">Nesse modo, todas as operações usam comportamentos *ordinais* ou *OrdinalIgnoreCase* , independentemente do `CultureInfo` argumento ou que `StringComparison` o chamador fornece.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-224">In this mode, all operations use *Ordinal* or *OrdinalIgnoreCase* behaviors, regardless of what `CultureInfo` or `StringComparison` argument the caller provides.</span></span> <span data-ttu-id="b8c3f-225">Para obter mais informações, consulte [Opções de configuração de tempo de execução para globalização](../../core/run-time-config/globalization.md) e [modo invariável de globalização do .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-225">For more information, see [Run-time configuration options for globalization](../../core/run-time-config/globalization.md) and [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

<span data-ttu-id="b8c3f-226">Para obter mais informações, consulte [práticas recomendadas para comparar cadeias de caracteres no .net](best-practices-strings.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3f-226">For more information, see [Best practices for comparing strings in .NET](best-practices-strings.md).</span></span>

## <a name="security-implications"></a><span data-ttu-id="b8c3f-227">Implicações de segurança</span><span class="sxs-lookup"><span data-stu-id="b8c3f-227">Security implications</span></span>

<span data-ttu-id="b8c3f-228">Se seu aplicativo usar uma API afetada para filtragem, é recomendável habilitar as regras de análise de código CA1307 e CA1309 para ajudar a localizar locais onde uma pesquisa linguística pode ter sido usada inadvertidamente em vez de uma pesquisa ordinal.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-228">If your app uses an affected API for filtering, we recommend enabling the CA1307 and CA1309 code analysis rules to help locate places where a linguistic search may have inadvertently been used instead of an ordinal search.</span></span> <span data-ttu-id="b8c3f-229">Os padrões de código como os seguintes podem ser suscetíveis a explorações de segurança.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-229">Code patterns like the following may be susceptible to security exploits.</span></span>

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

<span data-ttu-id="b8c3f-230">Como o `string.IndexOf(string)` método usa uma pesquisa linguística por padrão, é possível que uma cadeia de caracteres contenha um literal `'<'` ou `'&'` caractere e que a `string.IndexOf(string)` rotina seja retornada `-1` , indicando que a subcadeia de caracteres de pesquisa não foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-230">Because the `string.IndexOf(string)` method uses a linguistic search by default, it's possible for a string to contain a literal `'<'` or `'&'` character and for the `string.IndexOf(string)` routine to return `-1`, indicating that the search substring was not found.</span></span> <span data-ttu-id="b8c3f-231">As regras de análise de código CA1307 e CA1309 sinalizam sites de chamada e alertam o desenvolvedor de que há um problema potencial.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-231">Code analysis rules CA1307 and CA1309 flag such call sites and alert the developer that there's a potential problem.</span></span>

## <a name="default-search-and-comparison-types"></a><span data-ttu-id="b8c3f-232">Tipos de comparação e pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="b8c3f-232">Default search and comparison types</span></span>

<span data-ttu-id="b8c3f-233">A tabela a seguir lista os tipos de comparação e de pesquisa padrão para várias APIs de cadeia de caracteres e semelhantes a cadeia.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-233">The following table lists the default search and comparison types for various string and string-like APIs.</span></span> <span data-ttu-id="b8c3f-234">Se o chamador fornecer um `CultureInfo` parâmetro ou explícito `StringComparison` , esse parâmetro será respeitado em qualquer padrão.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-234">If the caller provides an explicit `CultureInfo` or `StringComparison` parameter, that parameter will be honored over any default.</span></span>

| <span data-ttu-id="b8c3f-235">API</span><span class="sxs-lookup"><span data-stu-id="b8c3f-235">API</span></span> | <span data-ttu-id="b8c3f-236">Comportamento padrão</span><span class="sxs-lookup"><span data-stu-id="b8c3f-236">Default behavior</span></span> | <span data-ttu-id="b8c3f-237">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8c3f-237">Remarks</span></span> |
|---|---|---|
| `string.Compare` | <span data-ttu-id="b8c3f-238">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-238">CurrentCulture</span></span> | |
| `string.CompareTo` | <span data-ttu-id="b8c3f-239">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-239">CurrentCulture</span></span> | |
| `string.Contains` | <span data-ttu-id="b8c3f-240">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-240">Ordinal</span></span> | |
| `string.EndsWith` | <span data-ttu-id="b8c3f-241">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-241">Ordinal</span></span> | <span data-ttu-id="b8c3f-242">(quando o primeiro parâmetro é um `char` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-242">(when the first parameter is a `char`)</span></span> |
| `string.EndsWith` | <span data-ttu-id="b8c3f-243">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-243">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-244">(quando o primeiro parâmetro é um `string` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-244">(when the first parameter is a `string`)</span></span> |
| `string.Equals` | <span data-ttu-id="b8c3f-245">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-245">Ordinal</span></span> | |
| `string.GetHashCode` | <span data-ttu-id="b8c3f-246">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-246">Ordinal</span></span> | |
| `string.IndexOf` | <span data-ttu-id="b8c3f-247">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-247">Ordinal</span></span> | <span data-ttu-id="b8c3f-248">(quando o primeiro parâmetro é um `char` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-248">(when the first parameter is a `char`)</span></span> |
| `string.IndexOf` | <span data-ttu-id="b8c3f-249">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-249">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-250">(quando o primeiro parâmetro é um `string` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-250">(when the first parameter is a `string`)</span></span> |
| `string.IndexOfAny` | <span data-ttu-id="b8c3f-251">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-251">Ordinal</span></span> | |
| `string.LastIndexOf` | <span data-ttu-id="b8c3f-252">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-252">Ordinal</span></span> | <span data-ttu-id="b8c3f-253">(quando o primeiro parâmetro é um `char` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-253">(when the first parameter is a `char`)</span></span> |
| `string.LastIndexOf` | <span data-ttu-id="b8c3f-254">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-254">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-255">(quando o primeiro parâmetro é um `string` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-255">(when the first parameter is a `string`)</span></span> |
| `string.LastIndexOfAny` | <span data-ttu-id="b8c3f-256">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-256">Ordinal</span></span> | |
| `string.Replace` | <span data-ttu-id="b8c3f-257">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-257">Ordinal</span></span> | |
| `string.Split` | <span data-ttu-id="b8c3f-258">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-258">Ordinal</span></span> | |
| `string.StartsWith` | <span data-ttu-id="b8c3f-259">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-259">Ordinal</span></span> | <span data-ttu-id="b8c3f-260">(quando o primeiro parâmetro é um `char` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-260">(when the first parameter is a `char`)</span></span> |
| `string.StartsWith` | <span data-ttu-id="b8c3f-261">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-261">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-262">(quando o primeiro parâmetro é um `string` )</span><span class="sxs-lookup"><span data-stu-id="b8c3f-262">(when the first parameter is a `string`)</span></span> |
| `string.ToLower` | <span data-ttu-id="b8c3f-263">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-263">CurrentCulture</span></span> | |
| `string.ToLowerInvariant` | <span data-ttu-id="b8c3f-264">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-264">InvariantCulture</span></span> | |
| `string.ToUpper` | <span data-ttu-id="b8c3f-265">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-265">CurrentCulture</span></span> | |
| `string.ToUpperInvariant` | <span data-ttu-id="b8c3f-266">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-266">InvariantCulture</span></span> | |
| `string.Trim` | <span data-ttu-id="b8c3f-267">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-267">Ordinal</span></span> | |
| `string.TrimEnd` | <span data-ttu-id="b8c3f-268">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-268">Ordinal</span></span> | |
| `string.TrimStart` | <span data-ttu-id="b8c3f-269">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-269">Ordinal</span></span> | |
| `string == string` | <span data-ttu-id="b8c3f-270">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-270">Ordinal</span></span> | |
| `string != string` | <span data-ttu-id="b8c3f-271">Ordinal</span><span class="sxs-lookup"><span data-stu-id="b8c3f-271">Ordinal</span></span> | |

<span data-ttu-id="b8c3f-272">Ao contrário das `string` APIs, todas as `MemoryExtensions` APIs executam pesquisas e comparações *ordinais* por padrão, com as seguintes exceções.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-272">Unlike `string` APIs, all `MemoryExtensions` APIs perform *Ordinal* searches and comparisons by default, with the following exceptions.</span></span>

| <span data-ttu-id="b8c3f-273">API</span><span class="sxs-lookup"><span data-stu-id="b8c3f-273">API</span></span> | <span data-ttu-id="b8c3f-274">Comportamento padrão</span><span class="sxs-lookup"><span data-stu-id="b8c3f-274">Default behavior</span></span> | <span data-ttu-id="b8c3f-275">Comentários</span><span class="sxs-lookup"><span data-stu-id="b8c3f-275">Remarks</span></span> |
|---|---|---|
| `MemoryExtensions.ToLower` | <span data-ttu-id="b8c3f-276">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-276">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-277">(quando passado um `CultureInfo` argumento nulo)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-277">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToLowerInvariant` | <span data-ttu-id="b8c3f-278">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-278">InvariantCulture</span></span> | |
| `MemoryExtensions.ToUpper` | <span data-ttu-id="b8c3f-279">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-279">CurrentCulture</span></span> | <span data-ttu-id="b8c3f-280">(quando passado um `CultureInfo` argumento nulo)</span><span class="sxs-lookup"><span data-stu-id="b8c3f-280">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToUpperInvariant` | <span data-ttu-id="b8c3f-281">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="b8c3f-281">InvariantCulture</span></span> | |

<span data-ttu-id="b8c3f-282">Uma consequência é que, ao converter o código do consumo `string` para o consumo `ReadOnlySpan<char>` , as alterações comportamentais podem ser introduzidas inadvertidamente.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-282">A consequence is that when converting code from consuming `string` to consuming `ReadOnlySpan<char>`, behavioral changes may be introduced inadvertently.</span></span> <span data-ttu-id="b8c3f-283">Veja a seguir um exemplo disso.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-283">An example of this follows.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

<span data-ttu-id="b8c3f-284">A maneira recomendada para resolver isso é passar um parâmetro explícito `StringComparison` para essas APIs.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-284">The recommended way to address this is to pass an explicit `StringComparison` parameter to these APIs.</span></span> <span data-ttu-id="b8c3f-285">As regras de análise de código CA1307 e CA1309 podem ajudar com isso.</span><span class="sxs-lookup"><span data-stu-id="b8c3f-285">The code analysis rules CA1307 and CA1309 can assist with this.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a><span data-ttu-id="b8c3f-286">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8c3f-286">See also</span></span>

- [<span data-ttu-id="b8c3f-287">Alterações significativas de globalização</span><span class="sxs-lookup"><span data-stu-id="b8c3f-287">Globalization breaking changes</span></span>](../../core/compatibility/globalization.md)
- [<span data-ttu-id="b8c3f-288">Práticas recomendadas para comparar cadeias de caracteres no .NET</span><span class="sxs-lookup"><span data-stu-id="b8c3f-288">Best practices for comparing strings in .NET</span></span>](best-practices-strings.md)
- [<span data-ttu-id="b8c3f-289">Como comparar cadeias de caracteres no C#</span><span class="sxs-lookup"><span data-stu-id="b8c3f-289">How to compare strings in C#</span></span>](../../csharp/how-to/compare-strings.md)
- [<span data-ttu-id="b8c3f-290">Globalização e ICU do .NET</span><span class="sxs-lookup"><span data-stu-id="b8c3f-290">.NET globalization and ICU</span></span>](../globalization-localization/globalization-icu.md)
- [<span data-ttu-id="b8c3f-291">Operações de cadeia de caracteres ordinal e sensível à cultura</span><span class="sxs-lookup"><span data-stu-id="b8c3f-291">Ordinal vs. culture-sensitive string operations</span></span>](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [<span data-ttu-id="b8c3f-292">Visão geral da análise de código-fonte do .NET</span><span class="sxs-lookup"><span data-stu-id="b8c3f-292">Overview of .NET source code analysis</span></span>](../../fundamentals/code-analysis/overview.md)
