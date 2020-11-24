---
title: Método IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 3c03497f48b8199da545d796637e5f8a5c532362
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675679"
---
# <a name="imetadataemitdefineevent-method"></a>Método IMetaDataEmit::DefineEvent

Cria uma definição para um evento com a assinatura de metadados especificada e Obtém um token para essa definição de evento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `td`  
 no O token para a classe ou interface de destino. Esse é um `mdTypeDef` token ou `mdTypeDefNil` .  
  
 `szEvent`  
 no O nome do evento.  
  
 `dwEventFlags`  
 no Sinalizadores de eventos.  
  
 `tkEventType`  
 no O token para a classe de evento. Este é um `mdTypeDef` , um `mdTypeRef` ou um `mdTokenNil` token.  
  
 `mdAddOn`  
 no O método usado para assinar o evento ou nulo.  
  
 `mdRemoveOn`  
 no O método usado para cancelar a assinatura do evento, ou NULL.  
  
 `mdFire`  
 no O método usado (por uma classe derivada) para gerar o evento.  
  
 `rmdOtherMethods[]`  
 no Uma matriz de tokens para outros métodos associados ao evento. A matriz é encerrada com um `mdMethodDefNil` token.  
  
 `pmdEvent`  
 fora O token de metadados atribuído ao evento.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataEmit](imetadataemit-interface.md)
- [Interface IMetaDataEmit2](imetadataemit2-interface.md)
