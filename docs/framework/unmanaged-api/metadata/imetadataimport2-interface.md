---
title: Interface IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702539"
---
# <a name="imetadataimport2-interface"></a>Interface IMetaDataImport2

Estende a interface [IMetaDataImport](imetadataimport-interface.md) para fornecer a capacidade de trabalhar com tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método EnumGenericParamConstraints](imetadataimport2-enumgenericparamconstraints-method.md)|Obtém um enumerador para uma matriz de restrições de parâmetro genérico associadas ao parâmetro genérico representado pelo token especificado.|  
|[Método EnumGenericParams](imetadataimport2-enumgenericparams-method.md)|Obtém um enumerador para uma matriz de tokens de parâmetro genéricos associados ao TypeDef ou token MethodDef especificado.|  
|[Método EnumMethodSpecs](imetadataimport2-enummethodspecs-method.md)|Obtém um enumerador para uma matriz de tokens de MethodSpec associados ao token MethodDef ou MemberRef especificado.|  
|[Método GetGenericParamConstraintProps](imetadataimport2-getgenericparamconstraintprops-method.md)|Obtém os metadados associados à restrição de parâmetro genérico representada pelo token de restrição especificado.|  
|[Método GetGenericParamProps](imetadataimport2-getgenericparamprops-method.md)|Obtém os metadados associados ao parâmetro genérico representado pelo token especificado.|  
|[Método GetMethodSpecProps](imetadataimport2-getmethodspecprops-method.md)|Obtém a assinatura de metadados do método referenciado pelo token de MethodSpec especificado.|  
|[Método GetPEKind](imetadataimport2-getpekind-method.md)|Obtém um valor que identifica a natureza do código em um arquivo executável portátil (PE), normalmente um arquivo DLL ou EXE, definido no escopo de metadados atual|  
|[Método GetVersionString](imetadataimport2-getversionstring-method.md)|Obtém o número de versão do tempo de execução que foi usado para compilar o assembly.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- <xref:System.Reflection.PortableExecutableKinds>
- [Interfaces de metadados](metadata-interfaces.md)
- [Interface IMetaDataImport](imetadataimport-interface.md)
