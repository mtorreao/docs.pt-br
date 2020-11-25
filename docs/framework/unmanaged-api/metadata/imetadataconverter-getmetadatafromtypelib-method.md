---
title: Método IMetaDataConverter::GetMetaDataFromTypeLib
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: ed0902824bdbb4d057bf5a7920db4b1d18eb7347
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714660"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a>Método IMetaDataConverter::GetMetaDataFromTypeLib

Obtém um ponteiro de interface para uma instância de [IMetaDataImport](imetadataimport-interface.md) que representa a assinatura de metadados da biblioteca de tipos representada pela `ITypeLib` instância especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pITL`  
 no Ponteiro para um `ITypeLib` objeto que representa a biblioteca de tipos.  
  
 `ppMDI`  
 fora Ponteiro para um local que recebe o endereço da `IMetaDataImport` instância que representa a assinatura de metadados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor. h  
  
 **Biblioteca:** Usado como um recurso no MsCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IMetaDataEmit](imetadataemit-interface.md)
- [Interface IMetaDataImport](imetadataimport-interface.md)
