---
title: 'Alteração significativa: a desserialização requer uma cadeia de caracteres de caractere único'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que JsonSerializer. Desserialize requer uma cadeia de caracteres de caractere único.
ms.date: 10/18/2020
ms.openlocfilehash: 780f2928d776ecb6db9a7fc05a720e889eb363e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760511"
---
# <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer. Desserialize requer cadeia de caracteres de caractere único

Quando o parâmetro de tipo é <xref:System.Char> , o argumento de cadeia de caracteres <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> deve conter um único caractere para que a desserialização tenha sucesso.

## <a name="change-description"></a>Descrição das alterações

Nas versões anteriores do .NET, se você passar uma cadeia de caracteres com vários caracteres para <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> e o parâmetro de tipo for <xref:System.Char> , a desserialização terá êxito e apenas o primeiro caractere será desserializado.

No .NET 5,0 e posterior, quando o parâmetro de tipo é <xref:System.Char> , a passagem de algo diferente de uma cadeia de caracteres de caractere único faz com que um seja <xref:System.Text.Json.JsonException> gerado.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>Versão introduzida

5.0

## <a name="reason-for-change"></a>Motivo da alteração

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> analisa o texto que representa um único valor JSON em uma instância do tipo especificado pelo parâmetro de tipo genérico. A análise só terá sucesso quando a carga fornecida for válida para o parâmetro de tipo genérico especificado. Para um <xref:System.Char> tipo de valor, uma carga válida é uma cadeia de caracteres única.

## <a name="recommended-action"></a>Ação recomendada

Ao analisar uma cadeia de caracteres em um <xref:System.Char> tipo usando <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> , verifique se a cadeia de caracteres consiste em um único caractere.

## <a name="affected-apis"></a>APIs afetadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
