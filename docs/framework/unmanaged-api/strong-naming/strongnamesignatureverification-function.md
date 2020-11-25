---
title: Função StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: c47d693f450b9cafcb4c8a388c8c38afcd2094e6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725710"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="4765f-102">Função StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="4765f-102">StrongNameSignatureVerification Function</span></span>

<span data-ttu-id="4765f-103">Obtém um valor que indica se o manifesto do assembly no caminho fornecido contém uma assinatura de nome forte, que é verificada de acordo com os sinalizadores especificados.</span><span class="sxs-lookup"><span data-stu-id="4765f-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="4765f-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="4765f-104">This function has been deprecated.</span></span> <span data-ttu-id="4765f-105">Em vez disso, use o método [ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4765f-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4765f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4765f-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4765f-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4765f-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="4765f-108">no O caminho para o arquivo executável portátil (. dll ou. exe) para o assembly verificar.</span><span class="sxs-lookup"><span data-stu-id="4765f-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4765f-109">no Sinalizadores para modificar o comportamento de verificação.</span><span class="sxs-lookup"><span data-stu-id="4765f-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="4765f-110">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="4765f-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="4765f-111">`SN_INFLAG_FORCE_VER` (0x00000001) – força a verificação mesmo que seja necessário substituir as configurações do registro.</span><span class="sxs-lookup"><span data-stu-id="4765f-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="4765f-112">`SN_INFLAG_INSTALL` (0x00000002) – especifica que esta é a primeira vez que o manifesto é verificado.</span><span class="sxs-lookup"><span data-stu-id="4765f-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="4765f-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) – especifica que o cache permitirá acesso somente aos usuários que têm privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="4765f-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="4765f-114">`SN_INFLAG_USER_ACCESS` (0x00000008) – especifica que o assembly será acessível somente para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="4765f-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="4765f-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) – especifica que o cache não oferecerá nenhuma garantia de restrição de acesso.</span><span class="sxs-lookup"><span data-stu-id="4765f-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="4765f-116">`SN_INFLAG_RUNTIME` (0x80000000)-reservado para depuração interna.</span><span class="sxs-lookup"><span data-stu-id="4765f-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4765f-117">fora Sinalizadores que indicam se a assinatura de nome forte foi verificada.</span><span class="sxs-lookup"><span data-stu-id="4765f-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="4765f-118">Há suporte para o seguinte valor:</span><span class="sxs-lookup"><span data-stu-id="4765f-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="4765f-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001)-esse valor é definido como `false` para especificar que a verificação foi bem-sucedida devido a configurações do registro.</span><span class="sxs-lookup"><span data-stu-id="4765f-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4765f-120">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="4765f-120">Return Value</span></span>  

 <span data-ttu-id="4765f-121">`true` se a verificação foi bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="4765f-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4765f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4765f-122">Requirements</span></span>  

 <span data-ttu-id="4765f-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4765f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4765f-124">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="4765f-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4765f-125">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4765f-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4765f-126">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4765f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4765f-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="4765f-127">See also</span></span>

- [<span data-ttu-id="4765f-128">Método StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="4765f-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="4765f-129">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="4765f-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="4765f-130">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="4765f-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
