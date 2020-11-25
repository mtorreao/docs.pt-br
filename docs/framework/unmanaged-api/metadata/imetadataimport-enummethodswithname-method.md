---
title: Método IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720926"
---
# <a name="imetadataimportenummethodswithname-method"></a>Método IMetaDataImport::EnumMethodsWithName

Enumera os métodos que têm o nome especificado e que são definidos pelo tipo referenciado pelo token de TypeDef especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `phEnum`  
 [entrada, saída] Um ponteiro para o enumerador. Isso deve ser nulo para a primeira chamada deste método.  
  
 `cl`  
 no Um token de TypeDef que representa o tipo cujos métodos são enumerados.  
  
 `szName`  
 no O nome que limita o escopo da enumeração.  
  
 `rMethods`  
 fora A matriz usada para armazenar os tokens MethodDef.  
  
 `cMax`  
 no O tamanho máximo da `rMethods` matriz.  
  
 `pcTokens`  
 fora O número de tokens MethodDef retornados em `rMethods` .  
  
## <a name="remarks"></a>Comentários  

 Esse método enumera campos e métodos, mas não propriedades ou eventos. Ao contrário de [IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` descarta todos os tokens de método que não têm o nome especificado.  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|DESCRIÇÃO|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodsWithName` retornado com êxito.|  
|`S_FALSE`|Não há tokens para enumerar. Nesse caso, `pcTokens` é zero.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataImport](imetadataimport-interface.md)
- [Interface IMetaDataImport2](imetadataimport2-interface.md)
