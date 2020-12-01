---
title: Como permitir alguns tipos de JSON inválido com System.Text.Json
description: Saiba como permitir comentários, vírgulas à direita e números entre aspas ao serializar e desserializar de JSON no .NET.
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
ms.openlocfilehash: 60cbb98bb65ee5c1ffdd3043e42a04004530a115
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439884"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a><span data-ttu-id="13b3f-103">Como permitir alguns tipos de JSON inválido com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="13b3f-103">How to allow some kinds of invalid JSON with System.Text.Json</span></span>

<span data-ttu-id="13b3f-104">Neste artigo, você aprenderá como permitir comentários, vírgulas à direita e números entre aspas em JSON e como escrever números como cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="13b3f-104">In this article, you will learn how to allow comments, trailing commas, and quoted numbers in JSON, and how to write numbers as strings.</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="13b3f-105">Permitir comentários e vírgulas à direita</span><span class="sxs-lookup"><span data-stu-id="13b3f-105">Allow comments and trailing commas</span></span>

<span data-ttu-id="13b3f-106">Por padrão, comentários e vírgulas à direita não são permitidos em JSON.</span><span class="sxs-lookup"><span data-stu-id="13b3f-106">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="13b3f-107">Para permitir comentários no JSON, defina a <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> propriedade como `JsonCommentHandling.Skip` .</span><span class="sxs-lookup"><span data-stu-id="13b3f-107">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="13b3f-108">E para permitir vírgulas à direita, defina a <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> propriedade como `true` .</span><span class="sxs-lookup"><span data-stu-id="13b3f-108">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="13b3f-109">O exemplo a seguir mostra como permitir:</span><span class="sxs-lookup"><span data-stu-id="13b3f-109">The following example shows how to allow both:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

<span data-ttu-id="13b3f-110">Aqui está um exemplo de JSON com comentários e uma vírgula à direita:</span><span class="sxs-lookup"><span data-stu-id="13b3f-110">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="13b3f-111">Permitir ou gravar números entre aspas</span><span class="sxs-lookup"><span data-stu-id="13b3f-111">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="13b3f-112">Alguns serializadores codificam números como cadeias de caracteres JSON (entre aspas).</span><span class="sxs-lookup"><span data-stu-id="13b3f-112">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span>

<span data-ttu-id="13b3f-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="13b3f-113">For example:</span></span>

```json
{
    "DegreesCelsius": "23"
}
```

<span data-ttu-id="13b3f-114">Em vez de:</span><span class="sxs-lookup"><span data-stu-id="13b3f-114">Instead of:</span></span>

```json
{
    "DegreesCelsius": 23
}
```

<span data-ttu-id="13b3f-115">Para serializar números entre aspas ou aceitar números entre aspas em todo o grafo de objeto de entrada, defina <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="13b3f-115">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

<span data-ttu-id="13b3f-116">Quando você usa `System.Text.Json` indiretamente por meio de ASP.NET Core, são permitidos números entre aspas ao desserializar porque ASP.NET Core especifica [opções padrão da Web](xref:System.Text.Json.JsonSerializerDefaults.Web).</span><span class="sxs-lookup"><span data-stu-id="13b3f-116">When you use `System.Text.Json` indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="13b3f-117">Para permitir ou gravar números entre aspas para propriedades, campos ou tipos específicos, use o atributo [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) .</span><span class="sxs-lookup"><span data-stu-id="13b3f-117">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="13b3f-118">`System.Text.Json` no .NET Core 3,1 não dá suporte à serialização ou desserialização de números entre aspas.</span><span class="sxs-lookup"><span data-stu-id="13b3f-118">`System.Text.Json` in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="13b3f-119">Para obter mais informações, consulte [permitir ou gravar números entre aspas](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span><span class="sxs-lookup"><span data-stu-id="13b3f-119">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="13b3f-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="13b3f-120">See also</span></span>

* [<span data-ttu-id="13b3f-121">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="13b3f-121">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="13b3f-122">Criar instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="13b3f-122">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="13b3f-123">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="13b3f-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="13b3f-124">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="13b3f-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="13b3f-125">Ignorar Propriedades</span><span class="sxs-lookup"><span data-stu-id="13b3f-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="13b3f-126">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="13b3f-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="13b3f-127">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="13b3f-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="13b3f-128">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="13b3f-128">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="13b3f-129">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="13b3f-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="13b3f-130">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="13b3f-130">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
