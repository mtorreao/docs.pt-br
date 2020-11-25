---
title: Método IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731586"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>Método IMetaDataAssemblyImport::FindExportedTypeByName

Obtém um ponteiro para um tipo exportado, dado seu nome e tipo de delimitador.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `szName`  
 no O nome do tipo exportado.  
  
 `mdtExportedType`  
 no O token de metadados para a classe de circunscrição do tipo exportado. Esse valor é `mdExportedTypeNil` se o tipo exportado solicitado não for um tipo aninhado.  
  
 `ptkExportedType`  
 fora Um ponteiro para o `mdExportedType` token que representa o tipo exportado.  
  
## <a name="remarks"></a>Comentários  

 O `FindExportedTypeByName` método usa as regras padrão empregadas pelo Common Language Runtime para resolver referências.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Como o runtime localiza assemblies](../../deployment/how-the-runtime-locates-assemblies.md)
