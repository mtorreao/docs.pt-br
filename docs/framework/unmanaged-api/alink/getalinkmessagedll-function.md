---
title: Função GetALinkMessageDll
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684740"
---
# <a name="getalinkmessagedll-function"></a>Função GetALinkMessageDll

Localiza e carrega a DLL de mensagem. Retornará 0 se a DLL de mensagem não puder ser localizada ou carregada. A DLL de mensagem deve estar em um subdiretório cujo nome é uma ID de idioma ou no diretório atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** ALink. h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Confira também

- [Al.exe (vinculador de assembly)](../../tools/al-exe-assembly-linker.md)
