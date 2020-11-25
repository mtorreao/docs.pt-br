---
title: Método ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 297f672097dd6561a971608f368369c623532907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716909"
---
# <a name="icorpublishenumprocesses-method"></a>Método ICorPublish::EnumProcesses

Obtém um enumerador para os processos gerenciados em execução neste computador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `Type`  
 Um valor da enumeração de [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) que especifica o tipo de processo a ser recuperado. Na versão atual, somente COR_PUB_MANAGEDONLY é válida.  
  
 `ppIEnum`  
 Um ponteiro para o endereço de uma instância de [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) que é o enumerador dos processos.  
  
## <a name="remarks"></a>Comentários  

 A coleção de processos do enumerador é baseada em um instantâneo dos processos que estão em execução quando o `EnumProcesses` método é chamado. O enumerador não incluirá nenhum processo encerrado antes ou iniciado depois de `EnumProcesses` ser chamado.  
  
 O `EnumProcesses` método pode ser chamado mais de uma vez nessa instância de [ICorPublish](icorpublish-interface.md) para criar uma nova coleção atualizada de processos. As coleções existentes não serão afetadas pelas chamadas subsequentes do `EnumProcesses` método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorPublish](icorpublish-interface.md)
