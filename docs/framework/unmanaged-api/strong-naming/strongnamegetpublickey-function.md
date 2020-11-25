---
title: Função StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710968"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="6dbd9-102">Função StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="6dbd9-102">StrongNameGetPublicKey Function</span></span>

<span data-ttu-id="6dbd9-103">Obtém a chave pública de um par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="6dbd9-104">O par de chaves pode ser fornecido como um nome de contêiner de chave em um CSP (provedor de serviços de criptografia) ou como uma coleção bruta de bytes.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="6dbd9-105">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-105">This function has been deprecated.</span></span> <span data-ttu-id="6dbd9-106">Em vez disso, use o método [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbd9-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6dbd9-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dbd9-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6dbd9-108">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="6dbd9-109">no O nome do contêiner de chave que contém o par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="6dbd9-110">Se `pbKeyBlob` for NULL, `szKeyContainer` deve especificar um contêiner válido no CSP.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="6dbd9-111">Nesse caso, `StrongNameGetPublicKey` o extrai a chave pública do par de chaves armazenado no contêiner.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="6dbd9-112">Se `pbKeyBlob` não for NULL, o par de chaves será considerado contido no BLOB (objeto binário grande) de chave.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="6dbd9-113">As chaves devem ter chaves de assinatura de 1024 bits Rivest-Shamir-Adleman (RSA).</span><span class="sxs-lookup"><span data-stu-id="6dbd9-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="6dbd9-114">Não há suporte para nenhum outro tipo de chave no momento.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6dbd9-115">no Um ponteiro para o par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="6dbd9-116">Esse par está no formato criado pela função do Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="6dbd9-117">Se `pbKeyBlob` for NULL, o contêiner de chave especificado por `szKeyContainer` será considerado para conter o par de chaves.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6dbd9-118">no O tamanho, em bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="6dbd9-119">fora O BLOB de chave pública retornado.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="6dbd9-120">O `ppbPublicKeyBlob` parâmetro é alocado pelo Common Language Runtime e retornado ao chamador.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="6dbd9-121">O chamador deve liberar a memória usando a função [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="6dbd9-122">fora O tamanho do BLOB de chave pública retornado.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dbd9-123">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="6dbd9-123">Return Value</span></span>  

 <span data-ttu-id="6dbd9-124">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dbd9-125">Comentários</span><span class="sxs-lookup"><span data-stu-id="6dbd9-125">Remarks</span></span>  

 <span data-ttu-id="6dbd9-126">A chave pública está contida em uma estrutura [PublicKeyBlob](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="6dbd9-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="6dbd9-127">Se a `StrongNameGetPublicKey` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="6dbd9-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbd9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dbd9-128">Requirements</span></span>  

 <span data-ttu-id="6dbd9-129">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dbd9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbd9-130">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="6dbd9-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6dbd9-131">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dbd9-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6dbd9-132">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbd9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbd9-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="6dbd9-133">See also</span></span>

- [<span data-ttu-id="6dbd9-134">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="6dbd9-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="6dbd9-135">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="6dbd9-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="6dbd9-136">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6dbd9-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="6dbd9-137">Estrutura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="6dbd9-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
