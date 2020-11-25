---
title: Método IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725749"
---
# <a name="imetadataemitdefinefield-method"></a>Método IMetaDataEmit::DefineField

Cria uma definição para um campo com a assinatura de metadados especificada e Obtém um token para essa definição de campo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `td`  
 no O `mdTypeDef` token para a classe ou a interface de circunscrição.  
  
 `szName`  
 no O nome do campo em Unicode.  
  
 `dwFieldFlags`  
 no Os atributos do campo. Esta é uma bitmask de `CorFieldAttr` valores.  
  
 `pvSigBlob`  
 no A assinatura de campo como um BLOB.  
  
 `cbSigBlob`  
 no A contagem de bytes em `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 no O `ELEMENT_TYPE_` *\** para o valor da constante. Esse é um `CorElementType` valor. Se não estiver definindo um valor constante para o campo, use `ELEMENT_TYPE_END` .  
  
 `pValue`  
 no O valor constante para o campo.  
  
 `cchValue`  
 no O tamanho em caracteres (Unicode) de `pValue` .  
  
 `pmd`  
 fora O `mdFieldDef` token atribuído.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataEmit](imetadataemit-interface.md)
- [Interface IMetaDataEmit2](imetadataemit2-interface.md)
