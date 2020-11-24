---
title: Método ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675822"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>Método ISymUnmanagedReader::UpdateSymbolStore

Atualiza o repositório de símbolos existente com um repositório de símbolos delta. Esse método é usado em cenários de edição e continuação para atualizar o armazenamento de símbolo para corresponder deltas ao arquivo PE (executável portátil) original.  
  
> [!NOTE]
> Você precisa especificar apenas um dos `filename` parâmetros ou `pIStream` , não ambos. Se `filename` for especificado, o armazenamento de símbolos será atualizado com os símbolos nesse arquivo. Se `pIStream` for especificado, o repositório será atualizado com os dados do <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `filename`  
 no O nome do arquivo que contém o armazenamento de símbolo.  
  
 `pIStream`  
 no O fluxo de arquivos, usado como uma alternativa ao `filename` parâmetro.  
  
## <a name="return-value"></a>Valor Retornado  

 S_OK se o método tiver sucesso; caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  

 **Cabeçalho:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Confira também

- [Interface ISymUnmanagedReader](isymunmanagedreader-interface.md)
