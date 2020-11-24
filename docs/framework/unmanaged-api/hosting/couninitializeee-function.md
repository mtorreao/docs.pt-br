---
title: Função CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687841"
---
# <a name="couninitializeee-function"></a>Função CoUninitializeEE

`CoUninitializeEE` é obsoleto e não fornece nenhuma funcionalidade.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Comentários  

 O mecanismo de execução de Common Language Runtime não pode ser descarregado de um processo. Para desligar a chamada do mecanismo de execução [CorExitProcess](corexitprocess-function.md).  
  
## <a name="see-also"></a>Confira também

- [Função CoInitializeEE](coinitializeee-function.md)
- [Funções estáticas globais de metadados](../metadata/metadata-global-static-functions.md)
