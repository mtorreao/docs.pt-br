---
title: Função StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
ms.openlocfilehash: 96dae519d73505a30c8593e9883da7338525ea2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708511"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="54d33-102">Função StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="54d33-102">StrongNameSignatureGenerationEx Function</span></span>

<span data-ttu-id="54d33-103">Gera uma assinatura de nome forte para o assembly especificado, de acordo com os sinalizadores especificados.</span><span class="sxs-lookup"><span data-stu-id="54d33-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="54d33-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="54d33-104">This function has been deprecated.</span></span> <span data-ttu-id="54d33-105">Em vez disso, use o método [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="54d33-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d33-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="54d33-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54d33-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="54d33-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="54d33-108">no O caminho para o arquivo que contém o manifesto do assembly para o qual a assinatura de nome forte será gerada.</span><span class="sxs-lookup"><span data-stu-id="54d33-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="54d33-109">no O nome do contêiner de chave que contém o par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="54d33-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="54d33-110">Se `pbKeyBlob` for NULL, `wszKeyContainer` deve especificar um contêiner válido no CSP (provedor de serviços de criptografia).</span><span class="sxs-lookup"><span data-stu-id="54d33-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="54d33-111">Nesse caso, o par de chaves armazenado no contêiner é usado para assinar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="54d33-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="54d33-112">Se `pbKeyBlob` não for NULL, o par de chaves será considerado contido no BLOB (objeto binário grande) de chave.</span><span class="sxs-lookup"><span data-stu-id="54d33-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="54d33-113">no Um ponteiro para o par de chaves pública/privada.</span><span class="sxs-lookup"><span data-stu-id="54d33-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="54d33-114">Esse par está no formato criado pela função do Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="54d33-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="54d33-115">Se `pbKeyBlob` for NULL, o contêiner de chave especificado por `wszKeyContainer` será considerado para conter o par de chaves.</span><span class="sxs-lookup"><span data-stu-id="54d33-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="54d33-116">no O tamanho, em bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="54d33-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="54d33-117">fora Um ponteiro para o local no qual o Common Language Runtime retorna a assinatura.</span><span class="sxs-lookup"><span data-stu-id="54d33-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="54d33-118">Se `ppbSignatureBlob` for NULL, o tempo de execução armazenará a assinatura no arquivo especificado por `wszFilePath` .</span><span class="sxs-lookup"><span data-stu-id="54d33-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="54d33-119">Se `ppbSignatureBlob` não for NULL, o common language runtime aloca espaço para retornar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="54d33-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="54d33-120">O chamador deve liberar esse espaço usando a função [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="54d33-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="54d33-121">fora O tamanho, em bytes, da assinatura retornada.</span><span class="sxs-lookup"><span data-stu-id="54d33-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="54d33-122">no Um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="54d33-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="54d33-123">`SN_SIGN_ALL_FILES` (0x00000001) – recomputar todos os hashes para módulos vinculados.</span><span class="sxs-lookup"><span data-stu-id="54d33-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="54d33-124">`SN_TEST_SIGN` (0x00000002)-testar o assembly.</span><span class="sxs-lookup"><span data-stu-id="54d33-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54d33-125">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="54d33-125">Return Value</span></span>  

 <span data-ttu-id="54d33-126">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="54d33-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54d33-127">Comentários</span><span class="sxs-lookup"><span data-stu-id="54d33-127">Remarks</span></span>  

 <span data-ttu-id="54d33-128">Especifique NULL para `wszFilePath` para calcular o tamanho da assinatura sem criar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="54d33-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="54d33-129">A assinatura pode ser armazenada diretamente no arquivo ou retornada ao chamador.</span><span class="sxs-lookup"><span data-stu-id="54d33-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="54d33-130">Se `SN_SIGN_ALL_FILES` for especificado, mas uma chave pública não estiver incluída ( `pbKeyBlob` e `wszFilePath` forem nulas), os hashes para módulos vinculados serão recalculados, mas o assembly não será assinado novamente.</span><span class="sxs-lookup"><span data-stu-id="54d33-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="54d33-131">Se `SN_TEST_SIGN` for especificado, o cabeçalho de Common Language Runtime não será modificado para indicar que o assembly é assinado com um nome forte.</span><span class="sxs-lookup"><span data-stu-id="54d33-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="54d33-132">Se a `StrongNameSignatureGenerationEx` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="54d33-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d33-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54d33-133">Requirements</span></span>  

 <span data-ttu-id="54d33-134">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54d33-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d33-135">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="54d33-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="54d33-136">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54d33-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54d33-137">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d33-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d33-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="54d33-138">See also</span></span>

- [<span data-ttu-id="54d33-139">Método StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="54d33-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="54d33-140">Método StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="54d33-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="54d33-141">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="54d33-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
