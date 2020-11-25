---
title: Método IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 26b345567699c5780827ed835cff13069ea8f609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702739"
---
# <a name="imetadataimport2enummethodspecs-method"></a>Método IMetaDataImport2::EnumMethodSpecs

Obtém um enumerador para uma matriz de tokens de MethodSpec associados ao token MethodDef ou MemberRef especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>Parâmetros  

 `phEnum`  
 [entrada, saída] Um ponteiro para o enumerador para `rMethodSpecs` .  
  
 `tk`  
 no O token MemberRef ou MethodDef que representa o método cujos tokens de MethodSpec devem ser enumerados. Se o valor de `tk` for 0 (zero), todos os tokens de MethodSpec no escopo serão enumerados.  
  
 `rMethodSpecs`  
 fora A matriz de tokens de MethodSpec a ser enumerada.  
  
 `cMax`  
 no O número máximo solicitado de tokens a serem colocados `rMethodSpecs` .  
  
 `pcMethodSpecs`  
 fora O número retornado de tokens colocados em `rMethodSpecs` .  
  
## <a name="return-value"></a>Valor Retornado  
  
|HRESULT|DESCRIÇÃO|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` retornado com êxito.|  
|`S_FALSE`|`phEnum` Não tem elementos de membro. Nesse caso, `pcMethodSpecs` é definido como 0 (zero).|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataImport2](imetadataimport2-interface.md)
- [Interface IMetaDataImport](imetadataimport-interface.md)
