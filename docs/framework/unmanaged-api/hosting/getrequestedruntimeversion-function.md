---
title: Função GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6c16b02a5ae323ba80d44937f322810022dfa9f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711631"
---
# <a name="getrequestedruntimeversion-function"></a>Função GetRequestedRuntimeVersion

Obtém o número de versão do Common Language Runtime (CLR) solicitado pelo aplicativo especificado. Se essa versão não estiver instalada, o obterá a versão mais recente instalada antes da versão solicitada.  
  
 Essa função foi preterida no .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pExe`  
 no O nome do aplicativo.  
  
 `pVersion`  
 fora Um buffer que contém a cadeia de caracteres de número de versão após a conclusão bem-sucedida.  
  
 `cchBuffer`  
 no O comprimento do buffer de versão.  
  
 `pdwLength`  
 fora Um ponteiro para o comprimento da cadeia de caracteres do número de versão.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna códigos de erro padrão de Component Object Model (COM), conforme definido no WinError. h, além dos valores a seguir.  
  
|Código de retorno|Descrição|  
|-----------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|ERROR_INSUFFICIENT_BUFFER|O buffer de versão não é grande o suficiente para armazenar a cadeia de caracteres de versão.|  
|E_POINTER|`pdwLength` é nulo.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Função GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)
- [Função GetVersionFromProcess](getversionfromprocess-function.md)
- [Funções de hospedagem CLR reprovadas](deprecated-clr-hosting-functions.md)
