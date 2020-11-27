---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250431"
---
# <a name="mustunderstandbehavior"></a>MustUnderstandBehavior

MustUnderstandBehavior  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Métodos  

 A classe MustUnderstandBehavior não define nenhum método.  
  
## <a name="properties"></a>Propriedades  

 A classe MustUnderstandBehavior tem a seguinte propriedade:  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Tipo de dados: booliano  
  
 Tipo de acesso: Somente leitura  
  
 Quando `true` , todos os cabeçalhos SOAP com o `MustUnderstand` atributo que não são tratados fazem com que o comportamento gere uma exceção.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em ServiceModel. mof.|  
|---------|-----------------------------------|  
|Namespace|Definido em root\ServiceModel|  
  
## <a name="see-also"></a>Confira também

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
