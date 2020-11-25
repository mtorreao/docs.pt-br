---
title: 'Alteração significativa: StringInfo e TextElementEnumerator agora são compatíveis com UAX29'
description: Saiba mais sobre a alteração significativa de globalização no .NET 5,0 em que StringInfo e TextElementEnumerator processam clusters grafemas de acordo com a versão mais recente do padrão Unicode.
ms.date: 04/07/2020
ms.openlocfilehash: cd5ae5a3eb9f2dd9c02bc179a40d454d24101199
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760324"
---
# <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="da5b1-103">StringInfo e TextElementEnumerator agora são compatíveis com UAX29</span><span class="sxs-lookup"><span data-stu-id="da5b1-103">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="da5b1-104">Antes dessa alteração, <xref:System.Globalization.StringInfo?displayProperty=fullName> e <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> não tratamos adequadamente de todos os clusters do grafemas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-104">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="da5b1-105">Algumas graphemes foram divididas em seus componentes constituintes em vez de serem mantidas juntas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-105">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="da5b1-106">Agora, <xref:System.Globalization.StringInfo> e <xref:System.Globalization.TextElementEnumerator> processe os clusters grafemas de acordo com a versão mais recente do padrão Unicode.</span><span class="sxs-lookup"><span data-stu-id="da5b1-106">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="da5b1-107">Além disso, o <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> método, que reverte os caracteres em uma cadeia de caracteres em Visual Basic, agora também segue o padrão Unicode para clusters grafemas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-107">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

## <a name="change-description"></a><span data-ttu-id="da5b1-108">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="da5b1-108">Change description</span></span>

<span data-ttu-id="da5b1-109">Um cluster [grafemas](https://www.unicode.org/glossary/#grapheme) ou [grafemas estendido](https://www.unicode.org/glossary/#extended_grapheme_cluster) é um único caractere percebido pelo usuário que pode ser composto por vários pontos de código Unicode.</span><span class="sxs-lookup"><span data-stu-id="da5b1-109">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="da5b1-110">Por exemplo, a cadeia de caracteres que contém o caractere Tai "Kam" ( :::no-loc text="กำ"::: ) consiste nos dois caracteres a seguir:</span><span class="sxs-lookup"><span data-stu-id="da5b1-110">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="da5b1-111">:::no-loc text="ก"::: (= ' \u0e01 ') CARACTERE TAI KO KAI</span><span class="sxs-lookup"><span data-stu-id="da5b1-111">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="da5b1-112">:::no-loc text=" ำ"::: (= ' \u0e33 ') CARACTERE TAI SARA AM</span><span class="sxs-lookup"><span data-stu-id="da5b1-112">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="da5b1-113">Quando exibido para o usuário, o sistema operacional combina os dois caracteres para formar o único caractere de exibição (ou grafemas) "Kam" ou :::no-loc text="กำ"::: .</span><span class="sxs-lookup"><span data-stu-id="da5b1-113">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="da5b1-114">O emoji também pode consistir em vários caracteres que são combinados para exibição de forma semelhante.</span><span class="sxs-lookup"><span data-stu-id="da5b1-114">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="da5b1-115">A documentação do .NET às vezes usa o termo "elemento de texto" ao fazer referência a um grafemas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-115">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="da5b1-116">As <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classes e inspecionam cadeias de caracteres e retornam informações sobre as graphemes que elas contêm.</span><span class="sxs-lookup"><span data-stu-id="da5b1-116">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="da5b1-117">No .NET Framework (todas as versões) e no .NET Core 3. x e versões anteriores, essas duas classes usam lógica personalizada que lida com algumas classes combinadoras, mas que não está totalmente em conformidade com o [padrão Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span><span class="sxs-lookup"><span data-stu-id="da5b1-117">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="da5b1-118">Por exemplo, as <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classes e dividem incorretamente o caractere Tai único "Kam" de volta em seus componentes constituintes em vez de mantê-los juntos.</span><span class="sxs-lookup"><span data-stu-id="da5b1-118">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="da5b1-119">Essas classes também dividem incorretamente o caractere de Emoji "🤷🏽 ♀️" em quatro clusters (pessoa shrugging, modificador de Tom de pele, modificador de sexo e um combinador invisível) em vez de mantê-los juntos como um único cluster grafemas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-119">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="da5b1-120">A partir do .NET 5, <xref:System.Globalization.StringInfo> as <xref:System.Globalization.TextElementEnumerator> classes e implementam o padrão Unicode conforme definido pelo [anexo 29 do padrão Unicode \# , Rev. 35, seg. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span><span class="sxs-lookup"><span data-stu-id="da5b1-120">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="da5b1-121">Em particular, eles agora retornam [clusters grafemas estendidos](https://www.unicode.org/glossary/#extended_grapheme_cluster) para todas as classes combinadas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-121">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="da5b1-122">Considere o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="da5b1-122">Consider the following C# code:</span></span>

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="da5b1-123">No .NET Framework e no .NET Core 3. x e versões anteriores, os graphemes são divididos e a saída do console é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="da5b1-123">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="da5b1-124">No .NET 5 e versões posteriores, os graphemes são mantidos juntos e a saída do console é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="da5b1-124">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="da5b1-125">Além disso, a partir do .NET 5, o <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> método, que reverte os caracteres em uma cadeia de caracteres em Visual Basic, agora também segue o padrão Unicode para clusters grafemas.</span><span class="sxs-lookup"><span data-stu-id="da5b1-125">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="da5b1-126">Essas alterações fazem parte de um conjunto mais amplo de aprimoramentos de Unicode e UTF-8 no .NET, incluindo uma API de enumeração de cluster grafemas estendida para complementar as APIs de enumeração de valor escalar Unicode que foram introduzidas com o <xref:System.Text.Rune?displayProperty=fullName> tipo no .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="da5b1-126">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="da5b1-127">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="da5b1-127">Version introduced</span></span>

<span data-ttu-id="da5b1-128">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="da5b1-128">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="da5b1-129">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="da5b1-129">Recommended action</span></span>

<span data-ttu-id="da5b1-130">Você não precisa realizar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="da5b1-130">You don't need to take any action.</span></span> <span data-ttu-id="da5b1-131">Seus aplicativos se comportarão automaticamente em uma maneira mais compatível com padrões em uma variedade de cenários relacionados à globalização.</span><span class="sxs-lookup"><span data-stu-id="da5b1-131">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="da5b1-132">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="da5b1-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

### Category

Globalization

-->
