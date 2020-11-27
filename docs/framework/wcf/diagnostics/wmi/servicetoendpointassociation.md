---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273939"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation

Mapeia um serviço para um ponto de extremidade.  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe ServiceToEndpointAssociation não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe ServiceToEndpointAssociation tem as seguintes propriedades:  
  
### <a name="ref"></a>ref  

 Tipo de dados: serviço  
  
 Tipo de acesso: Somente leitura  
Qualificadores: Chave  
  
 O serviço associado ao ponto de extremidade.  
  
### <a name="ref"></a>ref  

 Tipo de dados: ponto de extremidade  
  
 Tipo de acesso: Somente leitura  
Qualificadores: Chave  
  
 O ponto de extremidade associado ao serviço.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|
