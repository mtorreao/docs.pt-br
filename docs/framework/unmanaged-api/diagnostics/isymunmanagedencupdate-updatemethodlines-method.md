---
title: Método ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 99499b8717f219616b6b368e6393b4b7ca0a79d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699580"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>Método ISymUnmanagedENCUpdate::UpdateMethodLines

Permite atualizar as informações de linha de um método que não foi recompilado, mas cujas linhas foram movidas de forma independente. Um Delta para cada instrução é permitido.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `mdMethodToken`  
 no Os metadados do token do método.  
  
 `pDeltas`  
 no Uma matriz de `INT32` valores que indica deltas para cada ponto de sequência no método.  
  
 `cDeltas`  
 no Um `ULONG` valor que contém o tamanho do `pDeltas` parâmetro.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
