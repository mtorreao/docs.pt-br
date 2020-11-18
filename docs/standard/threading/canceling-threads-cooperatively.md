---
title: Cancelando threads de forma cooperativa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 9e9224e9dc9ac57defe75e916dd6b9844bba7f12
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826606"
---
# <a name="canceling-threads-cooperatively"></a>Cancelando threads de forma cooperativa

Antes do .NET Framework 4, o .NET não fornecia uma maneira interna de cancelar um thread de forma cooperativa depois que ele foi iniciado. No entanto, a partir do .NET Framework 4, você pode usar um <xref:System.Threading.CancellationToken?displayProperty=nameWithType> para cancelar threads, assim como você pode usá-los para cancelar <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos ou Consultas PLINQ. Embora a classe <xref:System.Threading.Thread?displayProperty=nameWithType> não ofereça suporte interno para tokens de cancelamento, você pode passar um token para um procedimento de thread usando o constructo <xref:System.Threading.Thread> que usa um representante <xref:System.Threading.ParameterizedThreadStart>. O exemplo a seguir demonstra como fazer isso.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Confira também

- [Usando threads e threading](using-threads-and-threading.md)
