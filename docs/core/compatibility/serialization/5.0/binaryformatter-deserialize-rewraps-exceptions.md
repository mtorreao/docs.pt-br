---
title: 'Alteração significativa: BinaryFormatter. desserializar reencapsula algumas exceções'
description: Saiba mais sobre a alteração significativa no .NET 5,0 em que BinaryFormatter. desserializar reencapsula alguns objetos de exceção dentro de uma Serializaexception.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760354"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="56e3d-103">BinaryFormatter. desserializate reencapsula algumas exceções na Serializaexception</span><span class="sxs-lookup"><span data-stu-id="56e3d-103">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="56e3d-104">O <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método agora reencapsula alguns objetos de exceção dentro de um <xref:System.Runtime.Serialization.SerializationException> antes de propagar a exceção de volta para o chamador.</span><span class="sxs-lookup"><span data-stu-id="56e3d-104">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

## <a name="change-description"></a><span data-ttu-id="56e3d-105">Descrição das alterações</span><span class="sxs-lookup"><span data-stu-id="56e3d-105">Change description</span></span>

<span data-ttu-id="56e3d-106">Anteriormente, o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método permitia algumas exceções arbitrárias, como <xref:System.ArgumentNullException> , para propagar a pilha para seus chamadores.</span><span class="sxs-lookup"><span data-stu-id="56e3d-106">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="56e3d-107">No .NET 5,0 e posterior, o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> método captura de forma mais agressiva as exceções que ocorrem devido a operações de desserialização inválidas e as encapsula em um <xref:System.Runtime.Serialization.SerializationException> .</span><span class="sxs-lookup"><span data-stu-id="56e3d-107">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="56e3d-108">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="56e3d-108">Version introduced</span></span>

<span data-ttu-id="56e3d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="56e3d-109">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="56e3d-110">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="56e3d-110">Recommended action</span></span>

<span data-ttu-id="56e3d-111">Na maioria dos casos, você não precisa realizar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="56e3d-111">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="56e3d-112">No entanto, se seu site de chamada depende de uma determinada exceção sendo gerada, você pode desencapsular a exceção da externa <xref:System.Runtime.Serialization.SerializationException> , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="56e3d-112">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a><span data-ttu-id="56e3d-113">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="56e3d-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
