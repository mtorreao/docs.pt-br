---
title: Função CreateAssemblyEnum
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683167"
---
# <a name="createassemblyenum-function"></a>Função CreateAssemblyEnum

Obtém um ponteiro para uma instância de [IAssemblyEnum](iassemblyenum-interface.md) que pode enumerar os objetos no assembly com o [IAssemblyName](iassemblyname-interface.md)especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pEnum`  
 fora Ponteiro para um local de memória que contém o `IAssemblyEnum` ponteiro solicitado.  
  
 `pUnkReserved`  
 no Reservado para extensibilidade futura. `pUnkReserved` deve ser uma referência nula.  
  
 `pName`  
 no O `IAssemblyName` do assembly solicitado. Esse nome é usado para filtrar a enumeração. Pode ser NULL para enumerar todos os assemblies no cache de assembly global.  
  
 `dwFlags`  
 no Sinalizadores para modificar o comportamento do enumerador. Esse parâmetro contém exatamente um bit da enumeração [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .  
  
 `pvReserved`  
 no Reservado para extensibilidade futura. `pvReserved` deve ser uma referência nula.  
  
## <a name="remarks"></a>Comentários  

 O `dwFlags` parâmetro contém exatamente um bit da `ASM_CACHE_FLAGS` enumeração.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IAssemblyEnum](iassemblyenum-interface.md)
- [Interface IAssemblyName](iassemblyname-interface.md)
- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
