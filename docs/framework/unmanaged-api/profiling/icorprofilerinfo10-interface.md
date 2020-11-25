---
title: Interface ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: a99fa8410bbd0dedeaeb9e1713107a3dcc9ada6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727218"
---
# <a name="icorprofilerinfo10-interface"></a>Interface ICorProfilerInfo10

Uma subclasse de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que fornece métodos para modificar o Il da função, consultar informações do tempo de execução e suspender e retomar o tempo de execução.

## <a name="methods"></a>Métodos  

| Método|DESCRIÇÃO|  
| ------------|-----------------|  
|[Método EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|Dado um ObjectID, retorno de chamada e clientData, enumera cada referência de objeto (se houver). |
|[Método IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Dado um ObjectID, determina se o objeto está em um segmento somente leitura. |
|[Método GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Obtém o valor do limite de LOH configurado. |
|[Método RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs os métodos solicitados, bem como quaisquer inlineers dos métodos solicitados.  |
|[Método SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Suspende o tempo de execução sem executar um GC. |
|[Método ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Retoma o tempo de execução sem executar um GC. |

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operacionais com suporte do .NET Core](../../../core/install/windows.md?pivots=os-windows).  
**Cabeçalho:** CorProf. idl, CorProf. h  
**Versões do .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Confira também

- [Criação de perfil de interfaces](profiling-interfaces.md)
