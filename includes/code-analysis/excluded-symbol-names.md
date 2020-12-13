---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366854"
---
### <a name="exclude-specific-symbols"></a><span data-ttu-id="1198a-101">Excluir símbolos específicos</span><span class="sxs-lookup"><span data-stu-id="1198a-101">Exclude specific symbols</span></span>

<span data-ttu-id="1198a-102">Você pode excluir símbolos específicos, como tipos e métodos, da análise.</span><span class="sxs-lookup"><span data-stu-id="1198a-102">You can exclude specific symbols, such as types and methods, from analysis.</span></span> <span data-ttu-id="1198a-103">Por exemplo, para especificar que a regra não deve ser executada em nenhum código dentro de tipos nomeados `MyType` , adicione o seguinte par chave-valor a um arquivo *. editorconfig* em seu projeto:</span><span class="sxs-lookup"><span data-stu-id="1198a-103">For example, to specify that the rule should not run on any code within types named `MyType`, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

<span data-ttu-id="1198a-104">Formatos de nome de símbolo permitidos no valor de opção (separados por `|` ):</span><span class="sxs-lookup"><span data-stu-id="1198a-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="1198a-105">Somente nome do símbolo (inclui todos os símbolos com o nome, independentemente do tipo ou namespace que o contém).</span><span class="sxs-lookup"><span data-stu-id="1198a-105">Symbol name only (includes all symbols with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="1198a-106">Nomes totalmente qualificados no [formato de ID de documentação](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)do símbolo.</span><span class="sxs-lookup"><span data-stu-id="1198a-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings).</span></span> <span data-ttu-id="1198a-107">Cada nome de símbolo requer um prefixo de tipo de símbolo, como `M:` para métodos, `T:` para tipos e `N:` para namespaces.</span><span class="sxs-lookup"><span data-stu-id="1198a-107">Each symbol name requires a symbol-kind prefix, such as `M:` for methods, `T:` for types, and `N:` for namespaces.</span></span>
- <span data-ttu-id="1198a-108">`.ctor` para construtores e `.cctor` para construtores estáticos.</span><span class="sxs-lookup"><span data-stu-id="1198a-108">`.ctor` for constructors and `.cctor` for static constructors.</span></span>

<span data-ttu-id="1198a-109">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="1198a-109">Examples:</span></span>

| <span data-ttu-id="1198a-110">Valor de Opção</span><span class="sxs-lookup"><span data-stu-id="1198a-110">Option Value</span></span> | <span data-ttu-id="1198a-111">Resumo</span><span class="sxs-lookup"><span data-stu-id="1198a-111">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | <span data-ttu-id="1198a-112">Corresponde a todos os símbolos chamados `MyType` .</span><span class="sxs-lookup"><span data-stu-id="1198a-112">Matches all symbols named `MyType`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | <span data-ttu-id="1198a-113">Corresponde a todos os símbolos nomeados `MyType1` ou `MyType2` .</span><span class="sxs-lookup"><span data-stu-id="1198a-113">Matches all symbols named either `MyType1` or `MyType2`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | <span data-ttu-id="1198a-114">Corresponde ao método específico `MyMethod` com a assinatura totalmente qualificada especificada.</span><span class="sxs-lookup"><span data-stu-id="1198a-114">Matches specific method `MyMethod` with the specified fully qualified signature.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | <span data-ttu-id="1198a-115">O corresponde a métodos específicos `MyMethod1` e `MyMethod2` com as respectivas assinaturas totalmente qualificadas.</span><span class="sxs-lookup"><span data-stu-id="1198a-115">Matches specific methods `MyMethod1` and `MyMethod2` with the respective fully qualified signatures.</span></span> |
