---
title: 'Método ICorDebugSymbolProvider:: GetCodeRange'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: f61a98dbd5a65207a46e033d54f9d5f60adac201
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709109"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>Método ICorDebugSymbolProvider:: GetCodeRange

Obtém o endereço inicial e o tamanho do método de acordo com um endereço virtual relativo (RVA) em um método.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `codeRva`  
 no O endereço virtual relativo (RVA) em um método.  
  
 `pCodeStartAddress`  
 fora Um ponteiro para o endereço inicial do método.  
  
 `pCodeSize`  
 Um ponteiro para o tamanho do código do método (o número de bytes do código do método).  
  
## <a name="remarks"></a>Comentários  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
