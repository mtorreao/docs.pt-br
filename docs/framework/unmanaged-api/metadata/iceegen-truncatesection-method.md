---
title: Método ICeeGen::TruncateSection
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 3005db62bba4089c669a00f62e3c1e62f9e1dae9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685676"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="f610d-102">Método ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="f610d-102">ICeeGen::TruncateSection Method</span></span>

<span data-ttu-id="f610d-103">Trunca a seção de código especificada pelo comprimento especificado.</span><span class="sxs-lookup"><span data-stu-id="f610d-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="f610d-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="f610d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f610d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f610d-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f610d-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f610d-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="f610d-107">no A seção a ser truncada.</span><span class="sxs-lookup"><span data-stu-id="f610d-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="f610d-108">no O comprimento, em bytes, pelo qual truncar a seção.</span><span class="sxs-lookup"><span data-stu-id="f610d-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f610d-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="f610d-109">Remarks</span></span>  

 <span data-ttu-id="f610d-110">Chame `TruncateSection` somente se você tiver requisitos de seção especiais que não são tratados por outros métodos.</span><span class="sxs-lookup"><span data-stu-id="f610d-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f610d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f610d-111">Requirements</span></span>  

 <span data-ttu-id="f610d-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f610d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f610d-113">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f610d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f610d-114">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f610d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f610d-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f610d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f610d-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="f610d-116">See also</span></span>

- [<span data-ttu-id="f610d-117">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="f610d-117">ICeeGen Interface</span></span>](iceegen-interface.md)
