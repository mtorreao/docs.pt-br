---
title: Método IMetaDataEmit::DefinePermissionSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: 3698525c139ed52b59ca577c598e675b6c26eef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719509"
---
# <a name="imetadataemitdefinepermissionset-method"></a>Método IMetaDataEmit::DefinePermissionSet

Cria uma definição para um conjunto de permissões com a assinatura de metadados especificada e Obtém um token para essa definição de conjunto de permissões.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `tk`  
 no O objeto a ser decorado.  
  
 `dwAction`  
 no Um valor de [CorDeclSecurity](cordeclsecurity-enumeration.md) que especifica o tipo de segurança declarativa a ser usado.  
  
 `pvPermission`  
 no O BLOB de permissão.  
  
 `cbPermission`  
 no O tamanho, em bytes, de `pvPermission` .  
  
 `ppm`  
 fora O token de permissão retornado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataEmit](imetadataemit-interface.md)
- [Interface IMetaDataEmit2](imetadataemit2-interface.md)
