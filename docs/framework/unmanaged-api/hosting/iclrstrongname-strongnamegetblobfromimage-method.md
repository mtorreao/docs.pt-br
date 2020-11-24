---
title: Método ICLRStrongName::StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: ad5fa510a17a3ce823ff90c4131b349b0d9efd39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671740"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="3d2dd-102">Método ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="3d2dd-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>

<span data-ttu-id="3d2dd-103">Obtém uma representação binária da imagem do assembly no endereço de memória especificado.</span><span class="sxs-lookup"><span data-stu-id="3d2dd-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d2dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d2dd-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d2dd-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3d2dd-105">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="3d2dd-106">no O endereço de memória do manifesto do assembly mapeado.</span><span class="sxs-lookup"><span data-stu-id="3d2dd-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3d2dd-107">no O tamanho, em bytes, da imagem em `pbBase` .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3d2dd-108">no Um buffer para conter a representação binária da imagem.</span><span class="sxs-lookup"><span data-stu-id="3d2dd-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3d2dd-109">[entrada, saída] O tamanho máximo solicitado, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3d2dd-110">No retorno, o tamanho real, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="3d2dd-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d2dd-111">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="3d2dd-111">Return Value</span></span>  

 <span data-ttu-id="3d2dd-112">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="3d2dd-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d2dd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d2dd-113">Requirements</span></span>  

 <span data-ttu-id="3d2dd-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d2dd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d2dd-115">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3d2dd-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3d2dd-116">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d2dd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d2dd-117">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d2dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2dd-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="3d2dd-118">See also</span></span>

- [<span data-ttu-id="3d2dd-119">Método StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="3d2dd-119">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="3d2dd-120">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3d2dd-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
