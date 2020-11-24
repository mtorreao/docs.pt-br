---
title: Interface ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: 41d049c931091d2cc0b41bd1e9d74b3c15d7878d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679254"
---
# <a name="iclrassemblyidentitymanager-interface"></a>Interface ICLRAssemblyIdentityManager

Fornece métodos que dão suporte à comunicação entre o host e o Common Language Runtime (CLR) sobre assemblies.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIÇÃO|  
|------------|-----------------|  
|[Método GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Obtém os dados de associação de identidade do assembly para o assembly no caminho de arquivo especificado.|  
|[Método GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Obtém os dados de identidade do assembly canônico para o assembly no fluxo especificado.|  
|[Método GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Obtém uma instância de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) da lista fornecida de identidades de assembly parciais.|  
|[Método GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Obtém um enumerador [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) para as identidades de assembly referenciadas pelo assembly com a identidade especificada.|  
|[Método GetReferencedAssembliesFromFile](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Obtém uma instância de [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contém uma lista de assemblies referenciados pelo assembly no caminho de arquivo especificado.|  
|[Método GetReferencedAssembliesFromStream](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Obtém um ponteiro para um `ICLRReferenceAssemblyEnum` objeto que contém dados de identidade de assembly para os assemblies referenciados pelo assembly no fluxo especificado.|  
|[Método IsStronglyNamed](iclrassemblyidentitymanager-isstronglynamed-method.md)|Obtém um valor que indica se o assembly especificado tem um nome forte.|  
  
## <a name="remarks"></a>Comentários  

 Use `ICLRAssemblyIdentityManager` para obter instâncias do `ICLRAssemblyReferenceList` e para enumerar identidades de assembly.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Interface ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)
- [Interfaces de hospedagem](hosting-interfaces.md)
