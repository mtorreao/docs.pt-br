---
title: Função FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: 7aa90b92d129f1269d901f1cbb5c6a0750de9a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728531"
---
# <a name="functionidmapper2-function"></a>Função FunctionIDMapper2

Notifica o criador de perfil de que o identificador fornecido de uma função pode ser remapeado para uma ID alternativa a ser usada nos retornos de chamada [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md)ou[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) para essa função. `FunctionIDMapper2` também permite que o criador de perfil indique se deseja receber retornos de chamada para essa função.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parâmetros

- `funcId`

  \[no] o identificador de função a ser remapeado.

- `clientData`

  \[in] um ponteiro para dados que são usados para eliminar a ambiguidade entre tempos de execução.

- `pbHookFunction`

  \[out] um ponteiro para um valor que o criador de perfil define `true` se deseja receber `FunctionEnter3` , `FunctionLeave3` , e `FunctionTailcall3` , ou `FunctionEnter3WithInfo` , `FunctionLeave3WithInfo` e `FunctionTailcall3WithInfo` retornos de chamada; caso contrário, ele define esse valor como `false` .

## <a name="return-value"></a>Valor Retornado  

 O criador de perfil retorna um valor que o mecanismo de execução usa como um identificador de função alternativo. O valor de retorno não pode ser nulo, a menos que `false` seja retornado em `pbHookFunction` . Caso contrário, um valor de retorno nulo produz resultados imprevisíveis, incluindo possivelmente interromper o processo.  
  
## <a name="remarks"></a>Comentários  

 Esse método estende a função [FunctionIDMapper](functionidmapper-function.md) com um parâmetro adicional que é usado para passar dados do cliente. Os dados do cliente são usados para fazer a ambiguidade entre tempos de execução.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3::SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Criando perfil de funções estáticas globais](profiling-global-static-functions.md)
