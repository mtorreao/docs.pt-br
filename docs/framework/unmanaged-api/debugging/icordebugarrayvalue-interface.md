---
title: Interface ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: 90688132b98f8316a4b08988c08b2f7cc7ce0fd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725037"
---
# <a name="icordebugarrayvalue-interface"></a>Interface ICorDebugArrayValue

Uma subclasse de ICorDebugHeapValue que representa uma matriz unidimensional ou multidimensional.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetBaseIndicies](icordebugarrayvalue-getbaseindicies-method.md)|Obtém o índice base de cada dimensão na matriz.|  
|[Método GetCount](icordebugarrayvalue-getcount-method.md)|Obtém o número total de elementos na matriz.|  
|[Método GetDimensions](icordebugarrayvalue-getdimensions-method.md)|Obtém as dimensões da matriz.|  
|[Método GetElement](icordebugarrayvalue-getelement-method.md)|Obtém um valor que representa o elemento fornecido na matriz.|  
|[Método GetElementAtPosition](icordebugarrayvalue-getelementatposition-method.md)|Obtém o elemento na posição fornecida, tratando a matriz como uma matriz unidimensional com base em zero.|  
|[Método GetElementType](icordebugarrayvalue-getelementtype-method.md)|Obtém o tipo simples dos elementos na matriz.|  
|[Método GetRank](icordebugarrayvalue-getrank-method.md)|Obtém o número de dimensões na matriz.|  
|[Método HasBaseIndicies](icordebugarrayvalue-hasbaseindicies-method.md)|Determina se a matriz tem índices base.|  
  
## <a name="remarks"></a>Comentários  

 `ICorDebugArrayValue` dá suporte a matrizes unidimensionais e multidimensionais.  
  
> [!NOTE]
> Esta interface não dá suporte para chamada remota, seja entre computadores ou processos cruzados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Depurando interfaces](debugging-interfaces.md)
