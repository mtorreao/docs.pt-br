---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366849"
---
### <a name="exclude-specific-types-and-their-derived-types"></a>Excluir tipos específicos e seus tipos derivados

Você pode excluir tipos específicos e seus tipos derivados da análise. Por exemplo, para especificar que a regra não deve ser executada em nenhum método em tipos nomeados `MyType` e seus tipos derivados, adicione o seguinte par chave-valor a um arquivo *. editorconfig* em seu projeto:

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

Formatos de nome de símbolo permitidos no valor de opção (separados por `|` ):

- Digite somente Name (inclui todos os tipos com o nome, independentemente do tipo ou namespace que a contém)..
- Nomes totalmente qualificados no [formato de ID de documentação](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)do símbolo, com um `T:` prefixo opcional.

Exemplos:

| Valor de Opção | Resumo |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | Corresponde a todos os tipos chamados `MyType` e todos os seus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | Corresponde a todos os tipos chamados `MyType1` ou `MyType2` e todos os seus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | Corresponde ao tipo específico `MyType` com o nome totalmente qualificado fornecido e todos os seus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | Faz a correspondência `MyType1` de tipos específicos e `MyType2` com os respectivos nomes totalmente qualificados e todos os seus tipos derivados. |
