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
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a><span data-ttu-id="77900-103">Como lidar com referências circulares com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="77900-103">How to handle circular references with System.Text.Json</span></span>

<span data-ttu-id="77900-104">Neste artigo, você aprenderá a lidar com referências circulares com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="77900-104">In this article, you will learn how to handle circular references with the `System.Text.Json` namespace.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="77900-105">Preservar referências e manipular referências circulares</span><span class="sxs-lookup"><span data-stu-id="77900-105">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="77900-106">Para preservar referências e manipular referências circulares, defina <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> como <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A> .</span><span class="sxs-lookup"><span data-stu-id="77900-106">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="77900-107">Essa configuração causa o seguinte comportamento:</span><span class="sxs-lookup"><span data-stu-id="77900-107">This setting causes the following behavior:</span></span>

* <span data-ttu-id="77900-108">Em serializar:</span><span class="sxs-lookup"><span data-stu-id="77900-108">On serialize:</span></span>

  <span data-ttu-id="77900-109">Ao escrever tipos complexos, o serializador também grava Propriedades de metadados ( `$id` , `$values` e `$ref` ).</span><span class="sxs-lookup"><span data-stu-id="77900-109">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="77900-110">Ao desserializar:</span><span class="sxs-lookup"><span data-stu-id="77900-110">On deserialize:</span></span>

  <span data-ttu-id="77900-111">Os metadados são esperados (embora não obrigatórios) e o desserializador tenta compreendê-lo.</span><span class="sxs-lookup"><span data-stu-id="77900-111">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="77900-112">O código a seguir ilustra o uso da `Preserve` configuração.</span><span class="sxs-lookup"><span data-stu-id="77900-112">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="77900-113">Esse recurso não pode ser usado para preservar tipos de valor ou tipos imutáveis.</span><span class="sxs-lookup"><span data-stu-id="77900-113">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="77900-114">Na desserialização, a instância de um tipo imutável é criada depois que a carga inteira é lida.</span><span class="sxs-lookup"><span data-stu-id="77900-114">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="77900-115">Portanto, seria impossível desserializar a mesma instância se uma referência a ela aparecer dentro da carga JSON.</span><span class="sxs-lookup"><span data-stu-id="77900-115">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="77900-116">Para tipos de valor, tipos imutáveis e matrizes, nenhum metadado de referência é serializado.</span><span class="sxs-lookup"><span data-stu-id="77900-116">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="77900-117">Na desserialização, uma exceção será lançada se `$ref` ou `$id` for encontrada.</span><span class="sxs-lookup"><span data-stu-id="77900-117">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="77900-118">No entanto, os tipos de valor ignoram `$id` (e, `$values` no caso de coleções) para possibilitar a desserialização de cargas que foram serializadas usando Newtonsoft.Json .</span><span class="sxs-lookup"><span data-stu-id="77900-118">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="77900-119">Newtonsoft.Json Serializa metadados para esses tipos.</span><span class="sxs-lookup"><span data-stu-id="77900-119">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="77900-120">Para determinar se os objetos são iguais, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType> , que usa igualdade de referência ( <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType> ) em vez de igualdade de valor ( <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> ao comparar duas instâncias de objeto.</span><span class="sxs-lookup"><span data-stu-id="77900-120">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="77900-121">Para obter mais informações sobre como as referências são serializadas e desserializadas, consulte <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="77900-121">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="77900-122">A <xref:System.Text.Json.Serialization.ReferenceResolver> classe define o comportamento de preservar referências na serialização e desserialização.</span><span class="sxs-lookup"><span data-stu-id="77900-122">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="77900-123">Crie uma classe derivada para especificar o comportamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="77900-123">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="77900-124">Para obter um exemplo, consulte [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span><span class="sxs-lookup"><span data-stu-id="77900-124">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="77900-125">System.Text.Json no .NET Core 3,1 dá suporte apenas a serialização por valor e gera uma exceção para referências circulares.</span><span class="sxs-lookup"><span data-stu-id="77900-125">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="77900-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="77900-126">See also</span></span>

* [<span data-ttu-id="77900-127">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="77900-127">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="77900-128">Criar instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="77900-128">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="77900-129">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="77900-129">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="77900-130">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="77900-130">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="77900-131">Ignorar Propriedades</span><span class="sxs-lookup"><span data-stu-id="77900-131">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="77900-132">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="77900-132">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="77900-133">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="77900-133">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="77900-134">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="77900-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="77900-135">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="77900-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="77900-136">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="77900-136">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
