---
title: Método ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: 9ba50616b25f9c7c592f19947c82a890ae6b5a4a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671675"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="c7a24-102">Método ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="c7a24-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>

<span data-ttu-id="c7a24-103">Gera um novo par de chaves pública/privada com o tamanho de chave especificado, para uso de nome forte.</span><span class="sxs-lookup"><span data-stu-id="c7a24-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a24-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c7a24-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a24-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c7a24-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="c7a24-106">no O nome do contêiner de chave solicitado.</span><span class="sxs-lookup"><span data-stu-id="c7a24-106">[in] The requested key container name.</span></span> <span data-ttu-id="c7a24-107">`wszKeyContainer` deve ser uma cadeia de caracteres não vazia ou NULL para gerar um nome temporário.</span><span class="sxs-lookup"><span data-stu-id="c7a24-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c7a24-108">no Um valor que especifica se a chave deve ser desregistrada.</span><span class="sxs-lookup"><span data-stu-id="c7a24-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="c7a24-109">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="c7a24-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="c7a24-110">0x00000000-usado quando `wszKeyContainer` é nulo para gerar um nome de contêiner de chave temporário.</span><span class="sxs-lookup"><span data-stu-id="c7a24-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="c7a24-111">0x00000001 ( `SN_LEAVE_KEY` ) – especifica que a chave deve ser registrada.</span><span class="sxs-lookup"><span data-stu-id="c7a24-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="c7a24-112">no O tamanho solicitado da chave, em bits.</span><span class="sxs-lookup"><span data-stu-id="c7a24-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="c7a24-113">fora O par de chaves pública/privada retornado.</span><span class="sxs-lookup"><span data-stu-id="c7a24-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="c7a24-114">fora O tamanho, em bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="c7a24-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7a24-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="c7a24-115">Return Value</span></span>  

 <span data-ttu-id="c7a24-116">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="c7a24-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7a24-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7a24-117">Remarks</span></span>  

 <span data-ttu-id="c7a24-118">O .NET Framework versões 1,0 e 1,1 exigem um `dwKeySize` de 1024 bits para assinar um assembly com um nome forte; a versão 2,0 adiciona suporte para chaves de bits de 2048.</span><span class="sxs-lookup"><span data-stu-id="c7a24-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="c7a24-119">Depois que a chave for recuperada, você deverá chamar o método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar a memória alocada.</span><span class="sxs-lookup"><span data-stu-id="c7a24-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a24-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7a24-120">Requirements</span></span>  

 <span data-ttu-id="c7a24-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7a24-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7a24-122">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="c7a24-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c7a24-123">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7a24-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7a24-124">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7a24-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a24-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="c7a24-125">See also</span></span>

- [<span data-ttu-id="c7a24-126">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="c7a24-126">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="c7a24-127">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c7a24-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
