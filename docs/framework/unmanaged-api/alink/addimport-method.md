---
title: Método AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
ms.openlocfilehash: cf73ada36be66edb3fa267d61873ae9acb088a34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717039"
---
# <a name="addimport-method"></a>Método AddImport

Adiciona importações ao assembly.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parâmetros  

 `AssemblyID`  
 ID exclusiva do assembly a ser aumentada.  
  
 `ImportToken`  
 ID exclusiva, recuperada do [Método ImportFile](importfile-method.md), do arquivo a ser importado.  
  
 `dwFlags`  
 Sinalizadores de FileDef COM+, como `ffContainsNoMetaData` e `ffWriteable` . `dwFlags` é passado para o [método definofile](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Ponteiro para token que recebe a ID do arquivo resultante.  
  
## <a name="return-value"></a>Valor Retornado  

 Retorna S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 Requer ALink. h  
  
## <a name="see-also"></a>Confira também

- [Interface IALink](ialink-interface.md)
- [Interface IALink2](ialink2-interface.md)
- [API do ALink](index.md)
