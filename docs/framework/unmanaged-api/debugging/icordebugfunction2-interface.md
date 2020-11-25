---
title: Interface ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: d9e84a70d72db1338c80140ce3350774bfae4bca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726269"
---
# <a name="icordebugfunction2-interface"></a>Interface ICorDebugFunction2

Estende logicamente a interface ICorDebugFunction para fornecer suporte para depuração passo a Apenas Meu Código, que ignora o código que não é do usuário.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método EnumerateNativeCode](icordebugfunction2-enumeratenativecode-method.md)|(Ainda não implementado.) Obtém um ponteiro de interface para um ICorDebugCodeEnum que contém as instruções de código nativo na função referenciada por este objeto ICorDebugFunction2.|  
|[Método GetJMCStatus](icordebugfunction2-getjmcstatus-method.md)|Obtém um valor que indica se esta função está marcada como código de usuário.|  
|[Método GetVersionNumber](icordebugfunction2-getversionnumber-method.md)|Obtém a versão editar e continuar desta função.|  
|[Método SetJMCStatus](icordebugfunction2-setjmcstatus-method.md)|Marca essa função para Apenas Meu Código stepping.|  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
