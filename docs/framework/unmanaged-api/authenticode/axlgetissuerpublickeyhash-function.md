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
# <a name="_axlgetissuerpublickeyhash-function"></a><span data-ttu-id="bf0b9-102">\_Função AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="bf0b9-102">\_AxlGetIssuerPublicKeyHash Function</span></span>

<span data-ttu-id="bf0b9-103">Recupera o hash SHA-1 da chave pública associada à chave privada usada para assinar o certificado especificado.</span><span class="sxs-lookup"><span data-stu-id="bf0b9-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0b9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bf0b9-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf0b9-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bf0b9-105">Parameters</span></span>  

 `pChainContext`  
 <span data-ttu-id="bf0b9-106">[in] O blob da chave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="bf0b9-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="bf0b9-107">Consulte a estrutura de [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .</span><span class="sxs-lookup"><span data-stu-id="bf0b9-107">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="bf0b9-108">[out] Um ponteiro para WCHAR \* para receber o token de chave pública com codificação hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="bf0b9-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf0b9-109">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="bf0b9-109">Return Value</span></span>  

 <span data-ttu-id="bf0b9-110">`S_OK` se a função for bem-sucedida; caso contrário, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="bf0b9-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0b9-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf0b9-111">See also</span></span>

- [<span data-ttu-id="bf0b9-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="bf0b9-112">Authenticode</span></span>](index.md)
