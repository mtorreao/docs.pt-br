---
title: Método ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: e1849eb95401e3637a1fd1b00715332f9886071e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715505"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="8c11b-102">Método ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="8c11b-102">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="8c11b-103">Cria um buffer do tamanho especificado para um método e Obtém o endereço virtual relativo do método.</span><span class="sxs-lookup"><span data-stu-id="8c11b-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="8c11b-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="8c11b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c11b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8c11b-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c11b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8c11b-106">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="8c11b-107">no O comprimento do buffer a ser criado.</span><span class="sxs-lookup"><span data-stu-id="8c11b-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="8c11b-108">fora O buffer retornado.</span><span class="sxs-lookup"><span data-stu-id="8c11b-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="8c11b-109">fora O endereço virtual relativo do método.</span><span class="sxs-lookup"><span data-stu-id="8c11b-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c11b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c11b-110">Requirements</span></span>  

 <span data-ttu-id="8c11b-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c11b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c11b-112">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8c11b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c11b-113">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c11b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c11b-114">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c11b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c11b-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c11b-115">See also</span></span>

- [<span data-ttu-id="8c11b-116">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="8c11b-116">ICeeGen Interface</span></span>](iceegen-interface.md)
