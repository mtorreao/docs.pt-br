---
title: Método ICLRStrongName::StrongNameHashSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 6ee87fdbf75d4a07a7337a1c9fdc58a06191b992
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674809"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="b61d0-102">Método ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="b61d0-102">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="b61d0-103">Obtém o tamanho do buffer necessário para um hash, usando o algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="b61d0-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61d0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b61d0-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b61d0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b61d0-105">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="b61d0-106">no O algoritmo de hash usado para calcular o tamanho do buffer.</span><span class="sxs-lookup"><span data-stu-id="b61d0-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="b61d0-107">fora O tamanho do buffer retornado, em bytes.</span><span class="sxs-lookup"><span data-stu-id="b61d0-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b61d0-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b61d0-108">Return Value</span></span>  

 <span data-ttu-id="b61d0-109">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="b61d0-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b61d0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b61d0-110">Requirements</span></span>  

 <span data-ttu-id="b61d0-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b61d0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b61d0-112">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b61d0-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b61d0-113">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b61d0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b61d0-114">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b61d0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61d0-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="b61d0-115">See also</span></span>

- [<span data-ttu-id="b61d0-116">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b61d0-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
