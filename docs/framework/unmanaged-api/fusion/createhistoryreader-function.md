---
title: Função CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 9dae3f1403d33aaf3cfb87d17856640548a90b4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688926"
---
# <a name="createhistoryreader-function"></a>Função CreateHistoryReader

Cria um leitor de histórico para o arquivo especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parâmetros  

 `wzFilePath`  
 no O caminho do arquivo.  
  
 `ppHistoryReader`  
 fora Após a conclusão bem-sucedida, contém um ponteiro para o leitor de histórico.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna códigos de erro COM padrão, conforme definido no WinError. h, além dos valores descritos na tabela a seguir.  
  
|Código de retorno|Descrição|  
|-----------------|-----------------|  
|S_OK|Indica que o método foi concluído com êxito.|  
|E_INVALIDARG|Indica se `wzFilePath` or `ppHistoryReader` está definido como uma referência nula.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Biblioteca:** Fusion.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
