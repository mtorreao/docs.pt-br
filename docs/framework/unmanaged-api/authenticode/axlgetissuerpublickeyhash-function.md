---
title: Função _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
ms.openlocfilehash: 49674e43109108e41b135cecbec061ad61e14865
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679956"
---
# <a name="_axlgetissuerpublickeyhash-function"></a>\_Função AxlGetIssuerPublicKeyHash

Recupera o hash SHA-1 da chave pública associada à chave privada usada para assinar o certificado especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a>Parâmetros  

 `pChainContext`  
 [in] O blob da chave pública CSP. Consulte a estrutura de [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .  
  
 `ppwszPublicKeyHash`  
 [out] Um ponteiro para WCHAR * para receber o token de chave pública com codificação hexadecimal.  
  
## <a name="return-value"></a>Valor Retornado  

 `S_OK` se a função for bem-sucedida; caso contrário, `S_FALSE`.  
  
## <a name="see-also"></a>Confira também

- [Authenticode](index.md)
