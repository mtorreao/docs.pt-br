---
title: Função CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683721"
---
# <a name="createalink-function"></a>Função CreateALink

Cria uma instância do vinculador de assembly e define um ponteiro para a interface especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Parâmetros  
  
|Parâmetro|DESCRIÇÃO|  
|---------------|-----------------|  
|`riid`|O nome físico de uma das interfaces do vinculador de assembly.|  
|`ppInterface`|O local em que a conclusão bem-sucedida contém um ponteiro para a `riid` interface.|  
  
## <a name="requirements"></a>Requisitos  

 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Confira também

- [Al.exe (vinculador de assembly)](../../tools/al-exe-assembly-linker.md)
