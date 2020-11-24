---
title: Aviso de SYSLIB0011
description: Saiba mais sobre o obsoletions que gera SYSLIB0011 de aviso de tempo de compilação.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 99cdd9f5335f71eb9325039891db17972fb48532
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685000"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="c49b1-103">SYSLIB0011: a serialização BinaryFormatter está obsoleta</span><span class="sxs-lookup"><span data-stu-id="c49b1-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="c49b1-104">Devido a [vulnerabilidades de segurança](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) no <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , as seguintes APIs são marcadas como obsoletas, a partir do .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="c49b1-104">Due to [security vulnerabilities](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="c49b1-105">Usá-los no código gera aviso `SYSLIB0011` no momento da compilação.</span><span class="sxs-lookup"><span data-stu-id="c49b1-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="c49b1-106">Soluções Alternativas</span><span class="sxs-lookup"><span data-stu-id="c49b1-106">Workarounds</span></span>

<span data-ttu-id="c49b1-107">Considere usar <xref:System.Text.Json.JsonSerializer> ou <xref:System.Xml.Serialization.XmlSerializer> em vez de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> .</span><span class="sxs-lookup"><span data-stu-id="c49b1-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="c49b1-108">Para obter mais informações sobre as ações recomendadas, consulte [Resolvendo erros de BinaryFormatter obsoletion e de desativação](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="c49b1-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="c49b1-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="c49b1-109">See also</span></span>

- [<span data-ttu-id="c49b1-110">Resolvendo erros de desativação e BinaryFormatter obsoletion</span><span class="sxs-lookup"><span data-stu-id="c49b1-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](https://aka.ms/binaryformatter)
- [<span data-ttu-id="c49b1-111">Os métodos de serialização BinaryFormatter são obsoletos e proibidos em aplicativos ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c49b1-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](core-libraries/5.0/binaryformatter-serialization-obsolete.md)
