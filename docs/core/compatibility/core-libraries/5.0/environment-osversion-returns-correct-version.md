---
title: 'Alteração significativa: Environment. OSVersion retorna a versão correta do sistema operacional'
description: Saiba mais sobre a alteração significativa do .NET 5,0 em bibliotecas principais do .NET em que Environment. OSVersion retorna a versão real do sistema operacional em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760546"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment. OSVersion retorna a versão correta do sistema operacional

<xref:System.Environment.OSVersion?displayProperty=nameWithType> Retorna a versão real do sistema operacional (SO) em vez de, por exemplo, o sistema operacional selecionado para compatibilidade de aplicativos.

## <a name="change-description"></a>Descrição das alterações

Nas versões anteriores do .NET, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna uma versão do sistema operacional que pode estar incorreta quando um aplicativo é executado no modo de compatibilidade do Windows. Para obter mais informações, consulte [comentários da função GetVersionExA](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).

A partir do .NET 5,0, <xref:System.Environment.OSVersion?displayProperty=nameWithType> retorna a versão real do sistema operacional.

## <a name="reason-for-change"></a>Motivo da alteração

Os usuários dessa propriedade esperam que ele retorne a versão real do sistema operacional. A maioria dos aplicativos .NET não especifica sua versão com suporte no manifesto do aplicativo e, portanto, obtém a versão padrão com suporte do host dotnet. Como resultado, o Shim de compatibilidade raramente é significativo para o aplicativo em execução. Quando o Windows libera uma nova versão e um host dotnet mais antigo ainda está em uso, esses aplicativos podem obter uma versão incorreta do sistema operacional. Retornar a versão real é mais embutido com as expectativas dos desenvolvedores desta API.

## <a name="version-introduced"></a>Versão introduzida

5.0

## <a name="recommended-action"></a>Ação recomendada

Revise e teste qualquer código que use <xref:System.Environment.OSVersion?displayProperty=nameWithType> para garantir que ele se comporta conforme o desejado.

## <a name="affected-apis"></a>APIs afetadas

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
