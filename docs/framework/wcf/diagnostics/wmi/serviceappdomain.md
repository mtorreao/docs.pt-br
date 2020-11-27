---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 243c9112dd9caf5c92ef77aa0f45b4b1e71a4e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273250"
---
# <a name="serviceappdomain"></a>ServiceAppDomain

Mapeia um serviço para um domínio de aplicativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe imappdomain não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe imappdomain tem as seguintes propriedades:  
  
### <a name="ref"></a>ref  

 Tipo de dados: serviço  
Qualificadores: Chave  
  
 Tipo de acesso: Somente leitura  
  
 O serviço deste domínio de aplicativo.  
  
### <a name="ref"></a>ref  

 Tipo de dados: AppDomainInfo  
Qualificadores: Chave  
  
 Tipo de acesso: Somente leitura  
  
 Contém as propriedades do domínio do aplicativo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|
