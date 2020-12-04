---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96584637"
---
- <span data-ttu-id="fec38-101">Se possível, use um serializador seguro em vez disso e **não permita que um invasor especifique um tipo arbitrário para desserializar**.</span><span class="sxs-lookup"><span data-stu-id="fec38-101">If possible, use a secure serializer instead, and **don't allow an attacker to specify an arbitrary type to deserialize**.</span></span> <span data-ttu-id="fec38-102">Alguns serializadores mais seguros incluem:</span><span class="sxs-lookup"><span data-stu-id="fec38-102">Some safer serializers include:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="fec38-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nunca use <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fec38-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> - Never use <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fec38-104">Se você precisar usar um resolvedor de tipo, restrinja os tipos desserializados a uma lista esperada.</span><span class="sxs-lookup"><span data-stu-id="fec38-104">If you must use a type resolver, restrict deserialized types to an expected list.</span></span>
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="fec38-105">Newtonsoft Json.NET-use TypeNameHandling. None.</span><span class="sxs-lookup"><span data-stu-id="fec38-105">Newtonsoft Json.NET - Use TypeNameHandling.None.</span></span> <span data-ttu-id="fec38-106">Se você precisar usar outro valor para TypeNameHandling, restrinja os tipos desserializados a uma lista esperada com um ISerializationBinder personalizado.</span><span class="sxs-lookup"><span data-stu-id="fec38-106">If you must use another value for TypeNameHandling, restrict deserialized types to an expected list with a custom ISerializationBinder.</span></span>
  - <span data-ttu-id="fec38-107">Buffers de protocolo</span><span class="sxs-lookup"><span data-stu-id="fec38-107">Protocol Buffers</span></span>

- <span data-ttu-id="fec38-108">Torne a prova de adulteração dos dados serializados.</span><span class="sxs-lookup"><span data-stu-id="fec38-108">Make the serialized data tamper-proof.</span></span> <span data-ttu-id="fec38-109">Após a serialização, assine criptograficamente os dados serializados.</span><span class="sxs-lookup"><span data-stu-id="fec38-109">After serialization, cryptographically sign the serialized data.</span></span> <span data-ttu-id="fec38-110">Antes da desserialização, valide a assinatura criptográfica.</span><span class="sxs-lookup"><span data-stu-id="fec38-110">Before deserialization, validate the cryptographic signature.</span></span> <span data-ttu-id="fec38-111">Proteja a chave de criptografia de ser divulgada e design para rotações de chave.</span><span class="sxs-lookup"><span data-stu-id="fec38-111">Protect the cryptographic key from being disclosed and design for key rotations.</span></span>
