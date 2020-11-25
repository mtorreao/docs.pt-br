---
title: Método IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: c9ff918121e7bb4ee972e674207810358b3f36f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712905"
---
# <a name="imetadataemit2definegenericparam-method"></a>Método IMetaDataEmit2::DefineGenericParam

Cria uma definição para um parâmetro de tipo genérico e Obtém um token para esse parâmetro de tipo genérico.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `tk`  
 no Um `mdTypeDef` `mdMethodDef` token ou que representa o método ou construtor para o qual definir um parâmetro genérico.  
  
 `ulParamSeq`  
 no O índice do parâmetro genérico.  
  
 `dwParamFlags`  
 no Um valor da enumeração [CorGenericParamAttr](corgenericparamattr-enumeration.md) que descreve o tipo para o parâmetro genérico.  
  
 `szname`  
 no O nome do parâmetro.  
  
 `reserved`  
 no Esse parâmetro é reservado para extensibilidade futura.  
  
 `rtkConstraints`  
 no Uma matriz de restrições de tipo terminada em zero. Os membros da matriz devem ser um `mdTypeDef` `mdTypeRef` token de metadados, ou `mdTypeSpec` .  
  
 `pgp`  
 fora Um token que representa o parâmetro genérico.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataEmit2](imetadataemit2-interface.md)
- [Interface IMetaDataEmit](imetadataemit-interface.md)
