---
title: Origem do evento BinaryFormatter
description: Saiba como usar a origem do evento BinaryFormatter para registrar quando a serialização ou desserialização estiver ocorrendo.
ms.date: 12/03/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 9ae2af77b6cfc270207fb0f2969ada8c2eca1153
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740413"
---
# <a name="binaryformatter-event-source"></a><span data-ttu-id="d440f-103">Origem do evento BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="d440f-103">BinaryFormatter event source</span></span>

<span data-ttu-id="d440f-104">A partir do .NET 5,0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o inclui um interno <xref:System.Diagnostics.Tracing.EventSource> que fornece visibilidade sobre quando uma serialização ou desserialização de objeto está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="d440f-104">Starting with .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> includes a built-in <xref:System.Diagnostics.Tracing.EventSource> that gives you visibility into when an object serialization or deserialization is occurring.</span></span> <span data-ttu-id="d440f-105">Os aplicativos podem usar <xref:System.Diagnostics.Tracing.EventListener> tipos derivados para escutar essas notificações e fazê-las em log.</span><span class="sxs-lookup"><span data-stu-id="d440f-105">Apps can use <xref:System.Diagnostics.Tracing.EventListener>-derived types to listen for these notifications and log them.</span></span>

<span data-ttu-id="d440f-106">Essa funcionalidade não é um substituto para um <xref:System.Runtime.Serialization.SerializationBinder> ou um <xref:System.Runtime.Serialization.ISerializationSurrogate> e não pode ser usada para modificar os dados que estão sendo serializados ou desserializados.</span><span class="sxs-lookup"><span data-stu-id="d440f-106">This functionality is not a substitute for a <xref:System.Runtime.Serialization.SerializationBinder> or an <xref:System.Runtime.Serialization.ISerializationSurrogate> and can't be used to modify the data being serialized or deserialized.</span></span> <span data-ttu-id="d440f-107">Em vez disso, esse sistema de eventos destina-se a fornecer informações sobre os tipos que estão sendo serializados ou desserializados.</span><span class="sxs-lookup"><span data-stu-id="d440f-107">Rather, this eventing system is intended to provide insight into the types being serialized or deserialized.</span></span> <span data-ttu-id="d440f-108">Ele também pode ser usado para detectar chamadas indesejadas na `BinaryFormatter` infraestrutura, como chamadas provenientes de código de biblioteca de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d440f-108">It can also be used to detect unintended calls into the `BinaryFormatter` infrastructure, such as calls originating from third-party library code.</span></span>

## <a name="description-of-events"></a><span data-ttu-id="d440f-109">Descrição de eventos</span><span class="sxs-lookup"><span data-stu-id="d440f-109">Description of events</span></span>

