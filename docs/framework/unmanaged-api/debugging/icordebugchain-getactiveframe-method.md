---
title: Método ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730130"
---
# <a name="icordebugchaingetactiveframe-method"></a>Método ICorDebugChain::GetActiveFrame

Obtém o quadro ativo (ou seja, mais recente) na cadeia.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppFrame`  
 fora Um ponteiro para o endereço de um objeto ICorDebugFrame que representa o quadro ativo (ou seja, mais recente) na cadeia.  
  
## <a name="remarks"></a>Comentários  

 Se nenhum quadro de pilha gerenciado estiver disponível, `ppFrame` será definido como nulo.  
  
 Se o quadro ativo não estiver disponível, a chamada terá sucesso e `ppFrame` será NULL. Os quadros ativos não estarão disponíveis para cadeias iniciadas devido a CHAIN_ENTER_UNMANAGED e para algumas cadeias iniciadas devido a CHAIN_CLASS_INIT. Consulte a enumeração CorDebugChainReason.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
