---
title: Como escrever conversores personalizados para serialização JSON-.NET
description: Saiba como criar conversores personalizados para as classes de serialização JSON que são fornecidas no System.Text.Json namespace.
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
- converters
ms.openlocfilehash: 008455a77f98cd9975b04001121217866cc2ba6e
ms.sourcegitcommit: 0014aa4d5cb2da56a70e03fc68f663d64df5247a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96918600"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a><span data-ttu-id="4dc5b-103">Como escrever conversores personalizados para serialização JSON (Marshalling) no .NET</span><span class="sxs-lookup"><span data-stu-id="4dc5b-103">How to write custom converters for JSON serialization (marshalling) in .NET</span></span>

<span data-ttu-id="4dc5b-104">Este artigo mostra como criar conversores personalizados para as classes de serialização JSON que são fornecidas no <xref:System.Text.Json> namespace.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-104">This article shows how to create custom converters for the JSON serialization classes that are provided in the <xref:System.Text.Json> namespace.</span></span> <span data-ttu-id="4dc5b-105">Para obter uma introdução ao `System.Text.Json` , consulte [como serializar e desserializar JSON no .net](system-text-json-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-105">For an introduction to `System.Text.Json`, see [How to serialize and deserialize JSON in .NET](system-text-json-how-to.md).</span></span>

<span data-ttu-id="4dc5b-106">Um *conversor* é uma classe que converte um objeto ou um valor de e para JSON.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-106">A *converter* is a class that converts an object or a value to and from JSON.</span></span> <span data-ttu-id="4dc5b-107">O `System.Text.Json` namespace tem conversores internos para a maioria dos tipos primitivos que mapeiam para primitivas de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-107">The `System.Text.Json` namespace has built-in converters for most primitive types that map to JavaScript primitives.</span></span> <span data-ttu-id="4dc5b-108">Você pode escrever conversores personalizados:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-108">You can write custom converters:</span></span>

* <span data-ttu-id="4dc5b-109">Para substituir o comportamento padrão de um conversor interno.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-109">To override the default behavior of a built-in converter.</span></span> <span data-ttu-id="4dc5b-110">Por exemplo, talvez você queira que `DateTime` os valores sejam representados pelo formato mm/dd/aaaa em vez do formato padrão ISO 8601-1:2019.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-110">For example, you might want `DateTime` values to be represented by mm/dd/yyyy format instead of the default  ISO 8601-1:2019 format.</span></span>
* <span data-ttu-id="4dc5b-111">Para dar suporte a um tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-111">To support a custom value type.</span></span> <span data-ttu-id="4dc5b-112">Por exemplo, um `PhoneNumber` struct.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-112">For example, a `PhoneNumber` struct.</span></span>

