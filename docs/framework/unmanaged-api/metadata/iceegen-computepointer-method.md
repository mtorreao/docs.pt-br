---
title: Método ICeeGen::ComputePointer
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 41a3b9c77fc766b2fa39b406dedbb3203cc97ad9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715466"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="a3323-102">Método ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="a3323-102">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="a3323-103">Determina o buffer para a seção de código especificada.</span><span class="sxs-lookup"><span data-stu-id="a3323-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="a3323-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="a3323-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3323-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a3323-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3323-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a3323-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="a3323-107">no A seção de código para a qual retornar um buffer.</span><span class="sxs-lookup"><span data-stu-id="a3323-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="a3323-108">no O endereço virtual relativo do método para o qual obter um ponteiro.</span><span class="sxs-lookup"><span data-stu-id="a3323-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="a3323-109">fora Um ponteiro para o buffer retornado.</span><span class="sxs-lookup"><span data-stu-id="a3323-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3323-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3323-110">Requirements</span></span>  

 <span data-ttu-id="a3323-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3323-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3323-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a3323-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3323-113">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3323-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3323-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3323-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3323-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3323-115">See also</span></span>

- [<span data-ttu-id="a3323-116">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="a3323-116">ICeeGen Interface</span></span>](iceegen-interface.md)
