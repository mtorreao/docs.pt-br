---
title: Interface IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714751"
---
# <a name="imetadataassemblyimport-interface"></a>Interface IMetaDataAssemblyImport

Fornece métodos para acessar e examinar o conteúdo de um manifesto do assembly.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método CloseEnum](imetadataassemblyimport-closeenum-method.md)|Libera o identificador para o enumerador especificado.|  
|[Método EnumAssemblyRefs](imetadataassemblyimport-enumassemblyrefs-method.md)|Obtém um ponteiro de interface para um enumerador que contém os `mdAssemblyRef` tokens dos assemblies referenciados pelo assembly no escopo de metadados atual.|  
|[Método EnumExportedTypes](imetadataassemblyimport-enumexportedtypes-method.md)|Obtém um ponteiro de interface para um enumerador que contém os `mdExportedType` tokens dos tipos com referenciados pelo assembly no escopo de metadados atual.|  
|[Método EnumFiles](imetadataassemblyimport-enumfiles-method.md)|Obtém um ponteiro de interface para um enumerador que contém os `mdFile` tokens dos arquivos referenciados pelo assembly no escopo de metadados atual.|  
|[Método EnumManifestResources](imetadataassemblyimport-enummanifestresources-method.md)|Obtém um ponteiro de interface para um enumerador que contém os `mdManifestResource` tokens dos recursos referenciados pelo assembly no escopo de metadados atual.|  
|[Método FindAssembliesByName](imetadataassemblyimport-findassembliesbyname-method.md)|Obtém uma matriz de `mdAssemblyRef` tokens para os assemblies com o nome especificado.|  
|[Método FindExportedTypeByName](imetadataassemblyimport-findexportedtypebyname-method.md)|Obtém um `mdExportedType` token para o tipo com com o nome especificado.|  
|[Método FindManifestResourceByName](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Obtém um `mdManifestResource` token para o recurso com o nome especificado.|  
|[Método GetAssemblyFromScope](imetadataassemblyimport-getassemblyfromscope-method.md)|Obtém o token para o assembly no escopo de metadados atual.|  
|[Método GetAssemblyProps](imetadataassemblyimport-getassemblyprops-method.md)|Obtém as configurações de Propriedade do assembly especificado.|  
|[Método GetAssemblyRefProps](imetadataassemblyimport-getassemblyrefprops-method.md)|Obtém as configurações de Propriedade do `mdAssemblyRef` token especificado.|  
|[Método GetExportedTypeProps](imetadataassemblyimport-getexportedtypeprops-method.md)|Obtém as configurações de Propriedade do tipo COM especificado.|  
|[Método GetFileProps](imetadataassemblyimport-getfileprops-method.md)|Obtém as configurações de Propriedade do arquivo especificado.|  
|[Método GetManifestResourceProps](imetadataassemblyimport-getmanifestresourceprops-method.md)|Obtém as configurações de Propriedade do recurso de manifesto especificado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interfaces de metadados](metadata-interfaces.md)
- [Interface IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
