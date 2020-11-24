---
title: Método ICLRMetaHost::GetVersionFromFile
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: f5e0ead41ebd13c259c24fa0c02bcc9a3b33e0fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689440"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>Método ICLRMetaHost::GetVersionFromFile

Obtém a versão de compilação de .NET Framework original de um assembly (armazenada nos metadados), dado seu caminho de arquivo. Esse método substitui a função [GetFileVersion](getfileversion-function.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pwzFilePath`  
 no O caminho completo do arquivo do assembly.  
  
 `pwzbuffer`  
 fora A versão de compilação .NET Framework armazenada nos metadados, no formato "v *A*. *B*[.*X*] ". *A*, *B* e *X* são números decimais que correspondem à versão principal, à versão secundária e ao número da compilação. O comprimento dessa cadeia de caracteres é limitado a MAX_PATH.  
  
> [!NOTE]
> Essa saída corresponde ao nome do diretório para a versão .NET Framework, como aparece em C:\Windows\Microsoft.NET\Framework.  
  
 Os valores de exemplo são "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", em que *x* depende do número de Build instalado. Observe que o prefixo "v" é necessário.  
  
 `pcchBuffer`  
 [entrada, saída] O tamanho de `pwzbuffer` para evitar estouros de buffer.  
  
## <a name="return-value"></a>Valor Retornado  

 Esse método retorna os HRESULTs específicos a seguir, bem como os erros de HRESULT que indicam falha de método.  
  
|HRESULT|Descrição|  
|-------------|-----------------|  
|S_OK|O método foi concluído com êxito.|  
|E_POINTER|`pwzbuffer` ou `pcchBuffer` é nulo.|  
|HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT_BUFFER)|O buffer é muito pequeno.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).  
  
 **Cabeçalho:** MetaHost. h  
  
 **Biblioteca:** Incluído como um recurso no MSCorEE.dll  
  
 **.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Confira também

- [Interface ICLRMetaHost](iclrmetahost-interface.md)
- [Hosting](index.md)
