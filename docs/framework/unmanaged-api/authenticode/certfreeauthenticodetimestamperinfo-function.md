---
title: Função CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674158"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="1fda3-102">Função CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="1fda3-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="1fda3-103">Libera recursos alocados para a estrutura de [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="1fda3-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fda3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1fda3-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fda3-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1fda3-105">Parameters</span></span>  

 `pTimestamperInfo`  
 <span data-ttu-id="1fda3-106">[in, out] As informações do carimbo de data/hora que será liberado.</span><span class="sxs-lookup"><span data-stu-id="1fda3-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="1fda3-107">Consulte a estrutura de [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="1fda3-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fda3-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="1fda3-108">Return Value</span></span>  

 <span data-ttu-id="1fda3-109">`S_OK` se a função for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="1fda3-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="1fda3-110">Caso contrário, retornará um código de erro.</span><span class="sxs-lookup"><span data-stu-id="1fda3-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fda3-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="1fda3-111">See also</span></span>

- [<span data-ttu-id="1fda3-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1fda3-112">Authenticode</span></span>](index.md)
