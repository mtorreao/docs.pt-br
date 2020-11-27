---
title: Encontrando declarações em um ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: c43a47b32a2a3c15d1a51b8b6931ebb021722a64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268450"
---
# <a name="finding-claims-in-a-claimset"></a>Encontrando declarações em um ClaimSet

Examinar o conteúdo de um <xref:System.IdentityModel.Claims.ClaimSet> para tipos específicos de declarações é uma tarefa comum ao usar a autorização baseada em declarações. Para examinar um <xref:System.IdentityModel.Claims.ClaimSet> para a presença de declarações específicas, use o <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> método. Esse método fornece melhor desempenho do que iterar diretamente sobre o <xref:System.IdentityModel.Claims.ClaimSet> . O exemplo a seguir demonstra esse uso. Observe que os `claimType` `claimRight` parâmetros e podem ser `null` . Nesse caso, os parâmetros corresponderão a todos os tipos de declaração e direitos de declaração.  
  
## <a name="example"></a>Exemplo  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a>Consulte também

- [Gerenciamento de declarações e autorizações com o modelo de identidade](managing-claims-and-authorization-with-the-identity-model.md)
