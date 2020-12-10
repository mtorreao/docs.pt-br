---
title: Como criar uma instância de JsonSerializerOptions com System.Text.Json
description: Saiba como evitar problemas de desempenho e como usar construtores disponíveis para instâncias de JsonSerializerOptions.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009827"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="e3d7b-103">Como instanciar instâncias JsonSerializerOptions com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="e3d7b-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="e3d7b-104">Este artigo explica como evitar problemas de desempenho ao usar o <xref:System.Text.Json.JsonSerializerOptions> .</span><span class="sxs-lookup"><span data-stu-id="e3d7b-104">This article explains how to avoid performance problems when you use <xref:System.Text.Json.JsonSerializerOptions>.</span></span> <span data-ttu-id="e3d7b-105">Ele também mostra como usar os construtores com parâmetros que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-105">It also shows how to use the parameterized constructors that are available.</span></span>

## <a name="reuse-jsonserializeroptions-instances"></a><span data-ttu-id="e3d7b-106">Reutilizar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="e3d7b-106">Reuse JsonSerializerOptions instances</span></span>

<span data-ttu-id="e3d7b-107">Se você usar `JsonSerializerOptions` repetidamente com as mesmas opções, não crie uma nova `JsonSerializerOptions` instância toda vez que usá-la.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-107">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="e3d7b-108">Reutilize a mesma instância para cada chamada.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-108">Reuse the same instance for every call.</span></span> <span data-ttu-id="e3d7b-109">Esta orientação se aplica ao código que você escreve para conversores personalizados e quando você chama <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> ou <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e3d7b-109">This guidance applies to code you write for custom converters and when you call <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> or <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="e3d7b-110">O código a seguir demonstra a penalidade de desempenho para usar novas instâncias de opções.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-110">The following code demonstrates the performance penalty for using new options instances.</span></span>

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

<span data-ttu-id="e3d7b-111">O código anterior serializa um objeto pequeno 100.000 vezes usando a mesma instância de opções.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-111">The preceding code serializes a small object 100,000 times using the same options instance.</span></span> <span data-ttu-id="e3d7b-112">Em seguida, ele serializa o mesmo objeto, o mesmo número de vezes, e cria uma nova instância de opções a cada vez.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-112">Then it serializes the same object the same number of times and creates a new options instance each time.</span></span> <span data-ttu-id="e3d7b-113">Uma diferença típica de tempo de execução é 190 em comparação com 40.140 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-113">A typical run time difference is 190 compared to 40,140 milliseconds.</span></span> <span data-ttu-id="e3d7b-114">A diferença é ainda maior se você aumentar o número de iterações.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-114">The difference is even greater if you increase the number of iterations.</span></span>

<span data-ttu-id="e3d7b-115">O serializador passa por uma fase de aquecimento durante a primeira serialização de cada tipo no grafo do objeto quando uma nova instância de opções é passada para ele.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-115">The serializer undergoes a warm-up phase during the first serialization of each type in the object graph when a new options instance is passed to it.</span></span> <span data-ttu-id="e3d7b-116">Esse aquecimento inclui a criação de um cache de metadados que são necessários para a serialização.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-116">This warm-up includes creating a cache of metadata that is needed for serialization.</span></span> <span data-ttu-id="e3d7b-117">Os metadados incluem delegados para getters de propriedade, setters, argumentos de construtor, atributos especificados e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-117">The metadata includes delegates to property getters, setters, constructor arguments, specified attributes, and so forth.</span></span> <span data-ttu-id="e3d7b-118">Esse cache de metadados é armazenado na instância de opções.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-118">This metadata cache is stored in the options instance.</span></span> <span data-ttu-id="e3d7b-119">O mesmo processo e cache de aquecimento aplica-se à desserialização.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-119">The same warm-up process and cache applies to deserialization.</span></span>

<span data-ttu-id="e3d7b-120">O tamanho do cache de metadados em uma `JsonSerializerOptions` instância depende do número de tipos a serem serializados.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-120">The size of the metadata cache in a `JsonSerializerOptions` instance depends on the number of types to be serialized.</span></span> <span data-ttu-id="e3d7b-121">Se você passar por vários tipos — por exemplo, tipos gerados dinamicamente — para o serializador, o tamanho do cache continuará crescendo e poderá acabar causando um `OutOfMemoryException` .</span><span class="sxs-lookup"><span data-stu-id="e3d7b-121">If you pass numerous types—for example, dynamically generated types—to the serializer, the cache size will continue to grow and can end up causing an `OutOfMemoryException`.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="e3d7b-122">Copiar JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="e3d7b-122">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="e3d7b-123">Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerOptions)) que permite criar uma nova instância com as mesmas opções de uma instância existente, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e3d7b-123">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="e3d7b-124">Um `JsonSerializerOptions` Construtor que usa uma instância existente não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-124">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="e3d7b-125">Padrões da Web para JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="e3d7b-125">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="e3d7b-126">Aqui estão as opções que têm padrões diferentes para aplicativos Web:</span><span class="sxs-lookup"><span data-stu-id="e3d7b-126">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="e3d7b-127">Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerDefaults)? View = NET-5,0&preserve-View = true) que permite criar uma nova instância com as opções padrão que ASP.NET Core usa para aplicativos Web, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="e3d7b-127">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="e3d7b-128">Aqui estão as opções que têm padrões diferentes para aplicativos Web:</span><span class="sxs-lookup"><span data-stu-id="e3d7b-128">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="e3d7b-129">Um `JsonSerializerOptions` Construtor que especifica um conjunto de padrões não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="e3d7b-129">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="e3d7b-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="e3d7b-130">See also</span></span>

* [<span data-ttu-id="e3d7b-131">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="e3d7b-131">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="e3d7b-132">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="e3d7b-132">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="e3d7b-133">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="e3d7b-133">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="e3d7b-134">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="e3d7b-134">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="e3d7b-135">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="e3d7b-135">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="e3d7b-136">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="e3d7b-136">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="e3d7b-137">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="e3d7b-137">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="e3d7b-138">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="e3d7b-138">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="e3d7b-139">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="e3d7b-139">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="e3d7b-140">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="e3d7b-140">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="e3d7b-141">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="e3d7b-141">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="e3d7b-142">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="e3d7b-142">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="e3d7b-143">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="e3d7b-143">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="e3d7b-144">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="e3d7b-144">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="e3d7b-145">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e3d7b-145">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="e3d7b-146">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="e3d7b-146">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="e3d7b-147">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="e3d7b-147">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
