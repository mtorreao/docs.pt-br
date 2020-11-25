---
title: Método ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: c76c8b23e707b530cbf1c28d03fbf2f84d424482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734004"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>Método ISymUnmanagedSourceServerModule::GetSourceServerData

Retorna os dados do servidor de origem para o módulo. O chamador deve liberar recursos usando o `CoTaskMemFree` .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pDataByteCount`  
 fora Um ponteiro para um `ULONG32` que recebe o tamanho, em bytes, dos dados do servidor de origem.  
  
 `ppData`  
 fora Um ponteiro para o `pDataByteCount` valor retornado.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedSourceServerModule](isymunmanagedsourceservermodule-interface.md)
