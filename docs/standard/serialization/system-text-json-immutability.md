---
title: Como usar tipos imutáveis e acessadores não públicos com System.Text.Json
description: Saiba como usar tipos imutáveis e acessadores não públicos ao serializar e desserializar de JSON no .NET.
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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008819"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="0b646-103">Como usar tipos imutáveis e acessadores não públicos com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0b646-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="0b646-104">Neste artigo, você aprenderá a usar tipos imutáveis, como registros, com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="0b646-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="0b646-105">Tipos e registros imutáveis</span><span class="sxs-lookup"><span data-stu-id="0b646-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0b646-106">`System.Text.Json` pode usar um construtor com parâmetros, o que torna possível desserializar uma classe ou estrutura imutável.</span><span class="sxs-lookup"><span data-stu-id="0b646-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="0b646-107">Para uma classe, se o único Construtor for um parametrizado, esse construtor será usado.</span><span class="sxs-lookup"><span data-stu-id="0b646-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="0b646-108">Para uma struct ou uma classe com vários construtores, especifique o que deve ser usado aplicando o atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) .</span><span class="sxs-lookup"><span data-stu-id="0b646-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="0b646-109">Quando o atributo não é usado, um construtor público sem parâmetros é sempre usado, se estiver presente.</span><span class="sxs-lookup"><span data-stu-id="0b646-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="0b646-110">O atributo só pode ser usado com construtores públicos.</span><span class="sxs-lookup"><span data-stu-id="0b646-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="0b646-111">O exemplo a seguir usa o `[JsonConstructor]` atributo:</span><span class="sxs-lookup"><span data-stu-id="0b646-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="0b646-112">Também há suporte para registros no C# 9, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0b646-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="0b646-113">Para tipos que são imutáveis porque todos os seus setters de propriedade são não públicos, consulte a seção a seguir sobre [acessadores de propriedade não pública](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="0b646-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0b646-114">`JsonConstructorAttribute` e o suporte a registros do C# 9 não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="0b646-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="0b646-115">Acessadores de propriedade não pública</span><span class="sxs-lookup"><span data-stu-id="0b646-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0b646-116">Para habilitar o uso de um acessador de propriedade não público, use o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0b646-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0b646-117">Não há suporte para acessadores de propriedade não pública no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="0b646-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="0b646-118">Para obter mais informações, consulte [o Newtonsoft.Json artigo migrar de](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="0b646-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="0b646-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0b646-119">See also</span></span>

* [<span data-ttu-id="0b646-120">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="0b646-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0b646-121">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="0b646-121">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="0b646-122">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="0b646-122">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="0b646-123">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="0b646-123">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="0b646-124">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="0b646-124">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0b646-125">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="0b646-125">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0b646-126">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="0b646-126">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0b646-127">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="0b646-127">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0b646-128">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="0b646-128">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0b646-129">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="0b646-129">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="0b646-130">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0b646-130">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="0b646-131">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="0b646-131">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="0b646-132">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="0b646-132">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="0b646-133">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="0b646-133">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="0b646-134">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="0b646-134">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="0b646-135">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0b646-135">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="0b646-136">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="0b646-136">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
