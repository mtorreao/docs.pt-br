---
title: Método IInstallReferenceEnum::GetNextInstallReferenceItem
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721095"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a>Método IInstallReferenceEnum::GetNextInstallReferenceItem

Obtém um ponteiro para o próximo objeto [IInstallReferenceItem](iinstallreferenceitem-interface.md) contido neste objeto [IInstallReferenceEnum](iinstallreferenceenum-interface.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppRefItem`  
 fora O `IInstallReferenceItem` ponteiro retornado.  
  
 `dwFlags`  
 no Reservado para extensibilidade futura. `dwFlags` deve ser 0 (zero).  
  
 `pvReserved`  
 no Reservado para extensibilidade futura. `pvReserved` deve ser uma referência nula.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface IInstallReferenceItem](iinstallreferenceitem-interface.md)
- [Interface IInstallReferenceEnum](iinstallreferenceenum-interface.md)
