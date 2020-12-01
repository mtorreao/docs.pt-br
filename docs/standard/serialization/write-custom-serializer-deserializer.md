---
title: Como escrever serializadores personalizados e desserializadores com o System.Text.Json
description: Saiba como escrever serializadores personalizados e desserializadores para JSON usando o System.Text.Json namespace.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a01d3c8dd18c114ea1c3aabc402bc841a6025ffe
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439906"
---
# <a name="how-to-write-custom-serializers-and-deserializers-with-no-locsystemtextjson"></a><span data-ttu-id="998ac-103">Como escrever serializadores personalizados e desserializadores com o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="998ac-103">How to write custom serializers and deserializers with System.Text.Json</span></span>

<span data-ttu-id="998ac-104"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> é um leitor de alto desempenho, de baixa alocação e somente de encaminhamento para texto JSON codificado em UTF-8, lido de um `ReadOnlySpan<byte>` ou `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="998ac-104"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="998ac-105">O `Utf8JsonReader` é um tipo de baixo nível que pode ser usado para criar analisadores e desserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="998ac-105">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="998ac-106">O <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> método usa `Utf8JsonReader` nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="998ac-106">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="998ac-107"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> é uma maneira de alto desempenho para escrever texto JSON codificado em UTF-8 de tipos comuns do .NET como `String` , `Int32` e `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="998ac-107"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="998ac-108">O gravador é um tipo de baixo nível que pode ser usado para criar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="998ac-108">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="998ac-109">O <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> método usa `Utf8JsonWriter` nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="998ac-109">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="998ac-110"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> fornece a capacidade de criar um Modelo de Objeto do Documento somente leitura (DOM) usando o `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="998ac-110"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="998ac-111">O DOM fornece acesso aleatório aos dados em uma carga JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-111">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="998ac-112">Os elementos JSON que compõem a carga podem ser acessados por meio do <xref:System.Text.Json.JsonElement> tipo.</span><span class="sxs-lookup"><span data-stu-id="998ac-112">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="998ac-113">O `JsonElement` tipo fornece enumeradores de matriz e de objeto juntamente com APIs para converter texto JSON em tipos .net comuns.</span><span class="sxs-lookup"><span data-stu-id="998ac-113">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="998ac-114">`JsonDocument` expõe uma <xref:System.Text.Json.JsonDocument.RootElement> propriedade.</span><span class="sxs-lookup"><span data-stu-id="998ac-114">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="998ac-115">As seções a seguir mostram como usar essas ferramentas para ler e gravar o JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-115">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="998ac-116">Usar o JsonDocument para acessar dados</span><span class="sxs-lookup"><span data-stu-id="998ac-116">Use JsonDocument for access to data</span></span>

<span data-ttu-id="998ac-117">O exemplo a seguir mostra como usar a <xref:System.Text.Json.JsonDocument> classe para acesso aleatório a dados em uma cadeia de caracteres JSON:</span><span class="sxs-lookup"><span data-stu-id="998ac-117">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades1":::

<span data-ttu-id="998ac-118">O código anterior:</span><span class="sxs-lookup"><span data-stu-id="998ac-118">The preceding code:</span></span>

* <span data-ttu-id="998ac-119">Assume que o JSON a ser analisado está em uma cadeia de caracteres chamada `jsonString` .</span><span class="sxs-lookup"><span data-stu-id="998ac-119">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="998ac-120">Calcula uma classificação média para objetos em uma `Students` matriz que tem uma `Grade` propriedade.</span><span class="sxs-lookup"><span data-stu-id="998ac-120">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="998ac-121">Atribui uma classificação padrão de 70 para alunos que não têm uma classificação.</span><span class="sxs-lookup"><span data-stu-id="998ac-121">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="998ac-122">Conta os alunos incrementando uma `count` variável com cada iteração.</span><span class="sxs-lookup"><span data-stu-id="998ac-122">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="998ac-123">Uma alternativa é chamar <xref:System.Text.Json.JsonElement.GetArrayLength%2A> , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="998ac-123">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades2":::

<span data-ttu-id="998ac-124">Veja um exemplo do JSON que esse código processa:</span><span class="sxs-lookup"><span data-stu-id="998ac-124">Here's an example of the JSON that this code processes:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="998ac-125">Usar JsonDocument para gravar JSON</span><span class="sxs-lookup"><span data-stu-id="998ac-125">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="998ac-126">O exemplo a seguir mostra como gravar JSON de um <xref:System.Text.Json.JsonDocument> :</span><span class="sxs-lookup"><span data-stu-id="998ac-126">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs" id="Serialize":::

<span data-ttu-id="998ac-127">O código anterior:</span><span class="sxs-lookup"><span data-stu-id="998ac-127">The preceding code:</span></span>

* <span data-ttu-id="998ac-128">Lê um arquivo JSON, carrega os dados em um `JsonDocument` e grava JSON formatado (bem-impresso) em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="998ac-128">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="998ac-129">Usa <xref:System.Text.Json.JsonDocumentOptions> para especificar que os comentários no JSON de entrada são permitidos, mas ignorados.</span><span class="sxs-lookup"><span data-stu-id="998ac-129">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="998ac-130">Quando terminar, chama <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> o gravador.</span><span class="sxs-lookup"><span data-stu-id="998ac-130">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="998ac-131">Uma alternativa é deixar a liberação automática do gravador quando ela é descartada.</span><span class="sxs-lookup"><span data-stu-id="998ac-131">An alternative is to let the writer auto-flush when it's disposed.</span></span>

<span data-ttu-id="998ac-132">Aqui está um exemplo de entrada JSON a ser processada pelo código de exemplo:</span><span class="sxs-lookup"><span data-stu-id="998ac-132">Here's an example of JSON input to be processed by the example code:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/Grades.json":::

<span data-ttu-id="998ac-133">O resultado é a seguinte saída JSON bem impressa:</span><span class="sxs-lookup"><span data-stu-id="998ac-133">The result is the following pretty-printed JSON output:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="998ac-134">Usar Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="998ac-134">Use Utf8JsonWriter</span></span>

<span data-ttu-id="998ac-135">O exemplo a seguir mostra como usar a <xref:System.Text.Json.Utf8JsonWriter> classe:</span><span class="sxs-lookup"><span data-stu-id="998ac-135">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs" id="Serialize":::

## <a name="use-utf8jsonreader"></a><span data-ttu-id="998ac-136">Usar Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="998ac-136">Use Utf8JsonReader</span></span>

<span data-ttu-id="998ac-137">O exemplo a seguir mostra como usar a <xref:System.Text.Json.Utf8JsonReader> classe:</span><span class="sxs-lookup"><span data-stu-id="998ac-137">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs" id="Deserialize":::

<span data-ttu-id="998ac-138">O código anterior pressupõe que a `jsonUtf8` variável é uma matriz de bytes que contém um JSON válido, codificado como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="998ac-138">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="998ac-139">Filtrar dados usando Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="998ac-139">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="998ac-140">O exemplo a seguir mostra como ler de forma síncrona um arquivo e procurar um valor.</span><span class="sxs-lookup"><span data-stu-id="998ac-140">The following example shows how to synchronously read a file, and search for a value.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs":::

<span data-ttu-id="998ac-141">Para obter uma versão assíncrona deste exemplo, consulte [.net Samples JSON Project](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).</span><span class="sxs-lookup"><span data-stu-id="998ac-141">For an asynchronous version of this example, see [.NET samples JSON project](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).</span></span>

<span data-ttu-id="998ac-142">O código anterior:</span><span class="sxs-lookup"><span data-stu-id="998ac-142">The preceding code:</span></span>

* <span data-ttu-id="998ac-143">Assume que o JSON contém uma matriz de objetos e cada objeto pode conter uma propriedade "Name" do tipo cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="998ac-143">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="998ac-144">Conta objetos e valores de propriedade "Name" que terminam com "University".</span><span class="sxs-lookup"><span data-stu-id="998ac-144">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="998ac-145">Pressupõe que o arquivo é codificado como UTF-16 e o codifica em UTF-8.</span><span class="sxs-lookup"><span data-stu-id="998ac-145">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="998ac-146">Um arquivo codificado como UTF-8 pode ser lido diretamente em um `ReadOnlySpan<byte>` , usando o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="998ac-146">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="998ac-147">Se o arquivo contiver uma marca de ordem de byte (BOM) UTF-8, remova-a antes de passar os bytes para o `Utf8JsonReader` , uma vez que o leitor espera o texto.</span><span class="sxs-lookup"><span data-stu-id="998ac-147">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="998ac-148">Caso contrário, a BOM será considerada JSON inválido e o leitor lançará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="998ac-148">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="998ac-149">Aqui está um exemplo de JSON que o código anterior pode ler.</span><span class="sxs-lookup"><span data-stu-id="998ac-149">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="998ac-150">A mensagem de resumo resultante é "2 de 4 têm nomes que terminam com" University "":</span><span class="sxs-lookup"><span data-stu-id="998ac-150">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/Universities.json":::

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="998ac-151">Ler de um fluxo usando Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="998ac-151">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="998ac-152">Ao ler um arquivo grande (um gigabyte ou mais, por exemplo), talvez você queira evitar ter que carregar todo o arquivo na memória de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="998ac-152">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="998ac-153">Para esse cenário, você pode usar um <xref:System.IO.FileStream> .</span><span class="sxs-lookup"><span data-stu-id="998ac-153">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="998ac-154">Ao usar o `Utf8JsonReader` para ler de um fluxo, as seguintes regras se aplicam:</span><span class="sxs-lookup"><span data-stu-id="998ac-154">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="998ac-155">O buffer que contém a carga JSON parcial deve ser pelo menos tão grande quanto o maior token JSON dentro dele, de modo que o leitor possa progredir em encaminhar.</span><span class="sxs-lookup"><span data-stu-id="998ac-155">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="998ac-156">O buffer deve ser pelo menos tão grande quanto a maior sequência de espaços em branco dentro do JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-156">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="998ac-157">O leitor não mantém o controle dos dados lidos até que ele leia completamente o próximo <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> na carga JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-157">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="998ac-158">Assim, quando houver bytes restantes no buffer, você precisa passá-los para o leitor novamente.</span><span class="sxs-lookup"><span data-stu-id="998ac-158">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="998ac-159">Você pode usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar quantos bytes serão deixados.</span><span class="sxs-lookup"><span data-stu-id="998ac-159">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="998ac-160">O código a seguir ilustra como ler de um fluxo.</span><span class="sxs-lookup"><span data-stu-id="998ac-160">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="998ac-161">O exemplo mostra um <xref:System.IO.MemoryStream> .</span><span class="sxs-lookup"><span data-stu-id="998ac-161">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="998ac-162">O código semelhante funcionará com um <xref:System.IO.FileStream> , exceto quando o `FileStream` contiver uma bom UTF-8 no início.</span><span class="sxs-lookup"><span data-stu-id="998ac-162">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="998ac-163">Nesse caso, você precisa remover esses três bytes do buffer antes de passar os bytes restantes para o `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="998ac-163">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="998ac-164">Caso contrário, o leitor lançaria uma exceção, uma vez que a BOM não é considerada uma parte válida do JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-164">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="998ac-165">O código de exemplo começa com um buffer de 4 KB e dobra o tamanho do buffer sempre que ele descobre que o tamanho não é grande o suficiente para se ajustar a um token JSON completo, que é necessário para que o leitor faça o progresso no conteúdo JSON.</span><span class="sxs-lookup"><span data-stu-id="998ac-165">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="998ac-166">O exemplo de JSON fornecido no trecho de código dispara um aumento de tamanho de buffer somente se você definir um tamanho de buffer inicial muito pequeno, por exemplo, 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="998ac-166">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="998ac-167">Se você definir o tamanho do buffer inicial como 10, as `Console.WriteLine` instruções ilustrarão a causa e o efeito do tamanho do buffer aumentará.</span><span class="sxs-lookup"><span data-stu-id="998ac-167">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="998ac-168">No tamanho do buffer inicial de 4 KB, o JSON de exemplo inteiro é mostrado por cada um `Console.WriteLine` , e o tamanho do buffer nunca precisa ser aumentado.</span><span class="sxs-lookup"><span data-stu-id="998ac-168">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs":::

<span data-ttu-id="998ac-169">O exemplo anterior não define nenhum limite quanto ao tamanho do buffer pode crescer.</span><span class="sxs-lookup"><span data-stu-id="998ac-169">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="998ac-170">Se o tamanho do token for muito grande, o código poderá falhar com uma <xref:System.OutOfMemoryException> exceção.</span><span class="sxs-lookup"><span data-stu-id="998ac-170">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="998ac-171">Isso pode acontecer se o JSON contiver um token com cerca de 1 GB ou mais de tamanho, porque dobrar o tamanho de 1 GB resulta em um tamanho muito grande para caber em um `int32` buffer.</span><span class="sxs-lookup"><span data-stu-id="998ac-171">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="see-also"></a><span data-ttu-id="998ac-172">Confira também</span><span class="sxs-lookup"><span data-stu-id="998ac-172">See also</span></span>

* [<span data-ttu-id="998ac-173">System.Text.Json sobre</span><span class="sxs-lookup"><span data-stu-id="998ac-173">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="998ac-174">Como personalizar a codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="998ac-174">How to customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="998ac-175">Como escrever conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="998ac-175">How to write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="998ac-176">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="998ac-176">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
