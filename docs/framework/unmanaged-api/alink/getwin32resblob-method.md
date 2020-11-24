---
title: Método GetWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684506"
---
# <a name="getwin32resblob-method"></a>Método GetWin32ResBlob

Recupera o blob de recursos do Win32. Chame esse método depois de definir as opções de assembly.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Parâmetros  

 `AssemblyID`  
 ID do assembly.  
  
 `FileToken`  
 O token de arquivo usado para recuperar o nome de o FileName a ser usado ao construir o recurso de versão do Win32  
  
 `fDll`  
 TRUE se o arquivo for uma DLL, false para um EXE.  
  
 `pszIconFile`  
 Ícone opcional para inserir no blob de recursos.  
  
 `ppResBlob`  
 Recebe o blob de recursos.  
  
 `pcbResBlob`  
 Recebe o tamanho do blob.  
  
## <a name="return-value"></a>Valor Retornado  

 Retorna S_OK se o método tiver sucesso.  
  
## <a name="requirements"></a>Requisitos  

 Requer ALink. h  
  
## <a name="see-also"></a>Confira também

- [Interface IALink](ialink-interface.md)
- [Interface IALink2](ialink2-interface.md)
- [API do ALink](index.md)
