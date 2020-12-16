---
ms.openlocfilehash: 4125df1d64fe7f3f2eb1eb4a821ed46c8270c95f
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97532001"
---
### <a name="exclude-specific-types-and-their-derived-types"></a><span data-ttu-id="b5ea9-101">Excluir tipos específicos e seus tipos derivados</span><span class="sxs-lookup"><span data-stu-id="b5ea9-101">Exclude specific types and their derived types</span></span>

<span data-ttu-id="b5ea9-102">Você pode excluir tipos específicos e seus tipos derivados da análise.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-102">You can exclude specific types and their derived types from analysis.</span></span> <span data-ttu-id="b5ea9-103">Por exemplo, para especificar que a regra não deve ser executada em nenhum método em tipos nomeados `MyType` e seus tipos derivados, adicione o seguinte par chave-valor a um arquivo *. editorconfig* em seu projeto:</span><span class="sxs-lookup"><span data-stu-id="b5ea9-103">For example, to specify that the rule should not run on any methods within types named `MyType` and their derived types, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

<span data-ttu-id="b5ea9-104">Formatos de nome de símbolo permitidos no valor de opção (separados por `|` ):</span><span class="sxs-lookup"><span data-stu-id="b5ea9-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="b5ea9-105">Somente nome de tipo (inclui todos os tipos com o nome, independentemente do tipo ou namespace que o contém).</span><span class="sxs-lookup"><span data-stu-id="b5ea9-105">Type name only (includes all types with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="b5ea9-106">Nomes totalmente qualificados no [formato de ID de documentação](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)do símbolo, com um `T:` prefixo opcional.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings), with an optional `T:` prefix.</span></span>

<span data-ttu-id="b5ea9-107">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="b5ea9-107">Examples:</span></span>

| <span data-ttu-id="b5ea9-108">Valor de Opção</span><span class="sxs-lookup"><span data-stu-id="b5ea9-108">Option Value</span></span> | <span data-ttu-id="b5ea9-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="b5ea9-109">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | <span data-ttu-id="b5ea9-110">Corresponde a todos os tipos chamados `MyType` e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-110">Matches all types named `MyType` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | <span data-ttu-id="b5ea9-111">Corresponde a todos os tipos chamados `MyType1` ou `MyType2` e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-111">Matches all types named either `MyType1` or `MyType2` and all of their derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | <span data-ttu-id="b5ea9-112">Corresponde ao tipo específico `MyType` com o nome totalmente qualificado fornecido e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-112">Matches specific type `MyType` with given fully qualified name and all of its derived types.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | <span data-ttu-id="b5ea9-113">Faz a correspondência `MyType1` de tipos específicos e `MyType2` com os respectivos nomes totalmente qualificados e todos os seus tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="b5ea9-113">Matches specific types `MyType1` and `MyType2` with the respective fully qualified names, and all of their derived types.</span></span> |
