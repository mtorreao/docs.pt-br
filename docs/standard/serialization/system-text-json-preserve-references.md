---
title: Como preservar referências com System.Text.Json
description: Saiba como preservar referências e manipular referências circulares ao serializar e desserializar de JSON no .NET.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008728"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="266e5-103">Como preservar referências e manipular referências circulares com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="266e5-103">How to preserve references and handle circular references with System.Text.Json</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="266e5-104">Para preservar referências e manipular referências circulares, defina <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> como <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> .</span><span class="sxs-lookup"><span data-stu-id="266e5-104">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="266e5-105">Essa configuração causa o seguinte comportamento:</span><span class="sxs-lookup"><span data-stu-id="266e5-105">This setting causes the following behavior:</span></span>

* <span data-ttu-id="266e5-106">Em serializar:</span><span class="sxs-lookup"><span data-stu-id="266e5-106">On serialize:</span></span>

  <span data-ttu-id="266e5-107">Ao escrever tipos complexos, o serializador também grava Propriedades de metadados ( `$id` , `$values` e `$ref` ).</span><span class="sxs-lookup"><span data-stu-id="266e5-107">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="266e5-108">Ao desserializar:</span><span class="sxs-lookup"><span data-stu-id="266e5-108">On deserialize:</span></span>

  <span data-ttu-id="266e5-109">Os metadados são esperados (embora não obrigatórios) e o desserializador tenta compreendê-lo.</span><span class="sxs-lookup"><span data-stu-id="266e5-109">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="266e5-110">O código a seguir ilustra o uso da `Preserve` configuração.</span><span class="sxs-lookup"><span data-stu-id="266e5-110">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="266e5-111">Esse recurso não pode ser usado para preservar tipos de valor ou tipos imutáveis.</span><span class="sxs-lookup"><span data-stu-id="266e5-111">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="266e5-112">Na desserialização, a instância de um tipo imutável é criada depois que a carga inteira é lida.</span><span class="sxs-lookup"><span data-stu-id="266e5-112">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="266e5-113">Portanto, seria impossível desserializar a mesma instância se uma referência a ela aparecer dentro da carga JSON.</span><span class="sxs-lookup"><span data-stu-id="266e5-113">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="266e5-114">Para tipos de valor, tipos imutáveis e matrizes, nenhum metadado de referência é serializado.</span><span class="sxs-lookup"><span data-stu-id="266e5-114">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="266e5-115">Na desserialização, uma exceção será lançada se `$ref` ou `$id` for encontrada.</span><span class="sxs-lookup"><span data-stu-id="266e5-115">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="266e5-116">No entanto, os tipos de valor ignoram `$id` (e, `$values` no caso de coleções) para possibilitar a desserialização de cargas que foram serializadas usando Newtonsoft.Json .</span><span class="sxs-lookup"><span data-stu-id="266e5-116">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="266e5-117">Newtonsoft.Json Serializa metadados para esses tipos.</span><span class="sxs-lookup"><span data-stu-id="266e5-117">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="266e5-118">Para determinar se os objetos são iguais, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> , que usa igualdade de referência ( <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType> ) em vez de igualdade de valor ( <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> ao comparar duas instâncias de objeto.</span><span class="sxs-lookup"><span data-stu-id="266e5-118">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="266e5-119">Para obter mais informações sobre como as referências são serializadas e desserializadas, consulte <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="266e5-119">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="266e5-120">A <xref:System.Text.Json.Serialization.ReferenceResolver> classe define o comportamento de preservar referências na serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="266e5-120">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="266e5-121">Crie uma classe derivada para especificar o comportamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="266e5-121">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="266e5-122">Para obter um exemplo, consulte [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="266e5-122">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="266e5-123">System.Text.Json no .NET Core 3,1 dá suporte apenas a serialização por valor e gera uma exceção para referências circulares.</span><span class="sxs-lookup"><span data-stu-id="266e5-123">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="266e5-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="266e5-124">See also</span></span>

* [<span data-ttu-id="266e5-125">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="266e5-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="266e5-126">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="266e5-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="266e5-127">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="266e5-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="266e5-128">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="266e5-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="266e5-129">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="266e5-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="266e5-130">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="266e5-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="266e5-131">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="266e5-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="266e5-132">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="266e5-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="266e5-133">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="266e5-133">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="266e5-134">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="266e5-134">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="266e5-135">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="266e5-135">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="266e5-136">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="266e5-136">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="266e5-137">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="266e5-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="266e5-138">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="266e5-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="266e5-139">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="266e5-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="266e5-140">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="266e5-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="266e5-141">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="266e5-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
