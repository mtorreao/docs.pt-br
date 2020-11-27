---
title: Retornos de chamada de serialização tolerantes à versão
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: ad162f24042f30eabee7a1fad2025072b26d9af5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289367"
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="1840a-102">Retornos de chamada de serialização tolerantes à versão</span><span class="sxs-lookup"><span data-stu-id="1840a-102">Version-Tolerant Serialization Callbacks</span></span>

<span data-ttu-id="1840a-103">O modelo de programação de contrato de dados dá suporte total aos métodos de retorno de chamada de serialização tolerantes à versão que as <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes e dão suporte.</span><span class="sxs-lookup"><span data-stu-id="1840a-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="1840a-104">Atributos de Version-Tolerant</span><span class="sxs-lookup"><span data-stu-id="1840a-104">Version-Tolerant Attributes</span></span>  

 <span data-ttu-id="1840a-105">Há quatro atributos de retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="1840a-105">There are four callback attributes.</span></span> <span data-ttu-id="1840a-106">Cada atributo pode ser aplicado a um método que o mecanismo de serialização/desserialização chama em vários momentos.</span><span class="sxs-lookup"><span data-stu-id="1840a-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="1840a-107">A tabela a seguir explica quando usar cada atributo.</span><span class="sxs-lookup"><span data-stu-id="1840a-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="1840a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1840a-108">Attribute</span></span>|<span data-ttu-id="1840a-109">Quando o método correspondente é chamado</span><span class="sxs-lookup"><span data-stu-id="1840a-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="1840a-110">Chamado antes de serializar o tipo.</span><span class="sxs-lookup"><span data-stu-id="1840a-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="1840a-111">Chamado após a serialização do tipo.</span><span class="sxs-lookup"><span data-stu-id="1840a-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="1840a-112">Chamado antes de desserializar o tipo.</span><span class="sxs-lookup"><span data-stu-id="1840a-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="1840a-113">Chamado após a desserialização do tipo.</span><span class="sxs-lookup"><span data-stu-id="1840a-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="1840a-114">Os métodos devem aceitar um <xref:System.Runtime.Serialization.StreamingContext> parâmetro.</span><span class="sxs-lookup"><span data-stu-id="1840a-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="1840a-115">Esses métodos se destinam principalmente ao uso com controle de versão ou inicialização.</span><span class="sxs-lookup"><span data-stu-id="1840a-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="1840a-116">Durante a desserialização, nenhum construtor é chamado.</span><span class="sxs-lookup"><span data-stu-id="1840a-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="1840a-117">Portanto, os membros de dados podem não ser inicializados corretamente (para valores padrão pretendidos) se os dados desses membros estiverem ausentes no fluxo de entrada, por exemplo, se os dados vierem de uma versão anterior de um tipo que não tem alguns membros de dados.</span><span class="sxs-lookup"><span data-stu-id="1840a-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="1840a-118">Para corrigir isso, use o método de retorno de chamada marcado com o <xref:System.Runtime.Serialization.OnDeserializingAttribute> , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1840a-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="1840a-119">Você pode marcar apenas um método por tipo com cada um dos atributos de retorno de chamada anteriores.</span><span class="sxs-lookup"><span data-stu-id="1840a-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1840a-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1840a-120">Example</span></span>  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="1840a-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1840a-121">See also</span></span>

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [<span data-ttu-id="1840a-122">Serialização tolerante a versão</span><span class="sxs-lookup"><span data-stu-id="1840a-122">Version Tolerant Serialization</span></span>](../../../standard/serialization/version-tolerant-serialization.md)
