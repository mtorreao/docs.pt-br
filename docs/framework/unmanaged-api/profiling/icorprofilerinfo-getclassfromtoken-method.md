---
title: Método ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706743"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>Método ICorProfilerInfo::GetClassFromToken

Obtém a ID da classe, dado o token de metadados. Esse método é obsoleto no .NET Framework versão 2,0. Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) em vez disso.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `moduleID`  
 no A ID do módulo que contém a classe.  
  
 `typeDef`  
 no Um `mdTypeDef` token de metadados que faz referência à classe.  
  
 `cTypeArgs`  
 fora Um ponteiro para a ID de classe.  
  
## <a name="remarks"></a>Comentários  

 Este método é obsoleto; em vez disso, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos os tipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf. idl, CorProf. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Confira também

- [Interface ICorProfilerInfo](icorprofilerinfo-interface.md)