<span data-ttu-id="d440f-110">A `BinaryFormatter` origem do evento tem o nome conhecido `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource` .</span><span class="sxs-lookup"><span data-stu-id="d440f-110">The `BinaryFormatter` event source has the well-known name `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span></span> <span data-ttu-id="d440f-111">Os ouvintes podem assinar 6 eventos.</span><span class="sxs-lookup"><span data-stu-id="d440f-111">Listeners may subscribe to 6 events.</span></span>

### <a name="serializationstart-event-id--10"></a><span data-ttu-id="d440f-112">Evento SerializationStart (ID = `10` )</span><span class="sxs-lookup"><span data-stu-id="d440f-112">SerializationStart event (id = `10`)</span></span>

<span data-ttu-id="d440f-113">Gerado quando foi <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> chamado e iniciou o processo de serialização.</span><span class="sxs-lookup"><span data-stu-id="d440f-113">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> has been called and has started the serialization process.</span></span> <span data-ttu-id="d440f-114">Esse evento é emparelhado com o `SerializationEnd` evento.</span><span class="sxs-lookup"><span data-stu-id="d440f-114">This event is paired with the `SerializationEnd` event.</span></span> <span data-ttu-id="d440f-115">O `SerializationStart` evento pode ser chamado recursivamente se um objeto chamar `BinaryFormatter.Serialize` em sua própria rotina de serialização.</span><span class="sxs-lookup"><span data-stu-id="d440f-115">The `SerializationStart` event can be called recursively if an object calls `BinaryFormatter.Serialize` within its own serialization routine.</span></span>

<span data-ttu-id="d440f-116">Esse evento não contém uma carga.</span><span class="sxs-lookup"><span data-stu-id="d440f-116">This event doesn't contain a payload.</span></span>

### <a name="serializationend-event-id--11"></a><span data-ttu-id="d440f-117">Evento SerializationEnd (ID = `11` )</span><span class="sxs-lookup"><span data-stu-id="d440f-117">SerializationEnd event (id = `11`)</span></span>

<span data-ttu-id="d440f-118">Gerado quando `BinaryFormatter.Serialize` concluiu seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="d440f-118">Raised when `BinaryFormatter.Serialize` has completed its work.</span></span> <span data-ttu-id="d440f-119">Cada ocorrência de `SerializationEnd` denota a conclusão do último evento não emparelhado `SerializationStart` .</span><span class="sxs-lookup"><span data-stu-id="d440f-119">Each occurrence of `SerializationEnd` denotes the completion of the last unpaired `SerializationStart` event.</span></span>

<span data-ttu-id="d440f-120">Esse evento não contém uma carga.</span><span class="sxs-lookup"><span data-stu-id="d440f-120">This event doesn't contain a payload.</span></span>

### <a name="serializingobject-event-id--12"></a><span data-ttu-id="d440f-121">Evento serializaobject (ID = `12` )</span><span class="sxs-lookup"><span data-stu-id="d440f-121">SerializingObject event (id = `12`)</span></span>

<span data-ttu-id="d440f-122">Gerado quando `BinaryFormatter.Serialize` está no processo de serialização de um tipo não primitivo.</span><span class="sxs-lookup"><span data-stu-id="d440f-122">Raised when `BinaryFormatter.Serialize` is in the process of serializing a non-primitive type.</span></span> <span data-ttu-id="d440f-123">A `BinaryFormatter` infraestrutura faz casos especiais determinados tipos (como `string` e `int` ) e não gera esse evento quando esses tipos são encontrados.</span><span class="sxs-lookup"><span data-stu-id="d440f-123">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="d440f-124">Esse evento é gerado para tipos definidos pelo usuário e outros tipos que `BinaryFormatter` não compreendem nativamente.</span><span class="sxs-lookup"><span data-stu-id="d440f-124">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="d440f-125">Esse evento pode ser gerado zero ou mais vezes entre `SerializationStart` `SerializationEnd` eventos e.</span><span class="sxs-lookup"><span data-stu-id="d440f-125">This event may be raised zero or more times between `SerializationStart` and `SerializationEnd` events.</span></span>

<span data-ttu-id="d440f-126">Esse evento contém uma carga com um argumento:</span><span class="sxs-lookup"><span data-stu-id="d440f-126">This event contains a payload with one argument:</span></span>

* <span data-ttu-id="d440f-127">`typeName` ( `string` ): O nome qualificado do assembly (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> ) do tipo que está sendo serializado.</span><span class="sxs-lookup"><span data-stu-id="d440f-127">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being serialized.</span></span>

### <a name="deserializationstart-event-id--20"></a><span data-ttu-id="d440f-128">Evento DeserializationStart (ID = `20` )</span><span class="sxs-lookup"><span data-stu-id="d440f-128">DeserializationStart event (id = `20`)</span></span>

<span data-ttu-id="d440f-129">Gerado quando foi <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> chamado e iniciou o processo de desserialização.</span><span class="sxs-lookup"><span data-stu-id="d440f-129">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> has been called and has started the deserialization process.</span></span> <span data-ttu-id="d440f-130">Esse evento é emparelhado com o `DeserializationEnd` evento.</span><span class="sxs-lookup"><span data-stu-id="d440f-130">This event is paired with the `DeserializationEnd` event.</span></span> <span data-ttu-id="d440f-131">O `DeserializationStart` evento pode ser chamado recursivamente se um objeto chamar `BinaryFormatter.Deserialize` em sua própria rotina de desserialização.</span><span class="sxs-lookup"><span data-stu-id="d440f-131">The `DeserializationStart` event can be called recursively if an object calls `BinaryFormatter.Deserialize` within its own deserialization routine.</span></span>

<span data-ttu-id="d440f-132">Esse evento não contém uma carga.</span><span class="sxs-lookup"><span data-stu-id="d440f-132">This event doesn't contain a payload.</span></span>

### <a name="deserializationend-event-id--21"></a><span data-ttu-id="d440f-133">Evento DeserializationEnd (ID = `21` )</span><span class="sxs-lookup"><span data-stu-id="d440f-133">DeserializationEnd event (id = `21`)</span></span>

<span data-ttu-id="d440f-134">Gerado quando `BinaryFormatter.Deserialize` concluiu seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="d440f-134">Raised when `BinaryFormatter.Deserialize` has completed its work.</span></span> <span data-ttu-id="d440f-135">Cada ocorrência de `DeserializationEnd` denota a conclusão do último evento não emparelhado `DeserializationStart` .</span><span class="sxs-lookup"><span data-stu-id="d440f-135">Each occurrence of `DeserializationEnd` denotes the completion of the last unpaired `DeserializationStart` event.</span></span>

<span data-ttu-id="d440f-136">Esse evento não contém uma carga.</span><span class="sxs-lookup"><span data-stu-id="d440f-136">This event doesn't contain a payload.</span></span>

### <a name="deserializingobject-event-id--22"></a><span data-ttu-id="d440f-137">Evento deserializaobject (ID = `22` )</span><span class="sxs-lookup"><span data-stu-id="d440f-137">DeserializingObject event (id = `22`)</span></span>

<span data-ttu-id="d440f-138">Gerado quando `BinaryFormatter.Deserialize` está no processo de desserializar um tipo não primitivo.</span><span class="sxs-lookup"><span data-stu-id="d440f-138">Raised when `BinaryFormatter.Deserialize` is in the process of deserializing a non-primitive type.</span></span> <span data-ttu-id="d440f-139">A `BinaryFormatter` infraestrutura faz casos especiais determinados tipos (como `string` e `int` ) e não gera esse evento quando esses tipos são encontrados.</span><span class="sxs-lookup"><span data-stu-id="d440f-139">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="d440f-140">Esse evento é gerado para tipos definidos pelo usuário e outros tipos que `BinaryFormatter` não compreendem nativamente.</span><span class="sxs-lookup"><span data-stu-id="d440f-140">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="d440f-141">Esse evento pode ser gerado zero ou mais vezes entre `DeserializationStart` `DeserializationEnd` eventos e.</span><span class="sxs-lookup"><span data-stu-id="d440f-141">This event may be raised zero or more times between `DeserializationStart` and `DeserializationEnd` events.</span></span>

<span data-ttu-id="d440f-142">Esse evento contém uma carga com um argumento.</span><span class="sxs-lookup"><span data-stu-id="d440f-142">This event contains a payload with one argument.</span></span>

* <span data-ttu-id="d440f-143">`typeName` ( `string` ): O nome qualificado do assembly (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> ) do tipo que está sendo desserializado.</span><span class="sxs-lookup"><span data-stu-id="d440f-143">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being deserialized.</span></span>

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a><span data-ttu-id="d440f-144">\[Assinatura avançada de \] um subconjunto de notificações</span><span class="sxs-lookup"><span data-stu-id="d440f-144">\[Advanced\] Subscribing to a subset of notifications</span></span>

<span data-ttu-id="d440f-145">Os ouvintes que desejam assinar apenas um subconjunto de notificações podem escolher quais palavras-chave habilitar.</span><span class="sxs-lookup"><span data-stu-id="d440f-145">Listeners who wish to subscribe to only a subset of notifications can choose which keywords to enable.</span></span>

* <span data-ttu-id="d440f-146">`Serialization` = `(EventKeywords)1`: Gera os `SerializationStart` `SerializationEnd` eventos, e `SerializingObject` .</span><span class="sxs-lookup"><span data-stu-id="d440f-146">`Serialization` = `(EventKeywords)1`: Raises the `SerializationStart`, `SerializationEnd`, and `SerializingObject` events.</span></span>
* <span data-ttu-id="d440f-147">`Deserialization` = `(EventKeywords)2`: Gera os `DeserializationStart` `DeserializationEnd` eventos, e `DeserializingObject` .</span><span class="sxs-lookup"><span data-stu-id="d440f-147">`Deserialization` = `(EventKeywords)2`: Raises the `DeserializationStart`, `DeserializationEnd`, and `DeserializingObject` events.</span></span>

<span data-ttu-id="d440f-148">Se nenhum filtro de palavra-chave for fornecido durante o `EventListener` registro, todos os eventos serão gerados.</span><span class="sxs-lookup"><span data-stu-id="d440f-148">If no keyword filters are provided during `EventListener` registration, all events are raised.</span></span>

<span data-ttu-id="d440f-149">Para obter mais informações, consulte <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d440f-149">For more information, see <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span></span>

## <a name="sample-code"></a><span data-ttu-id="d440f-150">Código de exemplo</span><span class="sxs-lookup"><span data-stu-id="d440f-150">Sample code</span></span>

<span data-ttu-id="d440f-151">O seguinte código:</span><span class="sxs-lookup"><span data-stu-id="d440f-151">The following code:</span></span>

- <span data-ttu-id="d440f-152">Cria um `EventListener` tipo derivado que grava em `System.Console` ,</span><span class="sxs-lookup"><span data-stu-id="d440f-152">creates an `EventListener`-derived type that writes to `System.Console`,</span></span>
- <span data-ttu-id="d440f-153">assina esse ouvinte para `BinaryFormatter` notificações produzidas,</span><span class="sxs-lookup"><span data-stu-id="d440f-153">subscribes that listener to `BinaryFormatter`-produced notifications,</span></span>
- <span data-ttu-id="d440f-154">Serializa e desserializa um grafo de objeto simples usando `BinaryFormatter` , e</span><span class="sxs-lookup"><span data-stu-id="d440f-154">serializes and deserializes a simple object graph using `BinaryFormatter`, and</span></span>
- <span data-ttu-id="d440f-155">analisa os eventos que foram gerados.</span><span class="sxs-lookup"><span data-stu-id="d440f-155">analyzes the events that have been raised.</span></span>

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

<span data-ttu-id="d440f-156">O código anterior produz uma saída semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d440f-156">The preceding code produces output similar to the following example:</span></span>

```output
Event SerializationStart (id=10) received.
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializationStop (id=11) received.
Event DeserializationStart (id=20) received.
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializationStop (id=21) received.
Rehydrated person Logan Edwards
Favorite book: A Tale of Two Cities by Charles Dickens, list price 10.25
```

<span data-ttu-id="d440f-157">Neste exemplo, os logs baseados em console `EventListener` que a serialização inicia, instâncias de `Person` e `Book` são serializados e, em seguida, a serialização é concluída.</span><span class="sxs-lookup"><span data-stu-id="d440f-157">In this sample, the console-based `EventListener` logs that serialization starts, instances of `Person` and `Book` are serialized, and then serialization completes.</span></span> <span data-ttu-id="d440f-158">Da mesma forma, quando a desserialização é iniciada, as instâncias de `Person` e `Book` são desserializadas e a desserialização é concluída.</span><span class="sxs-lookup"><span data-stu-id="d440f-158">Similarly, once deserialization has started, instances of `Person` and `Book` are deserialized, and then deserialization completes.</span></span>

<span data-ttu-id="d440f-159">Em seguida, o aplicativo imprime os valores contidos em desserializados `Person` para demonstrar que o objeto fazia serialização e desserialização apropriada.</span><span class="sxs-lookup"><span data-stu-id="d440f-159">The app then prints the values contained in the deserialized `Person` to demonstrate that the object did in fact serialize and deserialize properly.</span></span>

## <a name="see-also"></a><span data-ttu-id="d440f-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="d440f-160">See also</span></span>

<span data-ttu-id="d440f-161">Para obter mais informações sobre `EventListener` como usar para `EventSource` notificações baseadas em recebimento, consulte [a `EventListener` classe](xref:System.Diagnostics.Tracing.EventListener).</span><span class="sxs-lookup"><span data-stu-id="d440f-161">For more information on using `EventListener` to receive `EventSource`-based notifications, see [the `EventListener` class](xref:System.Diagnostics.Tracing.EventListener).</span></span>
