---
title: Função StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 3a84221f94bad76d69f0dc67fe695ada3f3862f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732236"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="7f398-102">Função StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="7f398-102">StrongNameGetBlobFromImage Function</span></span>

<span data-ttu-id="7f398-103">Obtém uma representação binária da imagem do assembly no endereço de memória especificado.</span><span class="sxs-lookup"><span data-stu-id="7f398-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="7f398-104">Esta função foi preterida.</span><span class="sxs-lookup"><span data-stu-id="7f398-104">This function has been deprecated.</span></span> <span data-ttu-id="7f398-105">Em vez disso, use o método [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7f398-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f398-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7f398-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f398-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7f398-107">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="7f398-108">no O endereço de memória do manifesto do assembly mapeado.</span><span class="sxs-lookup"><span data-stu-id="7f398-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7f398-109">no O tamanho, em bytes, da imagem em `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="7f398-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="7f398-110">no Um buffer para conter a representação binária da imagem.</span><span class="sxs-lookup"><span data-stu-id="7f398-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="7f398-111">[entrada, saída] O tamanho máximo solicitado, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="7f398-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="7f398-112">No retorno, o tamanho real, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="7f398-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f398-113">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="7f398-113">Return Value</span></span>  

 <span data-ttu-id="7f398-114">`true` após a conclusão bem-sucedida; caso contrário, `false` .</span><span class="sxs-lookup"><span data-stu-id="7f398-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f398-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="7f398-115">Remarks</span></span>  

 <span data-ttu-id="7f398-116">Se a `StrongNameGetBlobFromImage` função não for concluída com êxito, chame a função [StrongNameErrorInfo](strongnameerrorinfo-function.md) para recuperar o último erro gerado.</span><span class="sxs-lookup"><span data-stu-id="7f398-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f398-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f398-117">Requirements</span></span>  

 <span data-ttu-id="7f398-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f398-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f398-119">**Cabeçalho:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="7f398-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7f398-120">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f398-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f398-121">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f398-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f398-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="7f398-122">See also</span></span>

- [<span data-ttu-id="7f398-123">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="7f398-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="7f398-124">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="7f398-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="7f398-125">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7f398-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
