---
title: Método ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: c727d4524bc40ab90eee90faf16788140a73ad9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677655"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="b935a-102">Método ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="b935a-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>

<span data-ttu-id="b935a-103">Obtém um token que representa uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="b935a-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="b935a-104">Um token de nome forte é a forma abreviada de uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="b935a-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b935a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b935a-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b935a-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b935a-106">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="b935a-107">no Uma estrutura do tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contém a parte pública do par de chaves usado para gerar a assinatura de nome forte.</span><span class="sxs-lookup"><span data-stu-id="b935a-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="b935a-108">no O tamanho, em bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b935a-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="b935a-109">fora O token de nome forte correspondente à chave passada `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b935a-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="b935a-110">O Common Language Runtime aloca a memória na qual retornar o token.</span><span class="sxs-lookup"><span data-stu-id="b935a-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="b935a-111">O chamador deve liberar essa memória usando o método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b935a-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="b935a-112">fora O tamanho, em bytes, do token de nome forte retornado.</span><span class="sxs-lookup"><span data-stu-id="b935a-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b935a-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="b935a-113">Return Value</span></span>  

 <span data-ttu-id="b935a-114">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="b935a-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b935a-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="b935a-115">Remarks</span></span>  

 <span data-ttu-id="b935a-116">Um token de nome forte é a forma abreviada de uma chave pública que é usada para economizar espaço ao armazenar informações de chave em metadados.</span><span class="sxs-lookup"><span data-stu-id="b935a-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="b935a-117">Especificamente, tokens de nome forte são usados em referências de assembly para fazer referência ao assembly dependente.</span><span class="sxs-lookup"><span data-stu-id="b935a-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b935a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b935a-118">Requirements</span></span>  

 <span data-ttu-id="b935a-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b935a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b935a-120">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b935a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b935a-121">**Biblioteca:** Incluído como um recurso no mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b935a-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="b935a-122">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b935a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b935a-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="b935a-123">See also</span></span>

- [<span data-ttu-id="b935a-124">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="b935a-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="b935a-125">Estrutura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="b935a-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="b935a-126">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b935a-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
