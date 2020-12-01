---
title: Como preservar referências com System.Text.Json
description: Saiba como preservar referências e manipular referências circulares ao serializar e desserializar de JSON no .NET.
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
ms.openlocfilehash: 9254ca261c7d748c04c311fa56359014f752ff31
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439890"
---
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a>Como lidar com referências circulares com System.Text.Json

Neste artigo, você aprenderá a lidar com referências circulares com o `System.Text.Json` namespace.

## <a name="preserve-references-and-handle-circular-references"></a>Preservar referências e manipular referências circulares

::: zone pivot="dotnet-5-0"

Para preservar referências e manipular referências circulares, defina <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> como <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> . Essa configuração causa o seguinte comportamento:

* Em serializar:

  Ao escrever tipos complexos, o serializador também grava Propriedades de metadados ( `$id` , `$values` e `$ref` ).

* Ao desserializar:

  Os metadados são esperados (embora não obrigatórios) e o desserializador tenta compreendê-lo.

O código a seguir ilustra o uso da `Preserve` configuração.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Esse recurso não pode ser usado para preservar tipos de valor ou tipos imutáveis. Na desserialização, a instância de um tipo imutável é criada depois que a carga inteira é lida. Portanto, seria impossível desserializar a mesma instância se uma referência a ela aparecer dentro da carga JSON.

Para tipos de valor, tipos imutáveis e matrizes, nenhum metadado de referência é serializado. Na desserialização, uma exceção será lançada se `$ref` ou `$id` for encontrada. No entanto, os tipos de valor ignoram `$id` (e, `$values` no caso de coleções) para possibilitar a desserialização de cargas que foram serializadas usando Newtonsoft.Json .  Newtonsoft.Json Serializa metadados para esses tipos.

Para determinar se os objetos são iguais, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> , que usa igualdade de referência ( <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType> ) em vez de igualdade de valor ( <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> ao comparar duas instâncias de objeto.

Para obter mais informações sobre como as referências são serializadas e desserializadas, consulte <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType> .

A <xref:System.Text.Json.Serialization.ReferenceResolver> classe define o comportamento de preservar referências na serialização e desserialização. Crie uma classe derivada para especificar o comportamento personalizado. Para obter um exemplo, consulte [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json no .NET Core 3,1 dá suporte apenas a serialização por valor e gera uma exceção para referências circulares.
::: zone-end

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Criar instância de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitar correspondência que não diferencia maiúsculas de minúsculas](system-text-json-character-casing.md)
* [Personalizar nomes e valores de propriedade](system-text-json-customize-properties.md)
* [Ignorar Propriedades](system-text-json-ignore-properties.md)
* [Permitir JSON inválido](system-text-json-invalid-json.md)
* [Processar JSON de estouro](system-text-json-handle-overflow.md)
* [Tipos imutáveis e acessadores não públicos](system-text-json-immutability.md)
* [Serialização polimórfica](system-text-json-polymorphism.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
