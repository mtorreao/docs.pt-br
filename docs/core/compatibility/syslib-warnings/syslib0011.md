---
title: Aviso de SYSLIB0011
description: Saiba mais sobre o obsoletions que gera SYSLIB0011 de aviso de tempo de compilação.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 36292cc5314e2b7677d705780880b7e25ae0dfb6
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596439"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a>SYSLIB0011: a serialização BinaryFormatter está obsoleta

Devido a [vulnerabilidades de segurança](../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) no <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> , as seguintes APIs são marcadas como obsoletas, a partir do .NET 5,0. Usá-los no código gera aviso `SYSLIB0011` no momento da compilação.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a>Soluções Alternativas

Considere usar <xref:System.Text.Json.JsonSerializer> ou <xref:System.Xml.Serialization.XmlSerializer> em vez de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> .

Para obter mais informações sobre as ações recomendadas, consulte [Resolvendo erros de BinaryFormatter obsoletion e de desativação](https://aka.ms/binaryformatter).

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Confira também

- [Resolvendo erros de desativação e BinaryFormatter obsoletion](https://aka.ms/binaryformatter)
- [Os métodos de serialização BinaryFormatter são obsoletos e proibidos em aplicativos ASP.NET](../core-libraries/5.0/binaryformatter-serialization-obsolete.md)
