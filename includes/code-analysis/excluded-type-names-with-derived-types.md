---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366849"
---
### <a name="exclude-specific-types-and-their-derived-types"></a><span data-ttu-id="d7611-101">Excluir tipos específicos e seus tipos derivados</span><span class="sxs-lookup"><span data-stu-id="d7611-101">Exclude specific types and their derived types</span></span>

<span data-ttu-id="d7611-102">Você pode excluir tipos específicos e seus tipos derivados da análise.</span><span class="sxs-lookup"><span data-stu-id="d7611-102">You can exclude specific types and their derived types from analysis.</span></span> <span data-ttu-id="d7611-103">Por exemplo, para especificar que a regra não deve ser executada em nenhum método em tipos nomeados `MyType` e seus tipos derivados, adicione o seguinte par chave-valor a um arquivo *. editorconfig* em seu projeto:</span><span class="sxs-lookup"><span data-stu-id="d7611-103">For example, to specify that the rule should not run on any methods within types named `MyType` and their derived types, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

<span data-ttu-id="d7611-104">Formatos de nome de símbolo permitidos no valor de opção (separados por `|` ):</span><span class="sxs-lookup"><span data-stu-id="d7611-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="d7611-105">Digite somente Name (inclui todos os tipos com o nome, independentemente do tipo ou namespace que a contém)..</span><span class="sxs-lookup"><span data-stu-id="d7611-105">Type name only (includes all types with the name, regardless of the containing type or namespace)..</span></span>
- <span data-ttu-id="d7611-106">Nomes totalmente qualificados no [formato de ID de documentação](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)do símbolo, com um `T:` prefixo opcional.</span><span class="sxs-lookup"><span data-stu-id="d7611-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings), with an optional `T:` prefix.</span></span>

<span data-ttu-id="d7611-107">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="d7611-107">Examples:</span></span>

| <span data-ttu-id="d7611-108">Valor de Opção</span><span class="sxs-lookup"><span data-stu-id="d7611-108">Option Value</span></span> | <span data-ttu-id="d7611-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="d7611-109">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | <span data-ttu-id="d7611-110">Corresponde a todos os tipos chamados `MyType` e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="d7611-110">Matches all types named `MyType` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | <span data-ttu-id="d7611-111">Corresponde a todos os tipos chamados `MyType1` ou `MyType2` e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="d7611-111">Matches all types named either `MyType1` or `MyType2` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | <span data-ttu-id="d7611-112">Corresponde ao tipo específico `MyType` com o nome totalmente qualificado fornecido e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="d7611-112">Matches specific type `MyType` with given fully qualified name and all of its derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | <span data-ttu-id="d7611-113">Faz a correspondência `MyType1` de tipos específicos e `MyType2` com os respectivos nomes totalmente qualificados e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="d7611-113">Matches specific types `MyType1` and `MyType2` with the respective fully qualified names, and all of their derived types.</span></span> |
