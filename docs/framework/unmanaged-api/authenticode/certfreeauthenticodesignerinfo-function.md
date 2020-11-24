---
title: Função CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674171"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="b9d11-102">Função CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="b9d11-102">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="b9d11-103">Libera recursos alocados para a estrutura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b9d11-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9d11-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b9d11-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9d11-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b9d11-105">Parameters</span></span>  

 `pSignerInfo`  
 <span data-ttu-id="b9d11-106">[in, out] Informações de signatário a serem liberadas.</span><span class="sxs-lookup"><span data-stu-id="b9d11-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="b9d11-107">Consulte a estrutura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="b9d11-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9d11-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b9d11-108">Return Value</span></span>  

 <span data-ttu-id="b9d11-109">`S_OK` se a função for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b9d11-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b9d11-110">Caso contrário, retornará um código de erro.</span><span class="sxs-lookup"><span data-stu-id="b9d11-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d11-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9d11-111">See also</span></span>

- [<span data-ttu-id="b9d11-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b9d11-112">Authenticode</span></span>](index.md)
