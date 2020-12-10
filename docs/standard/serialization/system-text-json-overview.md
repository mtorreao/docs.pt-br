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
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009879"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a><span data-ttu-id="122e2-103">Serialização e desserialização JSON (empacotamento e desempacotamento) no .NET-visão geral</span><span class="sxs-lookup"><span data-stu-id="122e2-103">JSON serialization and deserialization (marshalling and unmarshalling) in .NET - overview</span></span>

<span data-ttu-id="122e2-104">O `System.Text.Json` namespace fornece a funcionalidade para serializar e desserializar de JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="122e2-104">The `System.Text.Json` namespace provides functionality for serializing to and deserializing from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="122e2-105">O design da biblioteca enfatiza o alto desempenho e a baixa alocação de memória em um amplo conjunto de recursos.</span><span class="sxs-lookup"><span data-stu-id="122e2-105">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="122e2-106">O suporte interno a UTF-8 otimiza o processo de leitura e gravação de texto JSON codificado como UTF-8, que é a codificação mais predominante para os dados na Web e nos arquivos no disco.</span><span class="sxs-lookup"><span data-stu-id="122e2-106">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="122e2-107">A biblioteca também fornece classes para trabalhar com um modelo de objeto de documento (DOM) na memória.</span><span class="sxs-lookup"><span data-stu-id="122e2-107">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="122e2-108">Esse recurso permite o acesso aleatório somente leitura dos elementos em um arquivo JSON ou cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="122e2-108">This feature enables random read-only access of the elements in a JSON file or string.</span></span>

## <a name="how-to-get-the-library"></a><span data-ttu-id="122e2-109">Como obter a biblioteca</span><span class="sxs-lookup"><span data-stu-id="122e2-109">How to get the library</span></span>

* <span data-ttu-id="122e2-110">A biblioteca é interna como parte da estrutura compartilhada para .NET Core 3,0 e versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="122e2-110">The library is built-in as part of the shared framework for .NET Core 3.0 and later versions.</span></span>
* <span data-ttu-id="122e2-111">Para versões anteriores do Framework, instale o [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="122e2-111">For earlier framework versions, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="122e2-112">O pacote dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="122e2-112">The package supports:</span></span>

  * <span data-ttu-id="122e2-113">.NET Standard 2,0 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="122e2-113">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="122e2-114">.NET Framework 4.7.2 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="122e2-114">.NET Framework 4.7.2 and later versions</span></span>
  * <span data-ttu-id="122e2-115">.NET Core 2,0, 2,1 e 2,2</span><span class="sxs-lookup"><span data-stu-id="122e2-115">.NET Core 2.0, 2.1, and 2.2</span></span>

## <a name="additional-resources"></a><span data-ttu-id="122e2-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="122e2-116">Additional resources</span></span>

* [<span data-ttu-id="122e2-117">Como usar a biblioteca</span><span class="sxs-lookup"><span data-stu-id="122e2-117">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="122e2-118">Instanciar instâncias JsonSerializerOptions</span><span class="sxs-lookup"><span data-stu-id="122e2-118">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="122e2-119">Habilitar a correspondência sem diferenciação de maiúsculas e minúsculas</span><span class="sxs-lookup"><span data-stu-id="122e2-119">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="122e2-120">Personalizar nomes e valores da propriedade</span><span class="sxs-lookup"><span data-stu-id="122e2-120">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="122e2-121">Ignorar propriedades</span><span class="sxs-lookup"><span data-stu-id="122e2-121">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="122e2-122">Permitir JSON inválido</span><span class="sxs-lookup"><span data-stu-id="122e2-122">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="122e2-123">Manipular JSON de estouro</span><span class="sxs-lookup"><span data-stu-id="122e2-123">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="122e2-124">Preservar referências</span><span class="sxs-lookup"><span data-stu-id="122e2-124">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="122e2-125">Tipos imutáveis e acessadores não públicos</span><span class="sxs-lookup"><span data-stu-id="122e2-125">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="122e2-126">Serialização polimórfica</span><span class="sxs-lookup"><span data-stu-id="122e2-126">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="122e2-127">Migrar do Newtonsoft.Json para o System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="122e2-127">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="122e2-128">Personalizar codificação de caracteres</span><span class="sxs-lookup"><span data-stu-id="122e2-128">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="122e2-129">Escrever serializadores personalizados e desserializadores</span><span class="sxs-lookup"><span data-stu-id="122e2-129">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="122e2-130">Gravar conversores personalizados para serialização JSON</span><span class="sxs-lookup"><span data-stu-id="122e2-130">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="122e2-131">Suporte a DateTime e DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="122e2-131">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="122e2-132">[System.Text.Json Referência de API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="122e2-132">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="122e2-133">[System.Text.Json. Referência de API de serialização](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="122e2-133">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
