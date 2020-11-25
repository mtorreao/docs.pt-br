---
title: Método ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: 8b3f6ae92e39f5385bf29f8b29abbb1726136088
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724761"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Método ICorDebugAppDomain2::GetArrayOrPointerType

Obtém uma matriz do tipo especificado ou um ponteiro ou uma referência para o tipo especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `elementType`  
 no Um valor da enumeração CorElementType que especifica o tipo nativo subjacente (uma matriz, um ponteiro ou uma referência) a ser criado.  
  
 `nRank`  
 no A classificação (ou seja, o número de dimensões) da matriz. Esse valor deve ser 0 se `elementType` especificar um ponteiro ou tipo de referência.  
  
 `pTypeArg`  
 no Um ponteiro para um objeto ICorDebugType que representa o tipo de matriz, ponteiro ou referência a ser criado.  
  
 `ppType`  
 fora Um ponteiro para o endereço de um `ICorDebugType` objeto que representa a matriz construída, o tipo de ponteiro ou o tipo de referência.  
  
## <a name="remarks"></a>Comentários  

 O valor de *ElementType* deve ser um dos seguintes:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY ou ELEMENT_TYPE_SZARRAY  
  
 Se o valor de *ElementType* for ELEMENT_TYPE_PTR ou ELEMENT_TYPE_BYREF, *nRank* deverá ser zero.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
