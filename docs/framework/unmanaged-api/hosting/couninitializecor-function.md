---
title: Função CoUninitializeCor
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 7d39c6fda6f159bfc937f62dc45d0d7ce37657f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687875"
---
# <a name="couninitializecor-function"></a>Função CoUninitializeCor

`CoUninitializeCor` é obsoleto.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Comentários  

 O Common Language Runtime não pode ser descarregado de um processo. Para remover completamente o tempo de execução de um processo em execução, você deve desligar esse processo.  
  
## <a name="see-also"></a>Confira também

- [Funções estáticas globais de metadados](../metadata/metadata-global-static-functions.md)
