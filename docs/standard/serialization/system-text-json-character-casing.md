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
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599070"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a><span data-ttu-id="0fb93-103">Como habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="0fb93-103">How to enable case-insensitive property name matching with System.Text.Json</span></span>

<span data-ttu-id="0fb93-104">Neste artigo, você aprenderá a habilitar a correspondência de nome de propriedade que não diferencia maiúsculas de minúsculas com o `System.Text.Json` namespace.</span><span class="sxs-lookup"><span data-stu-id="0fb93-104">In this article, you will learn how to enable case-insensitive property name matching with the `System.Text.Json` namespace.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="0fb93-105">Correspondência de propriedade que não diferencia maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="0fb93-105">Case-insensitive property matching</span></span>

<span data-ttu-id="0fb93-106">Por padrão, a desserialização procura as correspondências de nome de propriedade que diferenciam maiúsculas de minúsculas entre JSON e as propriedades do objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="0fb93-106">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="0fb93-107">Para alterar esse comportamento, defina <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> como `true` :</span><span class="sxs-lookup"><span data-stu-id="0fb93-107">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

> [!NOTE]
> <span data-ttu-id="0fb93-108">O [padrão da Web](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0fb93-108">The [web default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions) is case-insensitive.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

<span data-ttu-id="0fb93-109">Aqui está um exemplo de JSON com nomes de Propriedade do camel case.</span><span class="sxs-lookup"><span data-stu-id="0fb93-109">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="0fb93-110">Ele pode ser desserializado no seguinte tipo que tem nomes de propriedade de caso de Pascal.</span><span class="sxs-lookup"><span data-stu-id="0fb93-110">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a><span data-ttu-id="0fb93-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="0fb93-111">See also</span></span>

* [<span data-ttu-id="0fb93-112">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="0fb93-112">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0fb93-113">Criar uma instância de JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="0fb93-113">Instantiate JsonSerializerOptions</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="0fb93-114">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="0fb93-114">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="0fb93-115">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="0fb93-115">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="0fb93-116">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="0fb93-116">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="0fb93-117">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="0fb93-117">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="0fb93-118">Preservar referências circulares</span><span class="sxs-lookup"><span data-stu-id="0fb93-118">Preserve circular references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="0fb93-119">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="0fb93-119">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="0fb93-120">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="0fb93-120">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* <span data-ttu-id="0fb93-121">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="0fb93-121">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
