---
title: Função StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 89556cf0e1ef65c35278a526e10fc791063ea2c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708342"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="4dac6-102">Função StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="4dac6-102">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="4dac6-103">Obtém um token que representa uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="4dac6-103">Gets a token representing a public key.</span></span> <span data-ttu-id="4dac6-104">Um token de nome forte é a forma abreviada de uma chave pública.</span><span class="sxs-lookup"><span data-stu-id="4dac6-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="4dac6-105">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="4dac6-105">This function has been deprecated.</span></span> <span data-ttu-id="4dac6-106">Em vez disso, use o método [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4dac6-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dac6-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4dac6-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dac6-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4dac6-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="4dac6-109">no Uma estrutura do tipo [PublicKeyBlob](publickeyblob-structure.md) que contém a parte pública do par de chaves usado para gerar a assinatura de nome forte.</span><span class="sxs-lookup"><span data-stu-id="4dac6-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="4dac6-110">no O tamanho, em bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="4dac6-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="4dac6-111">fora O token de nome forte correspondente à chave passada `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="4dac6-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="4dac6-112">O Common Language Runtime aloca a memória na qual retornar o token.</span><span class="sxs-lookup"><span data-stu-id="4dac6-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="4dac6-113">O chamador deve liberar essa memória usando a função [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4dac6-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="4dac6-114">fora O tamanho, em bytes, do token de nome forte retornado.</span><span class="sxs-lookup"><span data-stu-id="4dac6-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dac6-115">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="4dac6-115">Return Value</span></span>  

 <span data-ttu-id="4dac6-116">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="4dac6-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dac6-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="4dac6-117">Remarks</span></span>  

 <span data-ttu-id="4dac6-118">Um token de nome forte é a forma abreviada de uma chave pública usada para economizar espaço ao armazenar informações de chave em metadados.</span><span class="sxs-lookup"><span data-stu-id="4dac6-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="4dac6-119">Especificamente, tokens de nome forte são usados em referências de assembly para fazer referência ao assembly dependente.</span><span class="sxs-lookup"><span data-stu-id="4dac6-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="4dac6-120">Se a `StrongNameTokenFromPublicKey` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="4dac6-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dac6-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dac6-121">Requirements</span></span>  

 <span data-ttu-id="4dac6-122">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dac6-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dac6-123">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="4dac6-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4dac6-124">**Biblioteca:** Incluído como um recurso no mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4dac6-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="4dac6-125">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dac6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dac6-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="4dac6-126">See also</span></span>

- [<span data-ttu-id="4dac6-127">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="4dac6-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="4dac6-128">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="4dac6-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="4dac6-129">Estrutura PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="4dac6-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
