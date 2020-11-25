---
title: Estrutura CALL_ID
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725242"
---
# <a name="call_id-structure"></a>Estrutura CALL_ID

Fornece informações para um depurador sobre uma função que está sendo chamada. Consulte a interface [INotifySink2](inotifysink2-interface.md) para obter mais informações.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Membros  
  
|Membro|DESCRIÇÃO|  
|------------|-----------------|  
|`szMachine`|Identifica o computador que está fazendo a chamada.|  
|`dwPid`|Identifica o processador do computador.|  
|`pUserThread`|Identifica o thread que está executando a chamada.|  
|`addrStackPointer`|Especifica o endereço da pilha de chamadas.|  
|`szEntryPoint`|Especifica o endereço da chamada.|  
|`szDestinationMachine`|Identifica o computador que executará a chamada.|  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Confira também

- [Interface INotifySink2](inotifysink2-interface.md)
- [Estruturas de armazenamento de símbolo de diagnóstico](diagnostics-symbol-store-structures.md)
