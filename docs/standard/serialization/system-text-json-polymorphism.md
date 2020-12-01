---
title: Como serializar Propriedades de classes derivadas com System.Text.Json
description: Saiba como serializar objetos polimórficos ao serializar e desserializar de JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 4b99a402ea4f4c664d3bfd75627ffaf94948d493
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439891"
---
# <a name="how-to-serialize-properties-of-derived-classes-with-no-locsystemtextjson"></a><span data-ttu-id="afe87-103">Como serializar Propriedades de classes derivadas com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="afe87-103">How to serialize properties of derived classes with System.Text.Json</span></span>

<span data-ttu-id="afe87-104">Neste artigo, você aprenderá a serializar Propriedades de classes derivadas com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="afe87-104">In this article, you will learn how to serialize properties of derived classes with the `System.Text.Json` namespace.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="afe87-105">Serializar Propriedades de classes derivadas</span><span class="sxs-lookup"><span data-stu-id="afe87-105">Serialize properties of derived classes</span></span>

<span data-ttu-id="afe87-106">_Não_ há suporte para a serialização de uma hierarquia de tipo polimórfico.</span><span class="sxs-lookup"><span data-stu-id="afe87-106">Serialization of a polymorphic type hierarchy is _not_ supported.</span></span> <span data-ttu-id="afe87-107">Por exemplo, se uma propriedade for definida como uma interface ou uma classe abstrata, somente as propriedades definidas na interface ou na classe abstrata serão serializadas, mesmo que o tipo de tempo de execução tenha propriedades adicionais.</span><span class="sxs-lookup"><span data-stu-id="afe87-107">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="afe87-108">As exceções a esse comportamento são explicadas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="afe87-108">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="afe87-109">Por exemplo, suponha que você tenha uma `WeatherForecast` classe e uma classe derivada `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="afe87-109">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFDerived":::

<span data-ttu-id="afe87-110">E suponha que o argumento de tipo do `Serialize` método em tempo de compilação seja `WeatherForecast` :</span><span class="sxs-lookup"><span data-stu-id="afe87-110">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeDefault":::

<span data-ttu-id="afe87-111">Nesse cenário, a `WindSpeed` propriedade não é serializada, mesmo que o `weatherForecast` objeto seja, na verdade, um `WeatherForecastDerived` objeto.</span><span class="sxs-lookup"><span data-stu-id="afe87-111">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="afe87-112">Somente as propriedades da classe base são serializadas:</span><span class="sxs-lookup"><span data-stu-id="afe87-112">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="afe87-113">Esse comportamento destina-se a ajudar a evitar a exposição acidental de dados em um tipo criado de tempo de execução derivado.</span><span class="sxs-lookup"><span data-stu-id="afe87-113">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="afe87-114">Para serializar as propriedades do tipo derivado no exemplo anterior, use uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="afe87-114">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="afe87-115">Chame uma sobrecarga de <xref:System.Text.Json.JsonSerializer.Serialize%2A> que permite especificar o tipo em tempo de execução:</span><span class="sxs-lookup"><span data-stu-id="afe87-115">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeGetType":::

* <span data-ttu-id="afe87-116">Declare o objeto a ser serializado como `object` .</span><span class="sxs-lookup"><span data-stu-id="afe87-116">Declare the object to be serialized as `object`.</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeObject":::

<span data-ttu-id="afe87-117">No cenário de exemplo anterior, ambas as abordagens fazem com que a `WindSpeed` propriedade seja incluída na saída JSON:</span><span class="sxs-lookup"><span data-stu-id="afe87-117">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="afe87-118">Essas abordagens fornecem serialização polimórfica somente para o objeto raiz a ser serializado, não para propriedades desse objeto raiz.</span><span class="sxs-lookup"><span data-stu-id="afe87-118">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="afe87-119">Você pode obter a serialização polimórfica para objetos de nível inferior se defini-los como tipo `object` .</span><span class="sxs-lookup"><span data-stu-id="afe87-119">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="afe87-120">Por exemplo, suponha que sua `WeatherForecast` classe tenha uma propriedade chamada `PreviousForecast` que possa ser definida como tipo `WeatherForecast` ou `object` :</span><span class="sxs-lookup"><span data-stu-id="afe87-120">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPrevious":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPreviousAsObject":::

<span data-ttu-id="afe87-121">Se a `PreviousForecast` Propriedade contiver uma instância de `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="afe87-121">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="afe87-122">A saída JSON da serialização `WeatherForecastWithPrevious` **não inclui** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="afe87-122">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="afe87-123">A saída JSON da serialização `WeatherForecastWithPreviousAsObject` **inclui** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="afe87-123">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="afe87-124">Para serializar `WeatherForecastWithPreviousAsObject` , não é necessário chamar `Serialize<object>` ou `GetType` porque o objeto raiz não é aquele que pode ser de um tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="afe87-124">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="afe87-125">O exemplo de código a seguir não chama `Serialize<object>` ou `GetType` :</span><span class="sxs-lookup"><span data-stu-id="afe87-125">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeSecondLevel":::

<span data-ttu-id="afe87-126">O código anterior serializa corretamente `WeatherForecastWithPreviousAsObject` :</span><span class="sxs-lookup"><span data-stu-id="afe87-126">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="afe87-127">A mesma abordagem de definir propriedades como `object` funciona com interfaces.</span><span class="sxs-lookup"><span data-stu-id="afe87-127">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="afe87-128">Suponha que você tenha a seguinte interface e implementação e queira serializar uma classe com propriedades que contêm instâncias de implementação:</span><span class="sxs-lookup"><span data-stu-id="afe87-128">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/IForecast.cs":::

<span data-ttu-id="afe87-129">Quando você serializa uma instância do `Forecasts` , `Tuesday` o mostra apenas a `WindSpeed` propriedade, porque `Tuesday` é definido como `object` :</span><span class="sxs-lookup"><span data-stu-id="afe87-129">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs" id="SerializeInterface":::

<span data-ttu-id="afe87-130">O exemplo a seguir mostra o JSON que resulta do código anterior:</span><span class="sxs-lookup"><span data-stu-id="afe87-130">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="afe87-131">Para obter mais informações sobre a **serialização** polimórfica e informações sobre a **desserialização**, consulte [como migrar do Newtonsoft.Json para System.Text.Json o](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="afe87-131">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="see-also"></a><span data-ttu-id="afe87-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="afe87-132">See also</span></span>

* [<span data-ttu-id="afe87-133">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="afe87-133">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="afe87-134">Criar instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="afe87-134">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="afe87-135">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="afe87-135">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="afe87-136">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="afe87-136">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="afe87-137">Ignorar Propriedades</span><span class="sxs-lookup"><span data-stu-id="afe87-137">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="afe87-138">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="afe87-138">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="afe87-139">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="afe87-139">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="afe87-140">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="afe87-140">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="afe87-141">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="afe87-141">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* <span data-ttu-id="afe87-142">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="afe87-142">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
