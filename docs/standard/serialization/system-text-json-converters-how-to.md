---
title: Como escrever conversores personalizados para serialização JSON-.NET
description: Saiba como criar conversores personalizados para as classes de serialização JSON que são fornecidas no System.Text.Json namespace.
ms.date: 12/14/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 390438e3dca7a5d40dd9957090f498b495996e05
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513192"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="73699-103">Como escrever conversores personalizados para serialização JSON (Marshalling) no .NET</span><span class="sxs-lookup"><span data-stu-id="73699-103">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="73699-104">Este artigo mostra como criar conversores personalizados para as classes de serialização JSON que são fornecidas no <xref:System.Text.Json> namespace.</span><span class="sxs-lookup"><span data-stu-id="73699-104">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="73699-105">Para obter uma introdução ao `System.Text.Json` , consulte [como serializar e desserializar JSON no .net](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="73699-105">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="73699-106">Um *conversor* é uma classe que converte um objeto ou um valor de e para JSON.</span><span class="sxs-lookup"><span data-stu-id="73699-106">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="73699-107">O `System.Text.Json` namespace tem conversores internos para a maioria dos tipos primitivos que mapeiam para primitivas de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="73699-107">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="73699-108">Você pode escrever conversores personalizados:</span><span class="sxs-lookup"><span data-stu-id="73699-108">You can write custom converters:</span></span>

