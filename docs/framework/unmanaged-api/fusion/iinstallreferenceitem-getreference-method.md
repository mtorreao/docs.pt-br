---
title: Método IInstallReferenceItem::GetReference
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
ms.openlocfilehash: 14286970a4f7093d72b47b780ea880f5ccb1bca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721065"
---
# <a name="iinstallreferenceitemgetreference-method"></a>Método IInstallReferenceItem::GetReference

Obtém um ponteiro para a estrutura de [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) representada por este objeto [IInstallReferenceItem](iinstallreferenceitem-interface.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `ppRefData`  
 fora O `FUSION_INSTALL_REFERENCE` ponteiro retornado.  
  
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
- [Estrutura FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)
