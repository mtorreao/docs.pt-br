---
title: 'Método ICorDebugMergedAssemblyRecord:: getculture'
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710643"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>Método ICorDebugMergedAssemblyRecord:: getculture

Obtém a cadeia de caracteres do nome da cultura do assembly.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `cchCulture`  
 no O número de caracteres no `szCulture` buffer.  
  
 `pcchCulture`  
 fora O número de caracteres realmente gravados no `szCulture` buffer.  
  
 `szCulture`  
 fora Uma matriz de caracteres que contém o nome da cultura.  
  
## <a name="remarks"></a>Comentários  

 O nome da cultura é uma cadeia de caracteres exclusiva que identifica uma cultura, como "en-US" (para a cultura em inglês (Estados Unidos)) ou "neutro" (para uma cultura neutra).  
  
> [!NOTE]
> Esse método está disponível somente com .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Depurando interfaces](debugging-interfaces.md)