* <span data-ttu-id="73699-109">Para substituir o comportamento padrão de um conversor interno.</span><span class="sxs-lookup"><span data-stu-id="73699-109">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="73699-110">Por exemplo, talvez você queira que `DateTime` os valores sejam representados pelo formato mm/dd/aaaa.</span><span class="sxs-lookup"><span data-stu-id="73699-110">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format.</span></span> <span data-ttu-id="73699-111">Por padrão, o ISO 8601-1:2019 tem suporte, incluindo o perfil RFC 3339.</span><span class="sxs-lookup"><span data-stu-id="73699-111">By default, ISO 8601-1:2019 is supported, including the RFC 3339 profile.</span></span> <span data-ttu-id="73699-112">Para obter mais informações, consulte [suporte a DateTime e System.Text.Json DateTimeOffset no ](../datetime/system-text-json-support.md).</span><span class="sxs-lookup"><span data-stu-id="73699-112">For more information, see [DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md).</span></span>
* <span data-ttu-id="73699-113">Para dar suporte a um tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="73699-113">To support a custom value type.</span></span> <span data-ttu-id="73699-114">Por exemplo, um `PhoneNumber` struct.</span><span class="sxs-lookup"><span data-stu-id="73699-114">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="73699-115">Você também pode escrever conversores personalizados para personalizar ou estender `System.Text.Json` com funcionalidade não incluída na versão atual.</span><span class="sxs-lookup"><span data-stu-id="73699-115">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="73699-116">Os cenários a seguir serão abordados posteriormente neste artigo:</span><span class="sxs-lookup"><span data-stu-id="73699-116">The following scenarios are covered later in this article:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="73699-117">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="73699-117">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="73699-118">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="73699-118">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="73699-119">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="73699-119">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="73699-120">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="73699-120">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="73699-121">[Dicionário de suporte com chave não cadeia de caracteres](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="73699-121">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="73699-122">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="73699-122">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="73699-123">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="73699-123">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

<span data-ttu-id="73699-124">No código que você escreve para um conversor personalizado, esteja ciente da penalidade de desempenho substancial para usar novas <xref:System.Text.Json.JsonSerializerOptions> instâncias.</span><span class="sxs-lookup"><span data-stu-id="73699-124">In the code you write for a custom converter, be aware of the substantial performance penalty for using new <xref:System.Text.Json.JsonSerializerOptions> instances.</span></span> <span data-ttu-id="73699-125">Para obter mais informações, consulte [reutilizar instâncias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="73699-125">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="73699-126">Padrões de conversor personalizado</span><span class="sxs-lookup"><span data-stu-id="73699-126">Custom converter patterns</span></span>

<span data-ttu-id="73699-127">Há dois padrões para a criação de um conversor personalizado: o padrão básico e o padrão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="73699-127">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="73699-128">O padrão de fábrica é para conversores que manipulam tipos `Enum` ou genéricos abertos.</span><span class="sxs-lookup"><span data-stu-id="73699-128">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="73699-129">O padrão básico é para tipos genéricos não genéricos e fechados.</span><span class="sxs-lookup"><span data-stu-id="73699-129">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="73699-130">Por exemplo, os conversores para os seguintes tipos exigem o padrão de fábrica:</span><span class="sxs-lookup"><span data-stu-id="73699-130">For example, converters for the following types require the factory pattern:</span></span>

* <xref:System.Collections.Generic.Dictionary%602>
* <xref:System.Enum>
* <xref:System.Collections.Generic.List%601>

<span data-ttu-id="73699-131">Alguns exemplos de tipos que podem ser tratados pelo padrão básico incluem:</span><span class="sxs-lookup"><span data-stu-id="73699-131">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* <xref:System.DateTime>
* <xref:System.Int32>

<span data-ttu-id="73699-132">O padrão básico cria uma classe que pode manipular um tipo.</span><span class="sxs-lookup"><span data-stu-id="73699-132">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="73699-133">O padrão de fábrica cria uma classe que determina, em tempo de execução, qual tipo específico é necessário e cria dinamicamente o conversor apropriado.</span><span class="sxs-lookup"><span data-stu-id="73699-133">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="73699-134">Conversor básico de exemplo</span><span class="sxs-lookup"><span data-stu-id="73699-134">Sample basic converter</span></span>

<span data-ttu-id="73699-135">O exemplo a seguir é um conversor que substitui a serialização padrão para um tipo de dados existente.</span><span class="sxs-lookup"><span data-stu-id="73699-135">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="73699-136">O conversor usa o formato mm/dd/aaaa para `DateTimeOffset` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="73699-136">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs":::

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="73699-137">Conversor de padrão de fábrica de exemplo</span><span class="sxs-lookup"><span data-stu-id="73699-137">Sample factory pattern converter</span></span>

<span data-ttu-id="73699-138">O código a seguir mostra um conversor personalizado que funciona com o `Dictionary<Enum,TValue>` .</span><span class="sxs-lookup"><span data-stu-id="73699-138">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="73699-139">O código segue o padrão de fábrica porque o primeiro parâmetro de tipo genérico é `Enum` e o segundo é aberto.</span><span class="sxs-lookup"><span data-stu-id="73699-139">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="73699-140">O `CanConvert` método retorna `true` apenas para um `Dictionary` com dois parâmetros genéricos, o primeiro deles é um `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="73699-140">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="73699-141">O conversor interno Obtém um conversor existente para lidar com qualquer tipo fornecido no tempo de execução para `TValue` .</span><span class="sxs-lookup"><span data-stu-id="73699-141">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="73699-142">O código anterior é o mesmo que o mostrado no dicionário de [suporte com uma chave que não seja de cadeia de caracteres](#support-dictionary-with-non-string-key) , mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="73699-142">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="73699-143">Etapas para seguir o padrão básico</span><span class="sxs-lookup"><span data-stu-id="73699-143">Steps to follow the basic pattern</span></span>

<span data-ttu-id="73699-144">As etapas a seguir explicam como criar um conversor seguindo o padrão básico:</span><span class="sxs-lookup"><span data-stu-id="73699-144">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="73699-145">Crie uma classe que derive de <xref:System.Text.Json.Serialization.JsonConverter%601> onde `T` é o tipo a ser serializado e desserializado.</span><span class="sxs-lookup"><span data-stu-id="73699-145">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="73699-146">Substitua o `Read` método para desserializar o JSON de entrada e convertê-lo no tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="73699-146">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="73699-147">Use o <xref:System.Text.Json.Utf8JsonReader> que é passado para o método para ler o JSON.</span><span class="sxs-lookup"><span data-stu-id="73699-147">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span> <span data-ttu-id="73699-148">Você não precisa se preocupar em lidar com dados parciais, pois o serializador passa todos os dados para o escopo JSON atual.</span><span class="sxs-lookup"><span data-stu-id="73699-148">You don't have to worry about handling partial data, as the serializer passes all the data for the current JSON scope.</span></span> <span data-ttu-id="73699-149">Portanto, não é necessário chamar <xref:System.Text.Json.Utf8JsonReader.Skip%2A> ou <xref:System.Text.Json.Utf8JsonReader.TrySkip%2A> ou para validar que <xref:System.Text.Json.Utf8JsonReader.Read%2A> retorna `true` .</span><span class="sxs-lookup"><span data-stu-id="73699-149">So it isn't necessary to call <xref:System.Text.Json.Utf8JsonReader.Skip%2A> or <xref:System.Text.Json.Utf8JsonReader.TrySkip%2A> or to validate that <xref:System.Text.Json.Utf8JsonReader.Read%2A> returns `true`.</span></span>
* <span data-ttu-id="73699-150">Substitua o `Write` método para serializar o objeto de entrada do tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="73699-150">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="73699-151">Use o <xref:System.Text.Json.Utf8JsonWriter> que é passado para o método para gravar o JSON.</span><span class="sxs-lookup"><span data-stu-id="73699-151">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="73699-152">Substitua o `CanConvert` método somente se necessário.</span><span class="sxs-lookup"><span data-stu-id="73699-152">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="73699-153">A implementação padrão retorna `true` quando o tipo a ser convertido é do tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="73699-153">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="73699-154">Portanto, os conversores que suportam apenas `T` o tipo não precisam substituir esse método.</span><span class="sxs-lookup"><span data-stu-id="73699-154">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="73699-155">Para obter um exemplo de um conversor que precisa substituir esse método, consulte a seção [desserialização polimórfica](#support-polymorphic-deserialization) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="73699-155">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="73699-156">Você pode consultar o [código-fonte dos conversores internos](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementações de referência para escrever conversores personalizados.</span><span class="sxs-lookup"><span data-stu-id="73699-156">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="73699-157">Etapas para seguir o padrão de fábrica</span><span class="sxs-lookup"><span data-stu-id="73699-157">Steps to follow the factory pattern</span></span>

<span data-ttu-id="73699-158">As etapas a seguir explicam como criar um conversor seguindo o padrão de fábrica:</span><span class="sxs-lookup"><span data-stu-id="73699-158">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="73699-159">Crie uma classe que deriva de <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="73699-159">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="73699-160">Substitua o `CanConvert` método para retornar true quando o tipo a ser convertido for aquele que o conversor pode manipular.</span><span class="sxs-lookup"><span data-stu-id="73699-160">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="73699-161">Por exemplo, se o conversor for para `List<T>` ele, ele só poderá manipular `List<int>` , `List<string>` e `List<DateTime>` .</span><span class="sxs-lookup"><span data-stu-id="73699-161">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="73699-162">Substitua o `CreateConverter` método para retornar uma instância de uma classe de conversor que manipulará o tipo a ser convertido que é fornecido no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="73699-162">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="73699-163">Crie a classe de conversor `CreateConverter` instanciada pelo método.</span><span class="sxs-lookup"><span data-stu-id="73699-163">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="73699-164">O padrão de fábrica é necessário para os genéricos abertos porque o código para converter um objeto de e para uma cadeia de caracteres não é o mesmo para todos os tipos.</span><span class="sxs-lookup"><span data-stu-id="73699-164">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="73699-165">Um conversor para um tipo genérico aberto ( `List<T>` , por exemplo) precisa criar um conversor para um tipo genérico fechado ( `List<DateTime>` , por exemplo) em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="73699-165">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="73699-166">O código deve ser gravado para lidar com cada tipo fechado genérico que o conversor pode manipular.</span><span class="sxs-lookup"><span data-stu-id="73699-166">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="73699-167">O `Enum` tipo é semelhante a um tipo genérico aberto: um conversor de `Enum` deve criar um conversor para um específico `Enum` ( `WeekdaysEnum` , por exemplo) em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="73699-167">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="73699-168">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="73699-168">Error handling</span></span>

<span data-ttu-id="73699-169">O serializador Fornece tratamento especial para tipos de exceção <xref:System.Text.Json.JsonException> e <xref:System.NotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="73699-169">The serializer provides special handling for exception types <xref:System.Text.Json.JsonException> and <xref:System.NotSupportedException>.</span></span>

### <a name="jsonexception"></a><span data-ttu-id="73699-170">Jsonexception</span><span class="sxs-lookup"><span data-stu-id="73699-170">JsonException</span></span>

<span data-ttu-id="73699-171">Se você lançar um `JsonException` sem uma mensagem, o serializador criará uma mensagem que inclui o caminho para a parte do JSON que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="73699-171">If you throw a `JsonException` without a message, the serializer creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="73699-172">Por exemplo, a instrução `throw new JsonException()` produz uma mensagem de erro semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73699-172">For example, the statement `throw new JsonException()` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="73699-173">Se você fornecer uma mensagem (por exemplo, `throw new JsonException("Error occurred")` o serializador ainda definirá as <xref:System.Text.Json.JsonException.Path> <xref:System.Text.Json.JsonException.LineNumber> Propriedades, e <xref:System.Text.Json.JsonException.BytePositionInLine> .</span><span class="sxs-lookup"><span data-stu-id="73699-173">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the serializer still sets the <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber>, and <xref:System.Text.Json.JsonException.BytePositionInLine> properties.</span></span>

### <a name="notsupportedexception"></a><span data-ttu-id="73699-174">NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="73699-174">NotSupportedException</span></span>

<span data-ttu-id="73699-175">Se você lançar um `NotSupportedException` , sempre obterá as informações de caminho na mensagem.</span><span class="sxs-lookup"><span data-stu-id="73699-175">If you throw a `NotSupportedException`, you always get the path information in the message.</span></span> <span data-ttu-id="73699-176">Se você fornecer uma mensagem, as informações de caminho serão acrescentadas a ela.</span><span class="sxs-lookup"><span data-stu-id="73699-176">If you provide a message, the path information is appended to it.</span></span> <span data-ttu-id="73699-177">Por exemplo, a instrução `throw new NotSupportedException("Error occurred.")` produz uma mensagem de erro semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73699-177">For example, the statement `throw new NotSupportedException("Error occurred.")` produces an error message like the following example:</span></span>

```output
Error occurred. The unsupported member type is located on type
'System.Collections.Generic.Dictionary`2[Samples.SummaryWords,System.Int32]'.
Path: $.TemperatureRanges | LineNumber: 4 | BytePositionInLine: 24
```

### <a name="when-to-throw-which-exception-type"></a><span data-ttu-id="73699-178">Quando lançar qual tipo de exceção</span><span class="sxs-lookup"><span data-stu-id="73699-178">When to throw which exception type</span></span>

<span data-ttu-id="73699-179">Quando a carga JSON contém tokens que não são válidos para o tipo que está sendo desserializado, lança um `JsonException` .</span><span class="sxs-lookup"><span data-stu-id="73699-179">When the JSON payload contains tokens that are not valid for the type being deserialized, throw a `JsonException`.</span></span>

<span data-ttu-id="73699-180">Quando você quiser não permitir certos tipos, acione um `NotSupportedException` .</span><span class="sxs-lookup"><span data-stu-id="73699-180">When you want to disallow certain types, throw a `NotSupportedException`.</span></span> <span data-ttu-id="73699-181">Essa exceção é o que o serializador gera automaticamente para tipos que não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="73699-181">This exception is what the serializer automatically throws for types that are not supported.</span></span> <span data-ttu-id="73699-182">Por exemplo, `System.Type` o não tem suporte por motivos de segurança, portanto, uma tentativa de desserializar isso resulta em um `NotSupportedException` .</span><span class="sxs-lookup"><span data-stu-id="73699-182">For example, `System.Type` is not supported for security reasons, so an attempt to deserialize it results in a `NotSupportedException`.</span></span>

<span data-ttu-id="73699-183">Você pode gerar outras exceções conforme necessário, mas elas não incluem automaticamente informações de caminho JSON.</span><span class="sxs-lookup"><span data-stu-id="73699-183">You can throw other exceptions as needed, but they don't automatically include JSON path information.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="73699-184">Registrar um conversor personalizado</span><span class="sxs-lookup"><span data-stu-id="73699-184">Register a custom converter</span></span>

<span data-ttu-id="73699-185">*Registre* um conversor personalizado para fazer com `Serialize` que os métodos e o `Deserialize` usem.</span><span class="sxs-lookup"><span data-stu-id="73699-185">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="73699-186">Escolha uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="73699-186">Choose one of the following approaches:</span></span>

* <span data-ttu-id="73699-187">Adicione uma instância da classe converter à <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> coleção.</span><span class="sxs-lookup"><span data-stu-id="73699-187">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="73699-188">Aplique o atributo [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) às propriedades que exigem o conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="73699-188">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="73699-189">Aplique o atributo [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a uma classe ou a uma struct que represente um tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="73699-189">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="73699-190">Amostra de registro – coleção de conversores</span><span class="sxs-lookup"><span data-stu-id="73699-190">Registration sample - Converters collection</span></span>

<span data-ttu-id="73699-191">Veja um exemplo que torna o <xref:System.ComponentModel.DateTimeOffsetConverter> padrão para propriedades do tipo <xref:System.DateTimeOffset> :</span><span class="sxs-lookup"><span data-stu-id="73699-191">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Serialize":::

<span data-ttu-id="73699-192">Suponha que você Serialize uma instância do seguinte tipo:</span><span class="sxs-lookup"><span data-stu-id="73699-192">Suppose you serialize an instance of the following type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="73699-193">Aqui está um exemplo de saída JSON que mostra que o conversor personalizado foi usado:</span><span class="sxs-lookup"><span data-stu-id="73699-193">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="73699-194">O código a seguir usa a mesma abordagem para desserializar usando o `DateTimeOffset` conversor personalizado:</span><span class="sxs-lookup"><span data-stu-id="73699-194">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="73699-195">Exemplo de registro-[Jsonconverter] em uma propriedade</span><span class="sxs-lookup"><span data-stu-id="73699-195">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="73699-196">O código a seguir seleciona um conversor personalizado para a `Date` Propriedade:</span><span class="sxs-lookup"><span data-stu-id="73699-196">The following code selects a custom converter for the `Date` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithConverterAttribute":::

<span data-ttu-id="73699-197">O código a ser serializado `WeatherForecastWithConverterAttribute` não exige o uso de `JsonSerializeOptions.Converters` :</span><span class="sxs-lookup"><span data-stu-id="73699-197">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Serialize":::

<span data-ttu-id="73699-198">O código para desserializar também não exige o uso de `Converters` :</span><span class="sxs-lookup"><span data-stu-id="73699-198">The code to deserialize also doesn't require the use of `Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="73699-199">Exemplo de registro-[Jsonconverter] em um tipo</span><span class="sxs-lookup"><span data-stu-id="73699-199">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="73699-200">Aqui está o código que cria uma struct e aplica o `[JsonConverter]` atributo a ela:</span><span class="sxs-lookup"><span data-stu-id="73699-200">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Temperature.cs":::

<span data-ttu-id="73699-201">Este é o conversor personalizado para o struct anterior:</span><span class="sxs-lookup"><span data-stu-id="73699-201">Here's the custom converter for the preceding struct:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/TemperatureConverter.cs":::

<span data-ttu-id="73699-202">O `[JsonConvert]` atributo na estrutura registra o conversor personalizado como o padrão para propriedades do tipo `Temperature` .</span><span class="sxs-lookup"><span data-stu-id="73699-202">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="73699-203">O conversor é usado automaticamente na `TemperatureCelsius` Propriedade do seguinte tipo ao serializar ou desserializar:</span><span class="sxs-lookup"><span data-stu-id="73699-203">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithTemperatureStruct":::

## <a name="converter-registration-precedence"></a><span data-ttu-id="73699-204">Precedência de registro do conversor</span><span class="sxs-lookup"><span data-stu-id="73699-204">Converter registration precedence</span></span>

<span data-ttu-id="73699-205">Durante a serialização ou desserialização, um conversor é escolhido para cada elemento JSON na seguinte ordem, listada da prioridade mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="73699-205">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="73699-206">`[JsonConverter]` aplicado a uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="73699-206">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="73699-207">Um conversor adicionado à `Converters` coleção.</span><span class="sxs-lookup"><span data-stu-id="73699-207">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="73699-208">`[JsonConverter]` aplicado a um tipo de valor personalizado ou POCO.</span><span class="sxs-lookup"><span data-stu-id="73699-208">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="73699-209">Se vários conversores personalizados para um tipo forem registrados na `Converters` coleção, o primeiro conversor que retorna true para `CanConvert` será usado.</span><span class="sxs-lookup"><span data-stu-id="73699-209">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="73699-210">Um conversor interno será escolhido somente se nenhum conversor personalizado aplicável for registrado.</span><span class="sxs-lookup"><span data-stu-id="73699-210">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="73699-211">Exemplos de conversor para cenários comuns</span><span class="sxs-lookup"><span data-stu-id="73699-211">Converter samples for common scenarios</span></span>

<span data-ttu-id="73699-212">As seções a seguir fornecem exemplos de conversor que abordam alguns cenários comuns que a funcionalidade interna não trata.</span><span class="sxs-lookup"><span data-stu-id="73699-212">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="73699-213">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="73699-213">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="73699-214">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="73699-214">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="73699-215">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="73699-215">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="73699-216">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="73699-216">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="73699-217">[Dicionário de suporte com chave não cadeia de caracteres](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="73699-217">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="73699-218">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="73699-218">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="73699-219">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="73699-219">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="73699-220">Desserializar tipos inferidos para propriedades de objeto</span><span class="sxs-lookup"><span data-stu-id="73699-220">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="73699-221">Ao desserializar para uma propriedade do tipo `object` , um `JsonElement` objeto é criado.</span><span class="sxs-lookup"><span data-stu-id="73699-221">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="73699-222">O motivo é que o desserializador não sabe qual tipo de CLR deve ser criado e não tenta adivinhar.</span><span class="sxs-lookup"><span data-stu-id="73699-222">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="73699-223">Por exemplo, se uma propriedade JSON tiver "true", o desserializador não inferirá que o valor é a `Boolean` e, se um elemento tiver "01/01/2019", o desserializador não inferirá que é um `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="73699-223">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="73699-224">A inferência de tipos pode ser imprecisa.</span><span class="sxs-lookup"><span data-stu-id="73699-224">Type inference can be inaccurate.</span></span> <span data-ttu-id="73699-225">Se o desserializador analisar um número JSON que não tenha nenhum ponto decimal como um `long` , isso poderá resultar em problemas fora do intervalo se o valor tiver sido originalmente serializado como um `ulong` ou `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="73699-225">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="73699-226">A análise de um número que tenha um ponto decimal como `double` pode perder a precisão se o número tiver sido originalmente serializado como um `decimal` .</span><span class="sxs-lookup"><span data-stu-id="73699-226">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="73699-227">Para cenários que exigem a inferência de tipos, o código a seguir mostra um conversor personalizado para `object` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="73699-227">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="73699-228">O código converte:</span><span class="sxs-lookup"><span data-stu-id="73699-228">The code converts:</span></span>

* <span data-ttu-id="73699-229">`true` e `false` para `Boolean`</span><span class="sxs-lookup"><span data-stu-id="73699-229">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="73699-230">Números sem um decimal para `long`</span><span class="sxs-lookup"><span data-stu-id="73699-230">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="73699-231">Números com um decimal para `double`</span><span class="sxs-lookup"><span data-stu-id="73699-231">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="73699-232">Datas para `DateTime`</span><span class="sxs-lookup"><span data-stu-id="73699-232">Dates to `DateTime`</span></span>
* <span data-ttu-id="73699-233">Cadeias de caracteres para `string`</span><span class="sxs-lookup"><span data-stu-id="73699-233">Strings to `string`</span></span>
* <span data-ttu-id="73699-234">Tudo o mais a `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="73699-234">Everything else to `JsonElement`</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs":::

<span data-ttu-id="73699-235">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="73699-235">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs" id="Register":::

<span data-ttu-id="73699-236">Aqui está um tipo de exemplo com `object` Propriedades:</span><span class="sxs-lookup"><span data-stu-id="73699-236">Here's an example type with `object` properties:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithObjectProperties":::

<span data-ttu-id="73699-237">O exemplo a seguir de JSON para desserializar contém valores que serão desserializados como `DateTime` , `long` e `string` :</span><span class="sxs-lookup"><span data-stu-id="73699-237">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="73699-238">Sem o conversor personalizado, a desserialização coloca um `JsonElement` em cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="73699-238">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="73699-239">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` namespace tem mais exemplos de conversores personalizados que manipulam a desserialização para `object` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="73699-239">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="73699-240">Dicionário de suporte com chave não cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="73699-240">Support Dictionary with non-string key</span></span>

<span data-ttu-id="73699-241">O suporte interno para coleções de dicionário é para o `Dictionary<string, TValue>` .</span><span class="sxs-lookup"><span data-stu-id="73699-241">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="73699-242">Ou seja, a chave deve ser uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="73699-242">That is, the key must be a string.</span></span> <span data-ttu-id="73699-243">Para dar suporte a um dicionário com um inteiro ou algum outro tipo como a chave, um conversor personalizado é necessário.</span><span class="sxs-lookup"><span data-stu-id="73699-243">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="73699-244">O código a seguir mostra um conversor personalizado que funciona com `Dictionary<Enum,TValue>` :</span><span class="sxs-lookup"><span data-stu-id="73699-244">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="73699-245">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="73699-245">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs" id="Register":::

<span data-ttu-id="73699-246">O conversor pode serializar e desserializar a `TemperatureRanges` propriedade da seguinte classe que usa o seguinte `Enum` :</span><span class="sxs-lookup"><span data-stu-id="73699-246">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnumDictionary":::

<span data-ttu-id="73699-247">A saída JSON da serialização é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73699-247">The JSON output from serialization looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

<span data-ttu-id="73699-248">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` namespace tem mais exemplos de conversores personalizados que manipulam dicionários que não são de chave de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="73699-248">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>
::: zone-end

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="73699-249">Suporte à desserialização polimórfico</span><span class="sxs-lookup"><span data-stu-id="73699-249">Support polymorphic deserialization</span></span>

<span data-ttu-id="73699-250">Os recursos internos fornecem um intervalo limitado de [serialização polimórfico](system-text-json-polymorphism.md) , mas não há suporte para desserialização.</span><span class="sxs-lookup"><span data-stu-id="73699-250">Built-in features provide a limited range of [polymorphic serialization](system-text-json-polymorphism.md) but no support for deserialization at all.</span></span> <span data-ttu-id="73699-251">A desserialização requer um conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="73699-251">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="73699-252">Suponha, por exemplo, que você tenha uma `Person` classe base abstrata, `Employee` com `Customer` classes derivadas e.</span><span class="sxs-lookup"><span data-stu-id="73699-252">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="73699-253">A desserialização polimórfica significa que, em tempo de design, você pode especificar `Person` como o destino de desserialização e `Customer` `Employee` os objetos no JSON são corretamente desserializados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="73699-253">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="73699-254">Durante a desserialização, você precisa encontrar pistas que identificam o tipo necessário no JSON.</span><span class="sxs-lookup"><span data-stu-id="73699-254">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="73699-255">Os tipos de pistas disponíveis variam de acordo com cada cenário.</span><span class="sxs-lookup"><span data-stu-id="73699-255">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="73699-256">Por exemplo, uma propriedade discriminadora pode estar disponível ou talvez você precise contar com a presença ou a ausência de uma determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="73699-256">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="73699-257">A versão atual do `System.Text.Json` não fornece atributos para especificar como lidar com cenários de desserialização polimórfico, para que conversores personalizados sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="73699-257">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="73699-258">O código a seguir mostra uma classe base, duas classes derivadas e um conversor personalizado para elas.</span><span class="sxs-lookup"><span data-stu-id="73699-258">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="73699-259">O conversor usa uma propriedade discriminadora para fazer desserialização polimórfica.</span><span class="sxs-lookup"><span data-stu-id="73699-259">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="73699-260">O discriminador de tipo não está nas definições de classe, mas é criado durante a serialização e é lido durante a desserialização.</span><span class="sxs-lookup"><span data-stu-id="73699-260">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Person.cs" id="Person":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs":::

<span data-ttu-id="73699-261">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="73699-261">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs" id="Register":::

<span data-ttu-id="73699-262">O conversor pode desserializar o JSON criado usando o mesmo conversor para serializar, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="73699-262">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

<span data-ttu-id="73699-263">O código do conversor no exemplo anterior lê e grava cada propriedade manualmente.</span><span class="sxs-lookup"><span data-stu-id="73699-263">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="73699-264">Uma alternativa é chamar `Deserialize` ou `Serialize` fazer parte do trabalho.</span><span class="sxs-lookup"><span data-stu-id="73699-264">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="73699-265">Para obter um exemplo, consulte [esta postagem de StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="73699-265">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="73699-266">Dar suporte à viagem de ida e volta para a pilha\<T></span><span class="sxs-lookup"><span data-stu-id="73699-266">Support round trip for Stack\<T></span></span>

<span data-ttu-id="73699-267">Se você desserializar uma cadeia de caracteres JSON em um <xref:System.Collections.Generic.Stack%601> objeto e, em seguida, serializar esse objeto, o conteúdo da pilha estará na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="73699-267">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="73699-268">Esse comportamento se aplica aos tipos e à interface a seguir e aos tipos definidos pelo usuário que derivam deles:</span><span class="sxs-lookup"><span data-stu-id="73699-268">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="73699-269">Para dar suporte à serialização e desserialização que retém o pedido original na pilha, é necessário um conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="73699-269">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="73699-270">O código a seguir mostra um conversor personalizado que permite a passagem de ida e volta de `Stack<T>` objetos:</span><span class="sxs-lookup"><span data-stu-id="73699-270">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs":::

<span data-ttu-id="73699-271">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="73699-271">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs" id="Register":::

## <a name="handle-null-values"></a><span data-ttu-id="73699-272">Manipular valores nulos</span><span class="sxs-lookup"><span data-stu-id="73699-272">Handle null values</span></span>

<span data-ttu-id="73699-273">Por padrão, o serializador trata valores nulos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="73699-273">By default, the serializer handles null values as follows:</span></span>

* <span data-ttu-id="73699-274">Para tipos de referência e <xref:System.Nullable%601> tipos:</span><span class="sxs-lookup"><span data-stu-id="73699-274">For reference types and <xref:System.Nullable%601> types:</span></span>

  * <span data-ttu-id="73699-275">Ele não passa `null` para conversores personalizados na serialização.</span><span class="sxs-lookup"><span data-stu-id="73699-275">It does not pass `null` to custom converters on serialization.</span></span>
  * <span data-ttu-id="73699-276">Ele não passa `JsonTokenType.Null` para conversores personalizados na desserialização.</span><span class="sxs-lookup"><span data-stu-id="73699-276">It does not pass `JsonTokenType.Null` to custom converters on deserialization.</span></span>
  * <span data-ttu-id="73699-277">Ele retorna uma `null` instância na desserialização.</span><span class="sxs-lookup"><span data-stu-id="73699-277">It returns a `null` instance on deserialization.</span></span>
  * <span data-ttu-id="73699-278">Ele grava `null` diretamente com o gravador na serialização.</span><span class="sxs-lookup"><span data-stu-id="73699-278">It writes `null` directly with the writer on serialization.</span></span>

* <span data-ttu-id="73699-279">Para tipos de valores não anuláveis:</span><span class="sxs-lookup"><span data-stu-id="73699-279">For non-nullable value types:</span></span>

  * <span data-ttu-id="73699-280">Ele passa `JsonTokenType.Null` para conversores personalizados na desserialização.</span><span class="sxs-lookup"><span data-stu-id="73699-280">It passes `JsonTokenType.Null` to custom converters on deserialization.</span></span> <span data-ttu-id="73699-281">(Se nenhum conversor personalizado estiver disponível, uma `JsonException` exceção será lançada pelo conversor interno para o tipo.)</span><span class="sxs-lookup"><span data-stu-id="73699-281">(If no custom converter is available, a `JsonException` exception is thrown by the internal converter for the type.)</span></span>

<span data-ttu-id="73699-282">Esse comportamento de tratamento nulo é principalmente para otimizar o desempenho, ignorando uma chamada extra para o conversor.</span><span class="sxs-lookup"><span data-stu-id="73699-282">This null-handling behavior is primarily to optimize performance by skipping an extra call to the converter.</span></span> <span data-ttu-id="73699-283">Além disso, evita a força de conversores para tipos anuláveis a serem verificados `null` no início de cada `Read` e `Write` substituição de método.</span><span class="sxs-lookup"><span data-stu-id="73699-283">In addition, it avoids forcing converters for nullable types to check for `null` at the start of every `Read` and `Write` method override.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="73699-284">Para habilitar um conversor personalizado para tratar `null` de uma referência ou tipo de valor, substitua <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> para retornar `true` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="73699-284">To enable a custom converter to handle `null` for a reference or value type, override <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> to return `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="18":::
::: zone-end

## <a name="other-custom-converter-samples"></a><span data-ttu-id="73699-285">Outras amostras de conversor personalizadas</span><span class="sxs-lookup"><span data-stu-id="73699-285">Other custom converter samples</span></span>

<span data-ttu-id="73699-286">O artigo [migrar de Newtonsoft.Json para System.Text.Json ](system-text-json-migrate-from-newtonsoft-how-to.md) contém exemplos adicionais de conversores personalizados.</span><span class="sxs-lookup"><span data-stu-id="73699-286">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="73699-287">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` código-fonte inclui outras amostras de conversores personalizadas, como:</span><span class="sxs-lookup"><span data-stu-id="73699-287">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="73699-288">[Conversor de Int32 que converte NULL para 0 em desserializar](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="73699-288">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="73699-289">[Conversor de Int32 que permite valores de cadeia de caracteres e de número na desserialização](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="73699-289">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="73699-290">[Conversor de enumeração](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="73699-290">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="73699-291">[\<T>Conversor de lista que aceita dados externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="73699-291">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="73699-292">[Conversor Long [] que funciona com uma lista de números delimitada por vírgulas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="73699-292">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="73699-293">Se você precisar criar um conversor que modifique o comportamento de um conversor interno existente, poderá obter [o código-fonte do conversor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para servir como ponto de partida para personalização.</span><span class="sxs-lookup"><span data-stu-id="73699-293">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73699-294">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="73699-294">Additional resources</span></span>

* <span data-ttu-id="73699-295">[Código-fonte para conversores internos](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="73699-295">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="73699-296">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="73699-296">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="73699-297">Como serializar e desserializar JSON</span><span class="sxs-lookup"><span data-stu-id="73699-297">How to serialize and deserialize JSON</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="73699-298">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="73699-298">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="73699-299">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="73699-299">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="73699-300">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="73699-300">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="73699-301">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="73699-301">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="73699-302">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="73699-302">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="73699-303">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="73699-303">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="73699-304">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="73699-304">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="73699-305">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="73699-305">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="73699-306">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="73699-306">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="73699-307">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="73699-307">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="73699-308">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="73699-308">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="73699-309">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="73699-309">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="73699-310">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73699-310">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="73699-311">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="73699-311">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="73699-312">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="73699-312">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
