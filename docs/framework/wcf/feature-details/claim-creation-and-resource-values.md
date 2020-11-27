---
title: Valores de recursos e criação de declarações
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: c3f36d607d88b208753066dcbd4e9baa6a2590fa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295126"
---
# <a name="claim-creation-and-resource-values"></a>Valores de recursos e criação de declarações

A <xref:System.IdentityModel.Claims.Claim> classe fornece vários métodos para criar instâncias de tipos de declarações internas. Desses métodos, o seguinte não executa nenhuma verificação semântica ou de formato no recurso fornecido:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (não verifica o comprimento ou o conteúdo da matriz de bytes)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (não verifica o comprimento ou o conteúdo da matriz de bytes)  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 Deve-se ter cuidado ao chamar os métodos acima para garantir que os valores de recurso passados sejam do formato correto ou contenham o tipo correto de informação (ou ambos).  
  
 Os métodos a seguir usam tipos específicos:  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a>Veja também

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Gerenciamento de declarações e autorizações com o modelo de identidade](managing-claims-and-authorization-with-the-identity-model.md)
