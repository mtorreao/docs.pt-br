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
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439888"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a><span data-ttu-id="0a1b9-103">Como usar tipos imutáveis e acessadores não públicos com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0a1b9-103">How to use immutable types and non-public accessors with System.Text.Json</span></span>

<span data-ttu-id="0a1b9-104">Neste artigo, você aprenderá a usar tipos imutáveis, como registros, com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-104">In this article, you will learn how to use immutable types, such as Records, with the `System.Text.Json` namespace.</span></span>

## <a name="immutable-types-and-records"></a><span data-ttu-id="0a1b9-105">Tipos e registros imutáveis</span><span class="sxs-lookup"><span data-stu-id="0a1b9-105">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0a1b9-106">`System.Text.Json` pode usar um construtor com parâmetros, o que torna possível desserializar uma classe ou estrutura imutável.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-106">`System.Text.Json` can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="0a1b9-107">Para uma classe, se o único Construtor for um parametrizado, esse construtor será usado.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-107">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="0a1b9-108">Para uma struct ou uma classe com vários construtores, especifique o que deve ser usado aplicando o atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) .</span><span class="sxs-lookup"><span data-stu-id="0a1b9-108">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="0a1b9-109">Quando o atributo não é usado, um construtor público sem parâmetros é sempre usado, se estiver presente.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-109">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="0a1b9-110">O atributo só pode ser usado com construtores públicos.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-110">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="0a1b9-111">O exemplo a seguir usa o `[JsonConstructor]` atributo:</span><span class="sxs-lookup"><span data-stu-id="0a1b9-111">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="0a1b9-112">Também há suporte para registros no C# 9, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0a1b9-112">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="0a1b9-113">Para tipos que são imutáveis porque todos os seus setters de propriedade são não públicos, consulte a seção a seguir sobre [acessadores de propriedade não pública](#non-public-property-accessors).</span><span class="sxs-lookup"><span data-stu-id="0a1b9-113">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0a1b9-114">`JsonConstructorAttribute` e o suporte a registros do C# 9 não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-114">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="0a1b9-115">Acessadores de propriedade não pública</span><span class="sxs-lookup"><span data-stu-id="0a1b9-115">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="0a1b9-116">Para habilitar o uso de um acessador de propriedade não público, use o atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0a1b9-116">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="0a1b9-117">Não há suporte para acessadores de propriedade não pública no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="0a1b9-117">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="0a1b9-118">Para obter mais informações, consulte [o Newtonsoft.Json artigo migrar de](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span><span class="sxs-lookup"><span data-stu-id="0a1b9-118">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="0a1b9-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0a1b9-119">See also</span></span>

* [<span data-ttu-id="0a1b9-120">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="0a1b9-120">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0a1b9-121">Criar instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="0a1b9-121">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="0a1b9-122">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0a1b9-122">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="0a1b9-123">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="0a1b9-123">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0a1b9-124">Ignorar Propriedades</span><span class="sxs-lookup"><span data-stu-id="0a1b9-124">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0a1b9-125">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="0a1b9-125">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0a1b9-126">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="0a1b9-126">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0a1b9-127">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="0a1b9-127">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0a1b9-128">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="0a1b9-128">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="0a1b9-129">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0a1b9-129">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
