---
title: Função StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: e7292635ea0344f1c77c8d44908a9a811e464ff9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732301"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="d8592-102">Função StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="d8592-102">StrongNameCompareAssemblies Function</span></span>

<span data-ttu-id="d8592-103">Determina se dois assemblies diferem somente por suas assinaturas de nome forte.</span><span class="sxs-lookup"><span data-stu-id="d8592-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="d8592-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="d8592-104">This function has been deprecated.</span></span> <span data-ttu-id="d8592-105">Em vez disso, use o método [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d8592-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8592-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d8592-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8592-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d8592-107">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="d8592-108">no O caminho para o primeiro assembly.</span><span class="sxs-lookup"><span data-stu-id="d8592-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="d8592-109">no O caminho para o segundo assembly.</span><span class="sxs-lookup"><span data-stu-id="d8592-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="d8592-110">fora Um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d8592-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="d8592-111">`SN_CMP_DIFFERENT` (0)-especifica que os assemblies contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="d8592-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="d8592-112">`SN_CMP_IDENTICAL` (1)-especifica que os assemblies são exatamente iguais, incluindo suas assinaturas e soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="d8592-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="d8592-113">`SN_CMP_SIGONLY` (2)-especifica que os assemblies diferem somente por assinatura e soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="d8592-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8592-114">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="d8592-114">Return Value</span></span>  

 <span data-ttu-id="d8592-115">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="d8592-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8592-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8592-116">Requirements</span></span>  

 <span data-ttu-id="d8592-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8592-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8592-118">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d8592-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d8592-119">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8592-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8592-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8592-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8592-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="d8592-121">Remarks</span></span>  

 <span data-ttu-id="d8592-122">A assinatura de nome forte de um assembly consiste no nome de texto, versão, cultura e token de chave pública do assembly.</span><span class="sxs-lookup"><span data-stu-id="d8592-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="d8592-123">Se a `StrongNameCompareAssemblies` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="d8592-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8592-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="d8592-124">See also</span></span>

- [<span data-ttu-id="d8592-125">Método StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="d8592-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="d8592-126">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d8592-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
