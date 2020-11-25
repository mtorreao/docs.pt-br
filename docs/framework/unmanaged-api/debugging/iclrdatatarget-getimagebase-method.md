---
title: Método ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703571"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="bbc9d-102">Método ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="bbc9d-102">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="bbc9d-103">Obtém o endereço de memória base da imagem especificada.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc9d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bbc9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbc9d-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="bbc9d-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="bbc9d-106">no O nome do arquivo da imagem, incluindo seu caminho.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="bbc9d-107">fora Um ponteiro para um CLRDATA_ADDRESS que armazena o endereço base da imagem.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbc9d-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="bbc9d-108">Remarks</span></span>  

 <span data-ttu-id="bbc9d-109">O nome do arquivo de imagem pode ou não ter um caminho.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="bbc9d-110">Se um caminho for especificado, a correspondência será feita no caminho inteiro; caso contrário, a correspondência será feita apenas no nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="bbc9d-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbc9d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbc9d-111">Requirements</span></span>  

 <span data-ttu-id="bbc9d-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbc9d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbc9d-113">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="bbc9d-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bbc9d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbc9d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbc9d-115">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbc9d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc9d-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="bbc9d-116">See also</span></span>

- [<span data-ttu-id="bbc9d-117">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="bbc9d-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
