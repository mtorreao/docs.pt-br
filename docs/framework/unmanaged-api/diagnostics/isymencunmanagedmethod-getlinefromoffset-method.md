---
title: Método ISymENCUnmanagedMethod::GetLineFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 196993df9058d3eb8167e0144255c5fe366c54f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707354"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>Método ISymENCUnmanagedMethod::GetLineFromOffset

Obtém as informações de linha associadas a um deslocamento. Se o parâmetro offset ( `dwOffset` ) não for um ponto de sequência, esse método obterá as informações de linha associadas ao deslocamento anterior.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `dwOffset`  
 no Um `ULONG32` que contém o deslocamento.  
  
 `pline`  
 fora Um ponteiro para um `ULONG32` que recebe a linha.  
  
 `pcolumn`  
 fora Um ponteiro para um `ULONG32` que recebe a coluna.  
  
 `pendLine`  
 fora Um ponteiro para um `ULONG32` que recebe a linha final.  
  
 `pendColumn`  
 fora Um ponteiro para um `ULONG32` que recebe a coluna final.  
  
 `pdwStartOffset`  
 fora Um ponteiro para um `ULONG32` que recebe o ponto de sequência associado.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
