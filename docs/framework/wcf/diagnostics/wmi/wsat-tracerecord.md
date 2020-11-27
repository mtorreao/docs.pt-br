---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262210"
---
# <a name="wsat_tracerecord"></a>WSAT_TraceRecord

WSAT_TraceRecord  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe WSAT_TraceRecord não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe WSAT_TraceRecord tem as seguintes propriedades:  
  
### <a name="activityid"></a>ActivityID  

 Tipo de dados: objeto  
Tipo de acesso: Somente leitura  
  
 A ID da atividade do registro de rastreamento.  
  
### <a name="eventid"></a>EventID  

 Tipo de dados: sint32  
Tipo de acesso: Somente leitura  
  
 A ID de evento do registro de rastreamento.  
  
### <a name="tracerecord"></a>TraceRecord  

 Tipo de dados: cadeia de caracteres  
Tipo de acesso: Somente leitura  
  
 Registro de rastreamento  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|
