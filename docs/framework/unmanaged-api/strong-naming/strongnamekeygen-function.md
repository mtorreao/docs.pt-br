---
title: Função StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: 4844701784a3e6a1008a5deb2bdff3b3ba47aa7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691403"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="620d7-102">Função StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="620d7-102">StrongNameKeyGen Function</span></span>

<span data-ttu-id="620d7-103">Cria um novo par de chaves públicas/privadas para uso de nome forte.</span><span class="sxs-lookup"><span data-stu-id="620d7-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="620d7-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="620d7-104">This function has been deprecated.</span></span> <span data-ttu-id="620d7-105">Em vez disso, use o método [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .</span><span class="sxs-lookup"><span data-stu-id="620d7-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620d7-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="620d7-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="620d7-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="620d7-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="620d7-108">no O nome do contêiner de chave solicitado.</span><span class="sxs-lookup"><span data-stu-id="620d7-108">[in] The requested key container name.</span></span> <span data-ttu-id="620d7-109">`wszKeyContainer` deve ser uma cadeia de caracteres não vazia ou NULL para gerar um nome temporário.</span><span class="sxs-lookup"><span data-stu-id="620d7-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="620d7-110">no Especifica se a chave deve ser desregistrada.</span><span class="sxs-lookup"><span data-stu-id="620d7-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="620d7-111">Os seguintes valores têm suporte:</span><span class="sxs-lookup"><span data-stu-id="620d7-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="620d7-112">0x00000000-usado quando `wszKeyContainer` é nulo para gerar um nome de contêiner de chave temporário.</span><span class="sxs-lookup"><span data-stu-id="620d7-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="620d7-113">0x00000001 ( `SN_LEAVE_KEY` ) – especifica que a chave deve ser registrada.</span><span class="sxs-lookup"><span data-stu-id="620d7-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="620d7-114">fora O par de chaves pública/privada retornado.</span><span class="sxs-lookup"><span data-stu-id="620d7-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="620d7-115">fora O tamanho, em bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="620d7-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="620d7-116">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="620d7-116">Return Value</span></span>  

 <span data-ttu-id="620d7-117">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="620d7-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="620d7-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="620d7-118">Remarks</span></span>  

 <span data-ttu-id="620d7-119">A `StrongNameKeyGen` função cria uma chave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="620d7-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="620d7-120">Depois que a chave for recuperada, você deverá chamar a função [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar a memória alocada.</span><span class="sxs-lookup"><span data-stu-id="620d7-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="620d7-121">Se a `StrongNameKeyGen` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="620d7-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620d7-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="620d7-122">Requirements</span></span>  

 <span data-ttu-id="620d7-123">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620d7-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620d7-124">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="620d7-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="620d7-125">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="620d7-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="620d7-126">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="620d7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620d7-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="620d7-127">See also</span></span>

- [<span data-ttu-id="620d7-128">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="620d7-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="620d7-129">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="620d7-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="620d7-130">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="620d7-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
