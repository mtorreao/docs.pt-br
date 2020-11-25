---
title: Método IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720406"
---
# <a name="imetadataimportenumtypedefs-method"></a>Método IMetaDataImport::EnumTypeDefs

Enumera os tokens de TypeDef que representam todos os tipos no escopo atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `phEnum`  
 fora Um ponteiro para o novo enumerador. Isso deve ser nulo para a primeira chamada deste método.  
  
 `rTypeDefs`  
 no A matriz usada para armazenar os tokens de TypeDef.  
  
 `cMax`  
 no O tamanho máximo da `rTypeDefs` matriz.  
  
 `pcTypeDefs`  
 fora O número de tokens de TypeDef retornados em `rTypeDefs` .  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|DESCRIÇÃO|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` retornado com êxito.|  
|`S_FALSE`|Não há tokens para enumerar. Nesse caso, `pcTypeDefs` é zero.|  
  
## <a name="remarks"></a>Comentários  

 O token TypeDef representa um tipo como uma classe ou uma interface, bem como qualquer tipo adicionado por meio de um mecanismo de extensibilidade.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Incluído como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataImport](imetadataimport-interface.md)
- [Interface IMetaDataImport2](imetadataimport2-interface.md)
