---
title: Método SetAssemblyFile2
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 131f5d951e524ef48f2cfe1e3e88ef80ac21c452
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703675"
---
# <a name="setassemblyfile2-method"></a>Método SetAssemblyFile2

Define o nome e as opções para um novo assembly. Não chame esse método quando você produzir módulos não associados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pszFilename`  
 Nome do arquivo de manifesto.  
  
 `pEmitter`  
 Interface de [interface IMetaDataEmit2](../metadata/imetadataemit2-interface.md) para este arquivo.  
  
 `afFlags`  
 Opções representadas pela [Enumeração AssemblyFlags](../metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Recebe uma ID exclusiva para o assembly que está sendo construído.  
  
## <a name="return-value"></a>Valor Retornado  

 Retorna S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 Requer ALink. h.  
  
## <a name="see-also"></a>Confira também

- [Interface IALink2](ialink2-interface.md)
- [Interface IALink](ialink-interface.md)
- [API do ALink](index.md)
