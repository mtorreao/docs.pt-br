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
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a><span data-ttu-id="a01c3-103">Como instanciar instâncias JsonSerializerOptions com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="a01c3-103">How to instantiate JsonSerializerOptions instances with System.Text.Json</span></span>

<span data-ttu-id="a01c3-104">Neste artigo, você aprenderá como instanciar <xref:System.Text.Json.JsonSerializerOptions> instâncias copiando instâncias existentes ou com padrões da Web.</span><span class="sxs-lookup"><span data-stu-id="a01c3-104">In this article, you'll learn how to instantiate <xref:System.Text.Json.JsonSerializerOptions> instances by copying existing instances or with web defaults.</span></span>

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="a01c3-105">Copiar JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="a01c3-105">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="a01c3-106">Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerOptions)) que permite criar uma nova instância com as mesmas opções de uma instância existente, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a01c3-106">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="a01c3-107">Um `JsonSerializerOptions` Construtor que usa uma instância existente não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a01c3-107">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="a01c3-108">Padrões da Web para JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="a01c3-108">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="a01c3-109">Aqui estão as opções que têm padrões diferentes para aplicativos Web:</span><span class="sxs-lookup"><span data-stu-id="a01c3-109">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="a01c3-110">Há um [Construtor JsonSerializerOptions] (xref: System.Text.Json . JsonSerializerOptions .% 23ctor ( System.Text.Json . JsonSerializerDefaults)? View = NET-5,0&preserve-View = true) que permite criar uma nova instância com as opções padrão que ASP.NET Core usa para aplicativos Web, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a01c3-110">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="a01c3-111">Aqui estão as opções que têm padrões diferentes para aplicativos Web:</span><span class="sxs-lookup"><span data-stu-id="a01c3-111">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="a01c3-112">Um `JsonSerializerOptions` Construtor que especifica um conjunto de padrões não está disponível no .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a01c3-112">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="a01c3-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="a01c3-113">See also</span></span>

* [<span data-ttu-id="a01c3-114">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="a01c3-114">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="a01c3-115">Habilitar correspondência que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="a01c3-115">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="a01c3-116">Personalizar nomes e valores de propriedade</span><span class="sxs-lookup"><span data-stu-id="a01c3-116">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="a01c3-117">Ignorar Propriedades</span><span class="sxs-lookup"><span data-stu-id="a01c3-117">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="a01c3-118">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="a01c3-118">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="a01c3-119">Processar JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="a01c3-119">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="a01c3-120">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="a01c3-120">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="a01c3-121">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="a01c3-121">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="a01c3-122">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="a01c3-122">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="a01c3-123">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="a01c3-123">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
