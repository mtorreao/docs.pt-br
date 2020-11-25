---
title: Função GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724432"
---
# <a name="gethistoryfiledirectory-function"></a>Função GetHistoryFileDirectory

Recupera o caminho do diretório de histórico do aplicativo.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `wzDir`  
 fora Um buffer para manter o caminho para o diretório de histórico do aplicativo.  
  
 `pdwSize`  
 [entrada, saída] O comprimento do buffer.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna códigos de erro COM padrão, conforme definido no arquivo WinError. h, além dos valores a seguir.  
  
|Código de retorno|Descrição|  
|-----------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|E_INVALIDARG|`wzDir` ou `pdwSize` é nulo ou a cadeia de caracteres da versão está incorreta.|  
  
## <a name="remarks"></a>Comentários  

 Após a conclusão bem-sucedida, o `pdwSize` argumento é definido como o comprimento da cadeia de caracteres do caminho.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** Fusion. h  
  
 **Biblioteca:** Fusion.dll e Mscorwks.dll. Use Fusion.dll em vez de Mscorwks.dll para garantir que você direcione a versão correta do .NET Framework.  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Função CreateHistoryReader](createhistoryreader-function.md)
- [Função NukeDownloadedCache](nukedownloadedcache-function.md)
- [Funções estáticas globais de fusão](fusion-global-static-functions.md)
