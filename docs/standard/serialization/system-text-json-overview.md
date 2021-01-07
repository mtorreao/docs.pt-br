---
title: Serializar e desserializar JSON usando C#-.NET
description: Esta visão geral descreve a System.Text.Json funcionalidade de namespace para serialização e desserialização do JSON no .net.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: b4432e7a137720216e7c0941b3384ce7ad7049e9
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970909"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="29643-103">Serialização e desserialização JSON (empacotamento e desempacotamento) no .NET-visão geral</span><span class="sxs-lookup"><span data-stu-id="29643-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="29643-104">O `System.Text.Json` namespace fornece a funcionalidade para serializar e desserializar de JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="29643-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="29643-105">O design da biblioteca enfatiza o alto desempenho e a baixa alocação de memória em um amplo conjunto de recursos.</span><span class="sxs-lookup"><span data-stu-id="29643-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="29643-106">O suporte interno a UTF-8 otimiza o processo de leitura e gravação de texto JSON codificado como UTF-8, que é a codificação mais predominante para os dados na Web e nos arquivos no disco.</span><span class="sxs-lookup"><span data-stu-id="29643-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="29643-107">A biblioteca também fornece classes para trabalhar com um modelo de objeto de documento (DOM) na memória.</span><span class="sxs-lookup"><span data-stu-id="29643-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="29643-108">Esse recurso permite o acesso aleatório somente leitura dos elementos em um arquivo JSON ou cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="29643-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="29643-109">Como obter a biblioteca</span><span class="sxs-lookup"><span data-stu-id="29643-109">How to get the library</span></span>

* <span data-ttu-id="29643-110">A biblioteca é interna como parte da estrutura compartilhada para .NET Core 3,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="29643-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="29643-111">Para versões anteriores do Framework, instale o [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="29643-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="29643-112">O pacote dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="29643-112">The package supports:</span></span>

  * <span data-ttu-id="29643-113">.NET Standard 2,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="29643-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="29643-114">.NET Framework 4.7.2 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="29643-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="29643-115">.NET Core 2,0, 2,1 e 2,2</span><span class="sxs-lookup"><span data-stu-id="29643-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29643-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="29643-116">Additional resources</span></span>

* [<span data-ttu-id="29643-117">Como usar a biblioteca</span><span class="sxs-lookup"><span data-stu-id="29643-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="29643-118">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="29643-118">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="29643-119">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="29643-119">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="29643-120">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="29643-120">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="29643-121">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="29643-121">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="29643-122">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="29643-122">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="29643-123">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="29643-123">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="29643-124">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="29643-124">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="29643-125">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="29643-125">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="29643-126">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="29643-126">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="29643-127">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="29643-127">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="29643-128">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="29643-128">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="29643-129">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="29643-129">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="29643-130">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="29643-130">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="29643-131">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="29643-131">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="29643-132">Tipos de coleção com suporte no System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="29643-132">Supported collection types in System.Text.Json</span></span>](system-text-json-supported-collection-types.md)
* <span data-ttu-id="29643-133">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="29643-133">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="29643-134">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="29643-134">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
