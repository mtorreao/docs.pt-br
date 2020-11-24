---
title: Método ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689544"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a>Método ISymUnmanagedReader::GetMethodsFromDocumentPosition

Retorna uma matriz de métodos, cada um contendo o ponto de interrupção na posição especificada em um documento.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `document`  
 no O documento especificado.  
  
 `line`  
 no A linha do documento especificado.  
  
 `column`  
 no A coluna do documento especificado.  
  
 `cMethod`  
 no O tamanho da `pRetVal` matriz.  
  
 `pcMethod`  
 fora Um ponteiro para uma variável que recebe o número de elementos retornados na `pRetVal` matriz.  
  
 `pRetVal`  
 fora Uma matriz de ponteiros, cada um dos quais aponta para um objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa um método que contém o ponto de interrupção.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedReader](isymunmanagedreader-interface.md)
