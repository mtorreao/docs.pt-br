---
title: Mapas do Protobuf para dicionários-gRPC para desenvolvedores do WCF
description: Entenda como usar o Protobuf Maps para representar tipos de dicionário no .NET.
ms.date: 12/15/2020
ms.openlocfilehash: d38270d4bc320cf1f758080c18843ed1d716b350
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938540"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="a9354-103">Mapas de Protobuf para dicionários</span><span class="sxs-lookup"><span data-stu-id="a9354-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="a9354-104">É importante poder representar coleções arbitrárias de valores nomeados em mensagens.</span><span class="sxs-lookup"><span data-stu-id="a9354-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="a9354-105">No .NET, essa atividade é comumente manipulada por meio de tipos de dicionário.</span><span class="sxs-lookup"><span data-stu-id="a9354-105">In .NET, this activity is commonly handled through dictionary types.</span></span> <span data-ttu-id="a9354-106">O equivalente do tipo .NET <xref:System.Collections.Generic.IDictionary%602> no buffer de protocolo (Protobuf) é o `map<key_type, value_type>` tipo.</span><span class="sxs-lookup"><span data-stu-id="a9354-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="a9354-107">Esta seção mostra como declarar um `map` tipo em Protobuf e como usar o código gerado.</span><span class="sxs-lookup"><span data-stu-id="a9354-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="a9354-108">No código gerado, os `map` campos são representados por propriedades somente leitura do [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] tipo.</span><span class="sxs-lookup"><span data-stu-id="a9354-108">In the generated code, `map` fields are represented by read-only properties of the [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] type.</span></span> <span data-ttu-id="a9354-109">Esse tipo implementa as interfaces de coleção do .NET padrão, incluindo <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="a9354-109">This type implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="a9354-110">Os campos de mapa não podem ser repetidos diretamente em uma definição de mensagem.</span><span class="sxs-lookup"><span data-stu-id="a9354-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="a9354-111">Mas você pode criar uma mensagem aninhada que contém um mapa e usar `repeated` no tipo de mensagem, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a9354-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="a9354-112">Usando Propriedades MapField no código</span><span class="sxs-lookup"><span data-stu-id="a9354-112">Using MapField properties in code</span></span>

<span data-ttu-id="a9354-113">As `MapField` Propriedades geradas a partir de `map` campos são somente leitura e nunca serão `null` .</span><span class="sxs-lookup"><span data-stu-id="a9354-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="a9354-114">Para definir uma propriedade de mapa, use o `Add(IDictionary<TKey,TValue> values)` método na `MapField` Propriedade Empty para copiar valores de qualquer dicionário .net.</span><span class="sxs-lookup"><span data-stu-id="a9354-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="a9354-115">Leitura adicional</span><span class="sxs-lookup"><span data-stu-id="a9354-115">Further reading</span></span>

<span data-ttu-id="a9354-116">Para obter mais informações sobre o Protobuf, consulte a documentação oficial do [Protobuf](https://developers.google.com/protocol-buffers/docs/overview).</span><span class="sxs-lookup"><span data-stu-id="a9354-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
><span data-ttu-id="a9354-117">[Anterior](protobuf-enums.md) 
> [Avançar](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="a9354-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
