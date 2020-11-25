---
title: Interface IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728284"
---
# <a name="imetadataassemblyemit-interface"></a>Interface IMetaDataAssemblyEmit

Fornece métodos que dão suporte ao modelo de autodescrição usado pelo Common Language Runtime para resolver e consumir recursos.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método DefineAssembly](imetadataassemblyemit-defineassembly-method.md)|Cria uma estrutura de dados de assembly contendo metadados para o assembly especificado e retorna o token de metadados associado.|  
|[Método DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md)|Cria uma `AssemblyRef` estrutura que contém metadados para o assembly ao qual este assembly faz referência e retorna o token de metadados associado.|  
|[Método DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md)|Cria uma `ExportedType` estrutura que contém metadados para o tipo exportado especificado e retorna o token de metadados associado.|  
|[Método DefineFile](imetadataassemblyemit-definefile-method.md)|Cria uma `File` estrutura de metadados que contém metadados para o assembly referenciado por esse assembly e retorna o token de metadados associado.|  
|[Método DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md)|Cria uma `ManifestResource` estrutura que contém metadados para o recurso de manifesto especificado e retorna o token de metadados associado.|  
|[Método SetAssemblyProps](imetadataassemblyemit-setassemblyprops-method.md)|Modifica a estrutura de `Assembly` metadados especificada.|  
|[Método SetAssemblyRefProps](imetadataassemblyemit-setassemblyrefprops-method.md)|Modifica a estrutura de `AssemblyRef` metadados especificada.|  
|[Método SetExportedTypeProps](imetadataassemblyemit-setexportedtypeprops-method.md)|Modifica a estrutura de `ExportedType` metadados especificada.|  
|[Método SetFileProps](imetadataassemblyemit-setfileprops-method.md)|Modifica a estrutura de `File` metadados especificada.|  
|[Método SetManifestResourceProps](imetadataassemblyemit-setmanifestresourceprops-method.md)|Modifica a estrutura de `ManifestResource` metadados especificada.|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de metadados](metadata-interfaces.md)
- [Interface IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
