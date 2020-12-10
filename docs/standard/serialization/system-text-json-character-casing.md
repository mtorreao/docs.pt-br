---
title: Como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com System.Text.Json
description: Saiba como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas ao serializar e desserializar de JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3e2fb8cbdd35e772b5e97c731199f69aa834bd0a
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009736"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="58dda-103">Como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="58dda-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="58dda-104">Neste artigo, você aprenderá a habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="58dda-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="58dda-105">Correspondência de propriedade que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="58dda-105">Case-insensitive property matching</span></span>

<span data-ttu-id="58dda-106">Por padrão, a desserialização procura as correspondências de nome de propriedade que diferenciam maiúsculas de minúsculas entre JSON e as propriedades do objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="58dda-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="58dda-107">Para alterar esse comportamento, defina <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> como `true` :</span><span class="sxs-lookup"><span data-stu-id="58dda-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="58dda-108">O [padrão da Web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="58dda-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="58dda-109">Aqui está um exemplo de JSON com nomes de Propriedade do camel case.</span><span class="sxs-lookup"><span data-stu-id="58dda-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="58dda-110">Ele pode ser desserializado no seguinte tipo que tem nomes de propriedade de caso de Pascal.</span><span class="sxs-lookup"><span data-stu-id="58dda-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="58dda-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="58dda-111">See also</span></span>

* [<span data-ttu-id="58dda-112">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="58dda-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="58dda-113">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="58dda-113">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="58dda-114">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="58dda-114">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="58dda-115">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="58dda-115">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="58dda-116">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="58dda-116">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="58dda-117">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="58dda-117">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="58dda-118">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="58dda-118">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="58dda-119">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="58dda-119">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="58dda-120">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="58dda-120">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="58dda-121">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="58dda-121">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="58dda-122">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="58dda-122">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="58dda-123">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="58dda-123">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="58dda-124">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="58dda-124">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="58dda-125">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="58dda-125">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="58dda-126">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="58dda-126">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="58dda-127">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="58dda-127">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="58dda-128">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="58dda-128">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
