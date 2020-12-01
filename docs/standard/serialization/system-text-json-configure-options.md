---
title: Como criar uma instância de JsonSerializerOptions com System.Text.Json
description: Saiba como instanciar instâncias JsonSerializerOptions copiando instâncias existentes ou com padrões da Web.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439910"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Como instanciar instâncias JsonSerializerOptions com System.Text.Json

Neste artigo, você aprenderá como instanciar <xref:System.Text.Json.JsonSerializerOptions> instâncias copiando instâncias existentes ou com padrões da Web.

## <a name="copy-jsonserializeroptions"></a>Copiar JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerOptions)) que permite criar uma nova instância com as mesmas opções de uma instância existente, conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Um `JsonSerializerOptions` Construtor que usa uma instância existente não está disponível no .NET Core 3,1.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Padrões da Web para JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Aqui estão as opções que têm padrões diferentes para aplicativos Web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerDefaults)? View = NET-5,0&preserve-View = true) que permite criar uma nova instância com as opções padrão que ASP.NET Core usa para aplicativos Web, conforme mostrado no exemplo a seguir:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Aqui estão as opções que têm padrões diferentes para aplicativos Web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Um `JsonSerializerOptions` Construtor que especifica um conjunto de padrões não está disponível no .NET Core 3,1.
::: zone-end

## <a name="see-also"></a>Confira também

* [System.Text.Json sobre](system-text-json-overview.md)
* [Habilitar correspondência que não diferencia maiúsculas de minúsculas](system-text-json-character-casing.md)
* [Personalizar nomes e valores de propriedade](system-text-json-customize-properties.md)
* [Ignorar Propriedades](system-text-json-ignore-properties.md)
* [Permitir JSON inválido](system-text-json-invalid-json.md)
* [Processar JSON de estouro](system-text-json-handle-overflow.md)
* [Preservar referências circulares](system-text-json-preserve-references.md)
* [Tipos imutáveis e acessadores não públicos](system-text-json-immutability.md)
* [Serialização polimórfica](system-text-json-polymorphism.md)
* [System.Text.Json Referência de API](xref:System.Text.Json)