<span data-ttu-id="4dc5b-113">Você também pode escrever conversores personalizados para personalizar ou estender `System.Text.Json` com funcionalidade não incluída na versão atual.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-113">You can also write custom converters to customize or extend `System.Text.Json` with functionality not included in the current release.</span></span> <span data-ttu-id="4dc5b-114">Os cenários a seguir serão abordados posteriormente neste artigo:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-114">The following scenarios are covered later in this article:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="4dc5b-115">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-115">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4dc5b-116">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-116">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="4dc5b-117">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-117">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="4dc5b-118">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-118">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4dc5b-119">[Dicionário de suporte com chave não cadeia de caracteres](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-119">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="4dc5b-120">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-120">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="4dc5b-121">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-121">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

<span data-ttu-id="4dc5b-122">No código que você escreve para um conversor personalizado, esteja ciente da penalidade de desempenho substancial para usar novas <xref:System.Text.Json.JsonSerializerOptions> instâncias.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-122">In the code you write for a custom converter, be aware of the substantial performance penalty for using new <xref:System.Text.Json.JsonSerializerOptions> instances.</span></span> <span data-ttu-id="4dc5b-123">Para obter mais informações, consulte [reutilizar instâncias de JsonSerializerOptions](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-123">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="custom-converter-patterns"></a><span data-ttu-id="4dc5b-124">Padrões de conversor personalizado</span><span class="sxs-lookup"><span data-stu-id="4dc5b-124">Custom converter patterns</span></span>

<span data-ttu-id="4dc5b-125">Há dois padrões para a criação de um conversor personalizado: o padrão básico e o padrão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-125">There are two patterns for creating a custom converter: the basic pattern and the factory pattern.</span></span> <span data-ttu-id="4dc5b-126">O padrão de fábrica é para conversores que manipulam tipos `Enum` ou genéricos abertos.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-126">The factory pattern is for converters that handle type `Enum` or open generics.</span></span> <span data-ttu-id="4dc5b-127">O padrão básico é para tipos genéricos não genéricos e fechados.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-127">The basic pattern is for non-generic and closed generic types.</span></span>  <span data-ttu-id="4dc5b-128">Por exemplo, os conversores para os seguintes tipos exigem o padrão de fábrica:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-128">For example, converters for the following types require the factory pattern:</span></span>

* <xref:System.Collections.Generic.Dictionary%602>
* <xref:System.Enum>
* <xref:System.Collections.Generic.List%601>

<span data-ttu-id="4dc5b-129">Alguns exemplos de tipos que podem ser tratados pelo padrão básico incluem:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-129">Some examples of types that can be handled by the basic pattern include:</span></span>

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* <xref:System.DateTime>
* <xref:System.Int32>

<span data-ttu-id="4dc5b-130">O padrão básico cria uma classe que pode manipular um tipo.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-130">The basic pattern creates a class that can handle one type.</span></span> <span data-ttu-id="4dc5b-131">O padrão de fábrica cria uma classe que determina, em tempo de execução, qual tipo específico é necessário e cria dinamicamente o conversor apropriado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-131">The factory pattern creates a class that determines, at run time, which specific type is required and dynamically creates the appropriate converter.</span></span>

## <a name="sample-basic-converter"></a><span data-ttu-id="4dc5b-132">Conversor básico de exemplo</span><span class="sxs-lookup"><span data-stu-id="4dc5b-132">Sample basic converter</span></span>

<span data-ttu-id="4dc5b-133">O exemplo a seguir é um conversor que substitui a serialização padrão para um tipo de dados existente.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-133">The following sample is a converter that overrides default serialization for an existing data type.</span></span> <span data-ttu-id="4dc5b-134">O conversor usa o formato mm/dd/aaaa para `DateTimeOffset` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-134">The converter uses mm/dd/yyyy format for `DateTimeOffset` properties.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs":::

## <a name="sample-factory-pattern-converter"></a><span data-ttu-id="4dc5b-135">Conversor de padrão de fábrica de exemplo</span><span class="sxs-lookup"><span data-stu-id="4dc5b-135">Sample factory pattern converter</span></span>

<span data-ttu-id="4dc5b-136">O código a seguir mostra um conversor personalizado que funciona com o `Dictionary<Enum,TValue>` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-136">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`.</span></span> <span data-ttu-id="4dc5b-137">O código segue o padrão de fábrica porque o primeiro parâmetro de tipo genérico é `Enum` e o segundo é aberto.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-137">The code follows the factory pattern because the first generic type parameter is `Enum` and the second is open.</span></span> <span data-ttu-id="4dc5b-138">O `CanConvert` método retorna `true` apenas para um `Dictionary` com dois parâmetros genéricos, o primeiro deles é um `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-138">The `CanConvert` method returns `true` only for a `Dictionary` with two generic parameters, the first of which is an `Enum` type.</span></span> <span data-ttu-id="4dc5b-139">O conversor interno Obtém um conversor existente para lidar com qualquer tipo fornecido no tempo de execução para `TValue` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-139">The inner converter gets an existing converter to handle whichever type is provided at run time for `TValue`.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="4dc5b-140">O código anterior é o mesmo que o mostrado no dicionário de [suporte com uma chave que não seja de cadeia de caracteres](#support-dictionary-with-non-string-key) , mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-140">The preceding code is the same as what is shown in the [Support Dictionary with non-string key](#support-dictionary-with-non-string-key) later in this article.</span></span>

## <a name="steps-to-follow-the-basic-pattern"></a><span data-ttu-id="4dc5b-141">Etapas para seguir o padrão básico</span><span class="sxs-lookup"><span data-stu-id="4dc5b-141">Steps to follow the basic pattern</span></span>

<span data-ttu-id="4dc5b-142">As etapas a seguir explicam como criar um conversor seguindo o padrão básico:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-142">The following steps explain how to create a converter by following the basic pattern:</span></span>

* <span data-ttu-id="4dc5b-143">Crie uma classe que derive de <xref:System.Text.Json.Serialization.JsonConverter%601> onde `T` é o tipo a ser serializado e desserializado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-143">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverter%601> where `T` is the type to be serialized and deserialized.</span></span>
* <span data-ttu-id="4dc5b-144">Substitua o `Read` método para desserializar o JSON de entrada e convertê-lo no tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-144">Override the `Read` method to deserialize the incoming JSON and convert it to type `T`.</span></span> <span data-ttu-id="4dc5b-145">Use o <xref:System.Text.Json.Utf8JsonReader> que é passado para o método para ler o JSON.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-145">Use the <xref:System.Text.Json.Utf8JsonReader> that is passed to the method to read the JSON.</span></span>
* <span data-ttu-id="4dc5b-146">Substitua o `Write` método para serializar o objeto de entrada do tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-146">Override the `Write` method to serialize the incoming object of type `T`.</span></span> <span data-ttu-id="4dc5b-147">Use o <xref:System.Text.Json.Utf8JsonWriter> que é passado para o método para gravar o JSON.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-147">Use the <xref:System.Text.Json.Utf8JsonWriter> that is passed to the method to write the JSON.</span></span>
* <span data-ttu-id="4dc5b-148">Substitua o `CanConvert` método somente se necessário.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-148">Override the `CanConvert` method only if necessary.</span></span> <span data-ttu-id="4dc5b-149">A implementação padrão retorna `true` quando o tipo a ser convertido é do tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-149">The default implementation returns `true` when the type to convert is of type `T`.</span></span> <span data-ttu-id="4dc5b-150">Portanto, os conversores que suportam apenas `T` o tipo não precisam substituir esse método.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-150">Therefore, converters that support only type `T` don't need to override this method.</span></span> <span data-ttu-id="4dc5b-151">Para obter um exemplo de um conversor que precisa substituir esse método, consulte a seção [desserialização polimórfica](#support-polymorphic-deserialization) mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-151">For an example of a converter that does need to override this method, see the [polymorphic deserialization](#support-polymorphic-deserialization) section later in this article.</span></span>

<span data-ttu-id="4dc5b-152">Você pode consultar o [código-fonte dos conversores internos](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) como implementações de referência para escrever conversores personalizados.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-152">You can refer to the [built-in converters source code](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) as reference implementations for writing custom converters.</span></span>

## <a name="steps-to-follow-the-factory-pattern"></a><span data-ttu-id="4dc5b-153">Etapas para seguir o padrão de fábrica</span><span class="sxs-lookup"><span data-stu-id="4dc5b-153">Steps to follow the factory pattern</span></span>

<span data-ttu-id="4dc5b-154">As etapas a seguir explicam como criar um conversor seguindo o padrão de fábrica:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-154">The following steps explain how to create a converter by following the factory pattern:</span></span>

* <span data-ttu-id="4dc5b-155">Crie uma classe que deriva de <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-155">Create a class that derives from <xref:System.Text.Json.Serialization.JsonConverterFactory>.</span></span>
* <span data-ttu-id="4dc5b-156">Substitua o `CanConvert` método para retornar true quando o tipo a ser convertido for aquele que o conversor pode manipular.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-156">Override the `CanConvert` method to return true when the type to convert is one that the converter can handle.</span></span> <span data-ttu-id="4dc5b-157">Por exemplo, se o conversor for para `List<T>` ele, ele só poderá manipular `List<int>` , `List<string>` e `List<DateTime>` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-157">For example, if the converter is for `List<T>` it might only handle `List<int>`, `List<string>`, and `List<DateTime>`.</span></span>
* <span data-ttu-id="4dc5b-158">Substitua o `CreateConverter` método para retornar uma instância de uma classe de conversor que manipulará o tipo a ser convertido que é fornecido no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-158">Override the `CreateConverter` method to return an instance of a converter class that will handle the type-to-convert that is provided at run time.</span></span>
* <span data-ttu-id="4dc5b-159">Crie a classe de conversor `CreateConverter` instanciada pelo método.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-159">Create the converter class that the `CreateConverter` method instantiates.</span></span>

<span data-ttu-id="4dc5b-160">O padrão de fábrica é necessário para os genéricos abertos porque o código para converter um objeto de e para uma cadeia de caracteres não é o mesmo para todos os tipos.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-160">The factory pattern is required for open generics because the code to convert an object to and from a string isn't the same for all types.</span></span> <span data-ttu-id="4dc5b-161">Um conversor para um tipo genérico aberto ( `List<T>` , por exemplo) precisa criar um conversor para um tipo genérico fechado ( `List<DateTime>` , por exemplo) em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-161">A converter for an open generic type (`List<T>`, for example) has to create a converter for a closed generic type (`List<DateTime>`, for example) behind the scenes.</span></span> <span data-ttu-id="4dc5b-162">O código deve ser gravado para lidar com cada tipo fechado genérico que o conversor pode manipular.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-162">Code must be written to handle each closed-generic type that the converter can handle.</span></span>

<span data-ttu-id="4dc5b-163">O `Enum` tipo é semelhante a um tipo genérico aberto: um conversor de `Enum` deve criar um conversor para um específico `Enum` ( `WeekdaysEnum` , por exemplo) em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-163">The `Enum` type is similar to an open generic type: a converter for `Enum` has to create a converter for a specific `Enum` (`WeekdaysEnum`, for example) behind the scenes.</span></span>

## <a name="error-handling"></a><span data-ttu-id="4dc5b-164">Tratamento de erros</span><span class="sxs-lookup"><span data-stu-id="4dc5b-164">Error handling</span></span>

<span data-ttu-id="4dc5b-165">Se você precisar lançar uma exceção no código de tratamento de erros, considere lançar um <xref:System.Text.Json.JsonException> sem uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-165">If you need to throw an exception in error-handling code, consider throwing a <xref:System.Text.Json.JsonException> without a message.</span></span> <span data-ttu-id="4dc5b-166">Esse tipo de exceção cria automaticamente uma mensagem que inclui o caminho para a parte do JSON que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-166">This exception type automatically creates a message that includes the path to the part of the JSON that caused the error.</span></span> <span data-ttu-id="4dc5b-167">Por exemplo, a instrução `throw new JsonException();` produz uma mensagem de erro semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-167">For example, the statement `throw new JsonException();` produces an error message like the following example:</span></span>

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

<span data-ttu-id="4dc5b-168">Se você fornecer uma mensagem (por exemplo, `throw new JsonException("Error occurred")` , a exceção ainda fornecerá o caminho na <xref:System.Text.Json.JsonException.Path> propriedade.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-168">If you do provide a message (for example, `throw new JsonException("Error occurred")`, the exception still provides the path in the <xref:System.Text.Json.JsonException.Path> property.</span></span>

## <a name="register-a-custom-converter"></a><span data-ttu-id="4dc5b-169">Registrar um conversor personalizado</span><span class="sxs-lookup"><span data-stu-id="4dc5b-169">Register a custom converter</span></span>

<span data-ttu-id="4dc5b-170">*Registre* um conversor personalizado para fazer com `Serialize` que os métodos e o `Deserialize` usem.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-170">*Register* a custom converter to make the `Serialize` and `Deserialize` methods use it.</span></span> <span data-ttu-id="4dc5b-171">Escolha uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-171">Choose one of the following approaches:</span></span>

* <span data-ttu-id="4dc5b-172">Adicione uma instância da classe converter à <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> coleção.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-172">Add an instance of the converter class to the <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> collection.</span></span>
* <span data-ttu-id="4dc5b-173">Aplique o atributo [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) às propriedades que exigem o conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-173">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to the properties that require the custom converter.</span></span>
* <span data-ttu-id="4dc5b-174">Aplique o atributo [[jsonconverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a uma classe ou a uma struct que represente um tipo de valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-174">Apply the [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) attribute to a class or a struct that represents a custom value type.</span></span>

## <a name="registration-sample---converters-collection"></a><span data-ttu-id="4dc5b-175">Amostra de registro – coleção de conversores</span><span class="sxs-lookup"><span data-stu-id="4dc5b-175">Registration sample - Converters collection</span></span>

<span data-ttu-id="4dc5b-176">Veja um exemplo que torna o <xref:System.ComponentModel.DateTimeOffsetConverter> padrão para propriedades do tipo <xref:System.DateTimeOffset> :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-176">Here's an example that makes the <xref:System.ComponentModel.DateTimeOffsetConverter> the default for properties of type <xref:System.DateTimeOffset>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Serialize":::

<span data-ttu-id="4dc5b-177">Suponha que você Serialize uma instância do seguinte tipo:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-177">Suppose you serialize an instance of the following type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

<span data-ttu-id="4dc5b-178">Aqui está um exemplo de saída JSON que mostra que o conversor personalizado foi usado:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-178">Here's an example of JSON output that shows the custom converter was used:</span></span>

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4dc5b-179">O código a seguir usa a mesma abordagem para desserializar usando o `DateTimeOffset` conversor personalizado:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-179">The following code uses the same approach to deserialize using the custom `DateTimeOffset` converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-property"></a><span data-ttu-id="4dc5b-180">Exemplo de registro-[Jsonconverter] em uma propriedade</span><span class="sxs-lookup"><span data-stu-id="4dc5b-180">Registration sample - [JsonConverter] on a property</span></span>

<span data-ttu-id="4dc5b-181">O código a seguir seleciona um conversor personalizado para a `Date` Propriedade:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-181">The following code selects a custom converter for the `Date` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithConverterAttribute":::

<span data-ttu-id="4dc5b-182">O código a ser serializado `WeatherForecastWithConverterAttribute` não exige o uso de `JsonSerializeOptions.Converters` :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-182">The code to serialize `WeatherForecastWithConverterAttribute` doesn't require the use of `JsonSerializeOptions.Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Serialize":::

<span data-ttu-id="4dc5b-183">O código para desserializar também não exige o uso de `Converters` :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-183">The code to deserialize also doesn't require the use of `Converters`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-type"></a><span data-ttu-id="4dc5b-184">Exemplo de registro-[Jsonconverter] em um tipo</span><span class="sxs-lookup"><span data-stu-id="4dc5b-184">Registration sample - [JsonConverter] on a type</span></span>

<span data-ttu-id="4dc5b-185">Aqui está o código que cria uma struct e aplica o `[JsonConverter]` atributo a ela:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-185">Here's code that creates a struct and applies the `[JsonConverter]` attribute to it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Temperature.cs":::

<span data-ttu-id="4dc5b-186">Este é o conversor personalizado para o struct anterior:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-186">Here's the custom converter for the preceding struct:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/TemperatureConverter.cs":::

<span data-ttu-id="4dc5b-187">O `[JsonConvert]` atributo na estrutura registra o conversor personalizado como o padrão para propriedades do tipo `Temperature` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-187">The `[JsonConvert]` attribute on the struct registers the custom converter as the default for properties of type `Temperature`.</span></span> <span data-ttu-id="4dc5b-188">O conversor é usado automaticamente na `TemperatureCelsius` Propriedade do seguinte tipo ao serializar ou desserializar:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-188">The converter is automatically used on the `TemperatureCelsius` property of the following type when you serialize or deserialize it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithTemperatureStruct":::

## <a name="converter-registration-precedence"></a><span data-ttu-id="4dc5b-189">Precedência de registro do conversor</span><span class="sxs-lookup"><span data-stu-id="4dc5b-189">Converter registration precedence</span></span>

<span data-ttu-id="4dc5b-190">Durante a serialização ou desserialização, um conversor é escolhido para cada elemento JSON na seguinte ordem, listada da prioridade mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-190">During serialization or deserialization, a converter is chosen for each JSON element in the following order, listed from highest priority to lowest:</span></span>

* <span data-ttu-id="4dc5b-191">`[JsonConverter]` aplicado a uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-191">`[JsonConverter]` applied to a property.</span></span>
* <span data-ttu-id="4dc5b-192">Um conversor adicionado à `Converters` coleção.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-192">A converter added to the `Converters` collection.</span></span>
* <span data-ttu-id="4dc5b-193">`[JsonConverter]` aplicado a um tipo de valor personalizado ou POCO.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-193">`[JsonConverter]` applied to a custom value type or POCO.</span></span>

<span data-ttu-id="4dc5b-194">Se vários conversores personalizados para um tipo forem registrados na `Converters` coleção, o primeiro conversor que retorna true para `CanConvert` será usado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-194">If multiple custom converters for a type are registered in the `Converters` collection, the first converter that returns true for `CanConvert` is used.</span></span>

<span data-ttu-id="4dc5b-195">Um conversor interno será escolhido somente se nenhum conversor personalizado aplicável for registrado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-195">A built-in converter is chosen only if no applicable custom converter is registered.</span></span>

## <a name="converter-samples-for-common-scenarios"></a><span data-ttu-id="4dc5b-196">Exemplos de conversor para cenários comuns</span><span class="sxs-lookup"><span data-stu-id="4dc5b-196">Converter samples for common scenarios</span></span>

<span data-ttu-id="4dc5b-197">As seções a seguir fornecem exemplos de conversor que abordam alguns cenários comuns que a funcionalidade interna não trata.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-197">The following sections provide converter samples that address some common scenarios that built-in functionality doesn't handle.</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="4dc5b-198">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-198">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4dc5b-199">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-199">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="4dc5b-200">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-200">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="4dc5b-201">[Desserializar tipos inferidos para propriedades de objeto](#deserialize-inferred-types-to-object-properties).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-201">[Deserialize inferred types to object properties](#deserialize-inferred-types-to-object-properties).</span></span>
* <span data-ttu-id="4dc5b-202">[Dicionário de suporte com chave não cadeia de caracteres](#support-dictionary-with-non-string-key).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-202">[Support Dictionary with non-string key](#support-dictionary-with-non-string-key).</span></span>
* <span data-ttu-id="4dc5b-203">[Suporte à desserialização polimórfico](#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-203">[Support polymorphic deserialization](#support-polymorphic-deserialization).</span></span>
* <span data-ttu-id="4dc5b-204">[Dar suporte à viagem de ida \<T> e volta para pilha](#support-round-trip-for-stackt).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-204">[Support round-trip for Stack\<T>](#support-round-trip-for-stackt).</span></span>
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a><span data-ttu-id="4dc5b-205">Desserializar tipos inferidos para propriedades de objeto</span><span class="sxs-lookup"><span data-stu-id="4dc5b-205">Deserialize inferred types to object properties</span></span>

<span data-ttu-id="4dc5b-206">Ao desserializar para uma propriedade do tipo `object` , um `JsonElement` objeto é criado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-206">When deserializing to a property of type `object`, a `JsonElement` object is created.</span></span> <span data-ttu-id="4dc5b-207">O motivo é que o desserializador não sabe qual tipo de CLR deve ser criado e não tenta adivinhar.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-207">The reason is that the deserializer doesn't know what CLR type to create, and it doesn't try to guess.</span></span> <span data-ttu-id="4dc5b-208">Por exemplo, se uma propriedade JSON tiver "true", o desserializador não inferirá que o valor é a `Boolean` e, se um elemento tiver "01/01/2019", o desserializador não inferirá que é um `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-208">For example, if a JSON property has "true", the deserializer doesn't infer that the value is a `Boolean`, and if an element has "01/01/2019", the deserializer doesn't infer that it's a `DateTime`.</span></span>

<span data-ttu-id="4dc5b-209">A inferência de tipos pode ser imprecisa.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-209">Type inference can be inaccurate.</span></span> <span data-ttu-id="4dc5b-210">Se o desserializador analisar um número JSON que não tenha nenhum ponto decimal como um `long` , isso poderá resultar em problemas fora do intervalo se o valor tiver sido originalmente serializado como um `ulong` ou `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-210">If the deserializer parses a JSON number that has no decimal point as a `long`, that might result in out-of-range issues if the value was originally serialized as a `ulong` or `BigInteger`.</span></span> <span data-ttu-id="4dc5b-211">A análise de um número que tenha um ponto decimal como `double` pode perder a precisão se o número tiver sido originalmente serializado como um `decimal` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-211">Parsing a number that has a decimal point as a `double` might lose precision if the number was originally serialized as a `decimal`.</span></span>

<span data-ttu-id="4dc5b-212">Para cenários que exigem a inferência de tipos, o código a seguir mostra um conversor personalizado para `object` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-212">For scenarios that require type inference, the following code shows a custom converter for `object` properties.</span></span> <span data-ttu-id="4dc5b-213">O código converte:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-213">The code converts:</span></span>

* <span data-ttu-id="4dc5b-214">`true` e `false` para `Boolean`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-214">`true` and `false` to `Boolean`</span></span>
* <span data-ttu-id="4dc5b-215">Números sem um decimal para `long`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-215">Numbers without a decimal to `long`</span></span>
* <span data-ttu-id="4dc5b-216">Números com um decimal para `double`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-216">Numbers with a decimal to `double`</span></span>
* <span data-ttu-id="4dc5b-217">Datas para `DateTime`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-217">Dates to `DateTime`</span></span>
* <span data-ttu-id="4dc5b-218">Cadeias de caracteres para `string`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-218">Strings to `string`</span></span>
* <span data-ttu-id="4dc5b-219">Tudo o mais a `JsonElement`</span><span class="sxs-lookup"><span data-stu-id="4dc5b-219">Everything else to `JsonElement`</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs":::

<span data-ttu-id="4dc5b-220">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-220">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs" id="Register":::

<span data-ttu-id="4dc5b-221">Aqui está um tipo de exemplo com `object` Propriedades:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-221">Here's an example type with `object` properties:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithObjectProperties":::

<span data-ttu-id="4dc5b-222">O exemplo a seguir de JSON para desserializar contém valores que serão desserializados como `DateTime` , `long` e `string` :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-222">The following example of JSON to deserialize contains values that will be deserialized as `DateTime`, `long`, and `string`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="4dc5b-223">Sem o conversor personalizado, a desserialização coloca um `JsonElement` em cada propriedade.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-223">Without the custom converter, deserialization puts a `JsonElement` in each property.</span></span>

<span data-ttu-id="4dc5b-224">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` namespace tem mais exemplos de conversores personalizados que manipulam a desserialização para `object` Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-224">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle deserialization to `object` properties.</span></span>

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a><span data-ttu-id="4dc5b-225">Dicionário de suporte com chave não cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4dc5b-225">Support Dictionary with non-string key</span></span>

<span data-ttu-id="4dc5b-226">O suporte interno para coleções de dicionário é para o `Dictionary<string, TValue>` .</span><span class="sxs-lookup"><span data-stu-id="4dc5b-226">The built-in support for dictionary collections is for `Dictionary<string, TValue>`.</span></span> <span data-ttu-id="4dc5b-227">Ou seja, a chave deve ser uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-227">That is, the key must be a string.</span></span> <span data-ttu-id="4dc5b-228">Para dar suporte a um dicionário com um inteiro ou algum outro tipo como a chave, um conversor personalizado é necessário.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-228">To support a dictionary with an integer or some other type as the key, a custom converter is required.</span></span>

<span data-ttu-id="4dc5b-229">O código a seguir mostra um conversor personalizado que funciona com `Dictionary<Enum,TValue>` :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-229">The following code shows a custom converter that works with `Dictionary<Enum,TValue>`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

<span data-ttu-id="4dc5b-230">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-230">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs" id="Register":::

<span data-ttu-id="4dc5b-231">O conversor pode serializar e desserializar a `TemperatureRanges` propriedade da seguinte classe que usa o seguinte `Enum` :</span><span class="sxs-lookup"><span data-stu-id="4dc5b-231">The converter can serialize and deserialize the `TemperatureRanges` property of the following class that uses the following `Enum`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnumDictionary":::

<span data-ttu-id="4dc5b-232">A saída JSON da serialização é semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-232">The JSON output from serialization looks like the following example:</span></span>

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

<span data-ttu-id="4dc5b-233">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` namespace tem mais exemplos de conversores personalizados que manipulam dicionários que não são de chave de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-233">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` namespace has more examples of custom converters that handle non-string-key dictionaries.</span></span>
::: zone-end

### <a name="support-polymorphic-deserialization"></a><span data-ttu-id="4dc5b-234">Suporte à desserialização polimórfico</span><span class="sxs-lookup"><span data-stu-id="4dc5b-234">Support polymorphic deserialization</span></span>

<span data-ttu-id="4dc5b-235">Os recursos internos fornecem um intervalo limitado de [serialização polimórfico](system-text-json-polymorphism.md) , mas não há suporte para desserialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-235">Built-in features provide a limited range of [polymorphic serialization](system-text-json-polymorphism.md) but no support for deserialization at all.</span></span> <span data-ttu-id="4dc5b-236">A desserialização requer um conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-236">Deserialization requires a custom converter.</span></span>

<span data-ttu-id="4dc5b-237">Suponha, por exemplo, que você tenha uma `Person` classe base abstrata, `Employee` com `Customer` classes derivadas e.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-237">Suppose, for example, you have a `Person` abstract base class, with `Employee` and `Customer` derived classes.</span></span> <span data-ttu-id="4dc5b-238">A desserialização polimórfica significa que, em tempo de design, você pode especificar `Person` como o destino de desserialização e `Customer` `Employee` os objetos no JSON são corretamente desserializados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-238">Polymorphic deserialization means that at design time you can specify `Person` as the deserialization target, and `Customer` and `Employee` objects in the JSON are correctly deserialized at run time.</span></span> <span data-ttu-id="4dc5b-239">Durante a desserialização, você precisa encontrar pistas que identificam o tipo necessário no JSON.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-239">During deserialization, you have to find clues that identify the required type in the JSON.</span></span> <span data-ttu-id="4dc5b-240">Os tipos de pistas disponíveis variam de acordo com cada cenário.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-240">The kinds of clues available vary with each scenario.</span></span> <span data-ttu-id="4dc5b-241">Por exemplo, uma propriedade discriminadora pode estar disponível ou talvez você precise contar com a presença ou a ausência de uma determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-241">For example, a discriminator property might be available or you might have to rely on the presence or absence of a particular property.</span></span> <span data-ttu-id="4dc5b-242">A versão atual do `System.Text.Json` não fornece atributos para especificar como lidar com cenários de desserialização polimórfico, para que conversores personalizados sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-242">The current release of `System.Text.Json` doesn't provide attributes to specify how to handle polymorphic deserialization scenarios, so custom converters are required.</span></span>

<span data-ttu-id="4dc5b-243">O código a seguir mostra uma classe base, duas classes derivadas e um conversor personalizado para elas.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-243">The following code shows a base class, two derived classes, and a custom converter for them.</span></span> <span data-ttu-id="4dc5b-244">O conversor usa uma propriedade discriminadora para fazer desserialização polimórfica.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-244">The converter uses a discriminator property to do polymorphic deserialization.</span></span> <span data-ttu-id="4dc5b-245">O discriminador de tipo não está nas definições de classe, mas é criado durante a serialização e é lido durante a desserialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-245">The type discriminator isn't in the class definitions but is created during serialization and is read during deserialization.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Person.cs" id="Person":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs":::

<span data-ttu-id="4dc5b-246">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-246">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs" id="Register":::

<span data-ttu-id="4dc5b-247">O conversor pode desserializar o JSON criado usando o mesmo conversor para serializar, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-247">The converter can deserialize JSON that was created by using the same converter to serialize, for example:</span></span>

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

<span data-ttu-id="4dc5b-248">O código do conversor no exemplo anterior lê e grava cada propriedade manualmente.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-248">The converter code in the preceding example reads and writes each property manually.</span></span> <span data-ttu-id="4dc5b-249">Uma alternativa é chamar `Deserialize` ou `Serialize` fazer parte do trabalho.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-249">An alternative is to call `Deserialize` or `Serialize` to do some of the work.</span></span> <span data-ttu-id="4dc5b-250">Para obter um exemplo, consulte [esta postagem de StackOverflow](https://stackoverflow.com/a/59744873/12509023).</span><span class="sxs-lookup"><span data-stu-id="4dc5b-250">For an example, see [this StackOverflow post](https://stackoverflow.com/a/59744873/12509023).</span></span>

### <a name="support-round-trip-for-stackt"></a><span data-ttu-id="4dc5b-251">Dar suporte à viagem de ida e volta para a pilha\<T></span><span class="sxs-lookup"><span data-stu-id="4dc5b-251">Support round trip for Stack\<T></span></span>

<span data-ttu-id="4dc5b-252">Se você desserializar uma cadeia de caracteres JSON em um <xref:System.Collections.Generic.Stack%601> objeto e, em seguida, serializar esse objeto, o conteúdo da pilha estará na ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-252">If you deserialize a JSON string into a <xref:System.Collections.Generic.Stack%601> object and then serialize that object, the contents of the stack are in reverse order.</span></span> <span data-ttu-id="4dc5b-253">Esse comportamento se aplica aos tipos e à interface a seguir e aos tipos definidos pelo usuário que derivam deles:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-253">This behavior applies to the following types and interface, and user-defined types that derive from them:</span></span>

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

<span data-ttu-id="4dc5b-254">Para dar suporte à serialização e desserialização que retém o pedido original na pilha, é necessário um conversor personalizado.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-254">To support serialization and deserialization that retains the original order in the stack, a custom converter is required.</span></span>

<span data-ttu-id="4dc5b-255">O código a seguir mostra um conversor personalizado que permite a passagem de ida e volta de `Stack<T>` objetos:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-255">The following code shows a custom converter that enables round-tripping to and from `Stack<T>` objects:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs":::

<span data-ttu-id="4dc5b-256">O código a seguir registra o conversor:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-256">The following code registers the converter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs" id="Register":::

## <a name="handle-null-values"></a><span data-ttu-id="4dc5b-257">Manipular valores nulos</span><span class="sxs-lookup"><span data-stu-id="4dc5b-257">Handle null values</span></span>

<span data-ttu-id="4dc5b-258">Por padrão, o serializador trata valores nulos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-258">By default, the serializer handles null values as follows:</span></span>

* <span data-ttu-id="4dc5b-259">Para tipos de referência e <xref:System.Nullable%601> tipos:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-259">For reference types and <xref:System.Nullable%601> types:</span></span>

  * <span data-ttu-id="4dc5b-260">Ele não passa `null` para conversores personalizados na serialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-260">It does not pass `null` to custom converters on serialization.</span></span>
  * <span data-ttu-id="4dc5b-261">Ele não passa `JsonTokenType.Null` para conversores personalizados na desserialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-261">It does not pass `JsonTokenType.Null` to custom converters on deserialization.</span></span>
  * <span data-ttu-id="4dc5b-262">Ele retorna uma `null` instância na desserialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-262">It returns a `null` instance on deserialization.</span></span>
  * <span data-ttu-id="4dc5b-263">Ele grava `null` diretamente com o gravador na serialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-263">It writes `null` directly with the writer on serialization.</span></span>

* <span data-ttu-id="4dc5b-264">Para tipos de valores não anuláveis:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-264">For non-nullable value types:</span></span>

  * <span data-ttu-id="4dc5b-265">Ele passa `JsonTokenType.Null` para conversores personalizados na desserialização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-265">It passes `JsonTokenType.Null` to custom converters on deserialization.</span></span> <span data-ttu-id="4dc5b-266">(Se nenhum conversor personalizado estiver disponível, uma `JsonException` exceção será lançada pelo conversor interno para o tipo.)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-266">(If no custom converter is available, a `JsonException` exception is thrown by the internal converter for the type.)</span></span>

<span data-ttu-id="4dc5b-267">Esse comportamento de tratamento nulo é principalmente para otimizar o desempenho, ignorando uma chamada extra para o conversor.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-267">This null-handling behavior is primarily to optimize performance by skipping an extra call to the converter.</span></span> <span data-ttu-id="4dc5b-268">Além disso, evita a força de conversores para tipos anuláveis a serem verificados `null` no início de cada `Read` e `Write` substituição de método.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-268">In addition, it avoids forcing converters for nullable types to check for `null` at the start of every `Read` and `Write` method override.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="4dc5b-269">Para habilitar um conversor personalizado para tratar `null` de uma referência ou tipo de valor, substitua <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> para retornar `true` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-269">To enable a custom converter to handle `null` for a reference or value type, override <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType> to return `true`, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a><span data-ttu-id="4dc5b-270">Outras amostras de conversor personalizadas</span><span class="sxs-lookup"><span data-stu-id="4dc5b-270">Other custom converter samples</span></span>

<span data-ttu-id="4dc5b-271">O artigo [migrar de Newtonsoft.Json para System.Text.Json ](system-text-json-migrate-from-newtonsoft-how-to.md) contém exemplos adicionais de conversores personalizados.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-271">The [Migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md) article contains additional samples of custom converters.</span></span>

<span data-ttu-id="4dc5b-272">A [pasta de testes de unidade](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) no `System.Text.Json.Serialization` código-fonte inclui outras amostras de conversores personalizadas, como:</span><span class="sxs-lookup"><span data-stu-id="4dc5b-272">The [unit tests folder](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) in the `System.Text.Json.Serialization` source code includes other custom converter samples, such as:</span></span>

* <span data-ttu-id="4dc5b-273">[Conversor de Int32 que converte NULL para 0 em desserializar](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-273">[Int32 converter that converts null to 0 on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)</span></span>
* <span data-ttu-id="4dc5b-274">[Conversor de Int32 que permite valores de cadeia de caracteres e de número na desserialização](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-274">[Int32 converter that allows both string and number values on deserialize](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)</span></span>
* <span data-ttu-id="4dc5b-275">[Conversor de enumeração](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-275">[Enum converter](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)</span></span>
* <span data-ttu-id="4dc5b-276">[\<T>Conversor de lista que aceita dados externos](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-276">[List\<T> converter that accepts external data](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)</span></span>
* <span data-ttu-id="4dc5b-277">[Conversor Long [] que funciona com uma lista de números delimitada por vírgulas](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-277">[Long[] converter that works with a comma-delimited list of numbers](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)</span></span>

<span data-ttu-id="4dc5b-278">Se você precisar criar um conversor que modifique o comportamento de um conversor interno existente, poderá obter [o código-fonte do conversor existente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) para servir como ponto de partida para personalização.</span><span class="sxs-lookup"><span data-stu-id="4dc5b-278">If you need to make a converter that modifies the behavior of an existing built-in converter, you can get [the source code of the existing converter](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) to serve as a starting point for customization.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4dc5b-279">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4dc5b-279">Additional resources</span></span>

* <span data-ttu-id="4dc5b-280">[Código-fonte para conversores internos](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-280">[Source code for built-in converters](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)</span></span>
* [<span data-ttu-id="4dc5b-281">Suporte a DateTime e DateTimeOffset em System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="4dc5b-281">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="4dc5b-282">Como personalizar a codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="4dc5b-282">How to customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="4dc5b-283">Como escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="4dc5b-283">How to write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* <span data-ttu-id="4dc5b-284">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-284">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="4dc5b-285">[System.Text.Json. Referência da API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="4dc5b-285">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
