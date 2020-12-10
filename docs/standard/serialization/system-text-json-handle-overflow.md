---
title: Como lidar com o JSON de estouro com System.Text.Json
description: Saiba como lidar com o JSON de estouro ao serializar e desserializar do JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 265ce4f77d353720419122d17c36e508a377b68f
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008910"
---
# <a name="how-to-handle-overflow-json-with-no-locsystemtextjson"></a><span data-ttu-id="37de8-103">Como lidar com o JSON de estouro com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="37de8-103">How to handle overflow JSON with System.Text.Json</span></span>

<span data-ttu-id="37de8-104">Neste artigo, você aprenderá a manipular o JSON de estouro com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="37de8-104">In this article, you will learn how to handle overflow JSON with the `System.Text.Json` namespace.</span></span>

## <a name="handle-overflow-json"></a><span data-ttu-id="37de8-105">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="37de8-105">Handle overflow JSON</span></span>

<span data-ttu-id="37de8-106">Durante a desserialização, você pode receber dados no JSON que não são representados pelas propriedades do tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="37de8-106">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="37de8-107">Por exemplo, suponha que o tipo de destino seja o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37de8-107">For example, suppose your target type is this:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="37de8-108">E o JSON a ser desserializado é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="37de8-108">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="37de8-109">Se você desserializar o JSON mostrado no tipo mostrado, as `DatesAvailable` Propriedades e `SummaryWords` ficarão sem lugar e serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="37de8-109">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="37de8-110">Para capturar dados adicionais, como essas propriedades, aplique o atributo [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a uma propriedade do tipo `Dictionary<string,object>` ou `Dictionary<string,JsonElement>` :</span><span class="sxs-lookup"><span data-stu-id="37de8-110">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithExtensionData":::

<span data-ttu-id="37de8-111">Quando você desserializar o JSON mostrado anteriormente neste tipo de exemplo, os dados extras se tornarão pares de chave-valor da `ExtensionData` Propriedade:</span><span class="sxs-lookup"><span data-stu-id="37de8-111">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

| <span data-ttu-id="37de8-112">Propriedade</span><span class="sxs-lookup"><span data-stu-id="37de8-112">Property</span></span> | <span data-ttu-id="37de8-113">Valor</span><span class="sxs-lookup"><span data-stu-id="37de8-113">Value</span></span> | <span data-ttu-id="37de8-114">Observações</span><span class="sxs-lookup"><span data-stu-id="37de8-114">Notes</span></span> |
|--|--|--|
| `Date` | `"8/1/2019 12:00:00 AM -07:00"` |  |
| `TemperatureCelsius` | `0` | <span data-ttu-id="37de8-115">Incompatibilidade de maiúsculas e minúsculas ( `temperatureCelsius` no JSON), portanto, a propriedade não está definida.</span><span class="sxs-lookup"><span data-stu-id="37de8-115">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| `Summary` | `"Hot"` |  |
| `ExtensionData` | `temperatureCelsius: 25` | <span data-ttu-id="37de8-116">Como o caso não corresponde, essa propriedade JSON é um extra e se torna um par chave-valor no dicionário.</span><span class="sxs-lookup"><span data-stu-id="37de8-116">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span> |
| `DatesAvailable` | `[ "8/1/2019 12:00:00 AM -07:00", "8/2/2019 12:00:00 AM -07:00" ]` | <span data-ttu-id="37de8-117">A propriedade extra do JSON torna-se um par chave-valor, com uma matriz como o objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="37de8-117">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |
| `SummaryWords` | `[ "Cool", "Windy", "Humid" ]` | <span data-ttu-id="37de8-118">A propriedade extra do JSON torna-se um par chave-valor, com uma matriz como o objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="37de8-118">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span> |

<span data-ttu-id="37de8-119">Quando o objeto de destino é serializado, os pares de valor de chave de dados de extensão se tornam propriedades JSON, assim como no JSON de entrada:</span><span class="sxs-lookup"><span data-stu-id="37de8-119">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="37de8-120">Observe que o `ExtensionData` nome da propriedade não aparece no JSON.</span><span class="sxs-lookup"><span data-stu-id="37de8-120">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="37de8-121">Esse comportamento permite que o JSON faça uma viagem de ida e volta sem perder nenhum dado extra que, de outra forma, não seria desserializado.</span><span class="sxs-lookup"><span data-stu-id="37de8-121">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="see-also"></a><span data-ttu-id="37de8-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="37de8-122">See also</span></span>

* [<span data-ttu-id="37de8-123">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="37de8-123">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="37de8-124">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="37de8-124">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="37de8-125">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="37de8-125">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="37de8-126">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="37de8-126">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="37de8-127">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="37de8-127">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="37de8-128">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="37de8-128">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="37de8-129">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="37de8-129">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="37de8-130">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="37de8-130">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="37de8-131">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="37de8-131">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="37de8-132">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="37de8-132">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="37de8-133">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="37de8-133">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="37de8-134">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="37de8-134">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="37de8-135">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="37de8-135">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="37de8-136">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="37de8-136">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="37de8-137">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="37de8-137">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="37de8-138">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="37de8-138">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="37de8-139">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="37de8-139">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
