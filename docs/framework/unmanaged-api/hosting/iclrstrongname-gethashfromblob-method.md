---
title: Método ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714803"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="77375-102">Método ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="77375-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="77375-103">Obtém um hash do assembly no endereço de memória especificado, usando o algoritmo de hash especificado.</span><span class="sxs-lookup"><span data-stu-id="77375-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77375-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="77375-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77375-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="77375-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="77375-106">no Um ponteiro para o endereço do bloco de memória com hash.</span><span class="sxs-lookup"><span data-stu-id="77375-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="77375-107">no O comprimento, em bytes, do bloco de memória.</span><span class="sxs-lookup"><span data-stu-id="77375-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="77375-108">[entrada, saída] Uma constante que especifica o algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="77375-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="77375-109">Use zero para o algoritmo padrão.</span><span class="sxs-lookup"><span data-stu-id="77375-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="77375-110">fora O buffer de hash retornado.</span><span class="sxs-lookup"><span data-stu-id="77375-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="77375-111">no O tamanho máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="77375-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="77375-112">fora O tamanho, em bytes, do retornado `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="77375-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77375-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="77375-113">Return Value</span></span>  

 <span data-ttu-id="77375-114">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="77375-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77375-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77375-115">Requirements</span></span>  

 <span data-ttu-id="77375-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77375-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77375-117">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="77375-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="77375-118">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77375-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77375-119">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77375-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77375-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="77375-120">See also</span></span>

- [<span data-ttu-id="77375-121">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="77375-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
