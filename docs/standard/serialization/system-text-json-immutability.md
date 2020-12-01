---
title: Como usar tipos imutáveis e acessadores não públicos com System.Text.Json
description: Saiba como usar tipos imutáveis e acessadores não públicos ao serializar e desserializar de JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439888"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a>Como usar tipos imutáveis e acessadores não públicos com System.Text.Json

Neste artigo, você aprenderá a usar tipos imutáveis, como registros, com o `System.Text.Json` namespace.

## <a name="immutable-types-and-records"></a>Tipos e registros imutáveis

::: zone pivot="dotnet-5-0"
`System.Text.Json` pode usar um construtor com parâmetros, o que torna possível desserializar uma classe ou estrutura imutável. Para uma classe, se o único Construtor for um parametrizado, esse construtor será usado. Para uma struct ou uma classe com vários construtores, especifique o que deve ser usado aplicando o atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) . Quando o atributo não é usado, um construtor público sem parâmetros é sempre usado, se estiver presente. O atributo só pode ser usado com construtores públicos. O exemplo a seguir usa o `[JsonConstructor]` atributo:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

Também há suporte para registros no C# 9, conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

Para tipos que são imutáveis porque todos os seus setters de propriedade são não públicos, consulte a seção a seguir sobre [acessadores de propriedade não pública](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` e o suporte a registros do C# 9 não está disponível no .NET Core 3,1.
::: zone-end

## <a name="non-public-property-accessors"></a>Acessadores de propriedade não pública

::: zone pivot="dotnet-5-0"
Para habilitar o uso de um acessador de propriedade não público, use o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) , conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Não há suporte para acessadores de propriedade não pública no .NET Core 3,1. Para obter mais informações, consulte [o Newtonsoft.Json artigo migrar de](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Criar instância de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitar correspondência que não diferencia maiúsculas de minúsculas](system-text-json-character-casing.md)
* [Personalizar nomes e valores de propriedade](system-text-json-customize-properties.md)
* [Ignorar Propriedades](system-text-json-ignore-properties.md)
* [Permitir JSON inválido](system-text-json-invalid-json.md)
* [Processar JSON de estouro](system-text-json-handle-overflow.md)
* [Preservar referências circulares](system-text-json-preserve-references.md)
* [Serialização polimórfica](system-text-json-polymorphism.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
