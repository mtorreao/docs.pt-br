---
title: Como personalizar a codificação de caracteres com System.Text.Json
description: Saiba como personalizar a codificação de caracteres ao serializar e desserializar do JSON no .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cfb83af0c58e0c9dfb73ecb8e2177d255e403fae
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009619"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a><span data-ttu-id="f5508-103">Como personalizar a codificação de caracteres com System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="f5508-103">How to customize character encoding with System.Text.Json</span></span>

<span data-ttu-id="f5508-104">Por padrão, o serializador escapa todos os caracteres não ASCII.</span><span class="sxs-lookup"><span data-stu-id="f5508-104">By default, the serializer escapes all non-ASCII characters.</span></span> <span data-ttu-id="f5508-105">Ou seja, ele substitui por `\uxxxx` onde `xxxx` está o código Unicode do caractere.</span><span class="sxs-lookup"><span data-stu-id="f5508-105">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span> <span data-ttu-id="f5508-106">Por exemplo, se a `Summary` propriedade no JSON a seguir estiver definida como cirílico `жарко` , o `WeatherForecast` objeto será serializado, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="f5508-106">For example, if the `Summary` property in the following JSON is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a><span data-ttu-id="f5508-107">Serializar conjuntos de caracteres de idioma</span><span class="sxs-lookup"><span data-stu-id="f5508-107">Serialize language character sets</span></span>

<span data-ttu-id="f5508-108">Para serializar os conjuntos de caracteres de um ou mais idiomas sem saída, especifique os [intervalos Unicode](xref:System.Text.Unicode.UnicodeRanges) ao criar uma instância do <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5508-108">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

<span data-ttu-id="f5508-109">Este código não sai de escape de caracteres cirílico ou grego.</span><span class="sxs-lookup"><span data-stu-id="f5508-109">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="f5508-110">Se a `Summary` propriedade for definida como cirílico `жарко` , o `WeatherForecast` objeto será serializado, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="f5508-110">If the `Summary` property is set to Cyrillic `жарко`, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="f5508-111">Para serializar todos os conjuntos de idiomas sem saída, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f5508-111">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

## <a name="serialize-specific-characters"></a><span data-ttu-id="f5508-112">Serializar caracteres específicos</span><span class="sxs-lookup"><span data-stu-id="f5508-112">Serialize specific characters</span></span>

<span data-ttu-id="f5508-113">Uma alternativa é especificar os caracteres individuais que você deseja permitir sem ter escape.</span><span class="sxs-lookup"><span data-stu-id="f5508-113">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="f5508-114">O exemplo a seguir serializa apenas os dois primeiros caracteres de `жарко` :</span><span class="sxs-lookup"><span data-stu-id="f5508-114">The following example serializes only the first two characters of `жарко`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

<span data-ttu-id="f5508-115">Aqui está um exemplo de JSON produzido pelo código anterior:</span><span class="sxs-lookup"><span data-stu-id="f5508-115">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a><span data-ttu-id="f5508-116">Serializar todos os caracteres</span><span class="sxs-lookup"><span data-stu-id="f5508-116">Serialize all characters</span></span>

<span data-ttu-id="f5508-117">Para minimizar a saída, você pode usar <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5508-117">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> <span data-ttu-id="f5508-118">Em comparação com o codificador padrão, o `UnsafeRelaxedJsonEscaping` codificador é mais permissivo de permitir que os caracteres passem sem escape:</span><span class="sxs-lookup"><span data-stu-id="f5508-118">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="f5508-119">Ele não sai de caracteres sensíveis a HTML, como `<` ,, `>` `&` e `'` .</span><span class="sxs-lookup"><span data-stu-id="f5508-119">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="f5508-120">Ele não oferece nenhuma proteção adicional de defesa profunda contra ataques XSS ou de divulgação de informações, como aqueles que podem resultar do cliente e do servidor que estão descordando no conjunto de *caracteres*.</span><span class="sxs-lookup"><span data-stu-id="f5508-120">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="f5508-121">Use o codificador não seguro somente quando for conhecido que o cliente irá interpretar a carga resultante como JSON codificado em UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f5508-121">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="f5508-122">Por exemplo, você pode usá-lo se o servidor estiver enviando o cabeçalho de resposta `Content-Type: application/json; charset=utf-8` .</span><span class="sxs-lookup"><span data-stu-id="f5508-122">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="f5508-123">Nunca permita que a `UnsafeRelaxedJsonEscaping` saída bruta seja emitida em uma página HTML ou em um `<script>` elemento.</span><span class="sxs-lookup"><span data-stu-id="f5508-123">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5508-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5508-124">See also</span></span>

* [<span data-ttu-id="f5508-125">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="f5508-125">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="f5508-126">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="f5508-126">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="f5508-127">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="f5508-127">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="f5508-128">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="f5508-128">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="f5508-129">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="f5508-129">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="f5508-130">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="f5508-130">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="f5508-131">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="f5508-131">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="f5508-132">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="f5508-132">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="f5508-133">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="f5508-133">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="f5508-134">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="f5508-134">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="f5508-135">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="f5508-135">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="f5508-136">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="f5508-136">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="f5508-137">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="f5508-137">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="f5508-138">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="f5508-138">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="f5508-139">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f5508-139">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="f5508-140">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="f5508-140">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="f5508-141">[System.Text.Json. Referência da API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="f5508-141">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
