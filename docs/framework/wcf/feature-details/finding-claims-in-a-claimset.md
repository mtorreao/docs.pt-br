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
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="4d1d4-102">Encontrando declarações em um ClaimSet</span><span class="sxs-lookup"><span data-stu-id="4d1d4-102">Finding Claims in a ClaimSet</span></span>

<span data-ttu-id="4d1d4-103">Examinar o conteúdo de um <xref:System.IdentityModel.Claims.ClaimSet> para tipos específicos de declarações é uma tarefa comum ao usar a autorização baseada em declarações.</span><span class="sxs-lookup"><span data-stu-id="4d1d4-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="4d1d4-104">Para examinar um <xref:System.IdentityModel.Claims.ClaimSet> para a presença de declarações específicas, use o <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4d1d4-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="4d1d4-105">Esse método fornece melhor desempenho do que iterar diretamente sobre o <xref:System.IdentityModel.Claims.ClaimSet> .</span><span class="sxs-lookup"><span data-stu-id="4d1d4-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="4d1d4-106">O exemplo a seguir demonstra esse uso.</span><span class="sxs-lookup"><span data-stu-id="4d1d4-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="4d1d4-107">Observe que os `claimType` `claimRight` parâmetros e podem ser `null` .</span><span class="sxs-lookup"><span data-stu-id="4d1d4-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="4d1d4-108">Nesse caso, os parâmetros corresponderão a todos os tipos de declaração e direitos de declaração.</span><span class="sxs-lookup"><span data-stu-id="4d1d4-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d1d4-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4d1d4-109">Example</span></span>  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4d1d4-110">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4d1d4-110">See also</span></span>

- [<span data-ttu-id="4d1d4-111">Gerenciamento de declarações e autorizações com o modelo de identidade</span><span class="sxs-lookup"><span data-stu-id="4d1d4-111">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
