---
title: Método ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 4030da31400b7075952d146e5d6740306863e9ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721082"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>Método ISymUnmanagedDocument::GetCheckSum

Obtém a soma de verificação.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `cData`  
 no O comprimento do buffer fornecido pelo `data` parâmetro  
  
 `pcData`  
 fora O tamanho e o comprimento da soma de verificação, em bytes.  
  
 `data`  
 fora O buffer que recebe a soma de verificação.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, um código de erro.  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedDocument](isymunmanageddocument-interface.md)
