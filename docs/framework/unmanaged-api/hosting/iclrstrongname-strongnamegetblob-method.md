---
title: Método ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 824dcf89bacec27ced7cc431a9646d00fb879430
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674665"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="396af-102">Método ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="396af-102">ICLRStrongName::StrongNameGetBlob Method</span></span>

<span data-ttu-id="396af-103">Preenche o buffer especificado com a representação binária do arquivo executável no endereço especificado.</span><span class="sxs-lookup"><span data-stu-id="396af-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="396af-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="396af-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="396af-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="396af-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="396af-106">no Um caminho válido para o arquivo executável a ser carregado.</span><span class="sxs-lookup"><span data-stu-id="396af-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="396af-107">no O buffer no qual carregar o arquivo executável.</span><span class="sxs-lookup"><span data-stu-id="396af-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="396af-108">[entrada, saída] O tamanho máximo solicitado, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="396af-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="396af-109">No retorno, o tamanho real, em bytes, de `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="396af-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="396af-110">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="396af-110">Return Value</span></span>  

 <span data-ttu-id="396af-111">`S_OK` Se o método foi concluído com êxito; caso contrário, um valor HRESULT que indica falha (consulte [valores de HRESULT comuns](/windows/win32/seccrypto/common-hresult-values) para uma lista).</span><span class="sxs-lookup"><span data-stu-id="396af-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="396af-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="396af-112">Requirements</span></span>  

 <span data-ttu-id="396af-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="396af-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="396af-114">**Cabeçalho:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="396af-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="396af-115">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="396af-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="396af-116">**.NET Framework versões:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="396af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396af-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="396af-117">See also</span></span>

- [<span data-ttu-id="396af-118">Método StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="396af-118">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="396af-119">Interface ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="396af-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
