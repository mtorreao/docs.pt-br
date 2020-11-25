---
title: Método ICeeGen::GetMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
ms.openlocfilehash: e9c2dab9f30be6e5eea8f6570b297f8df11b6fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715323"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="95727-102">Método ICeeGen::GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="95727-102">ICeeGen::GetMethodBuffer Method</span></span>

<span data-ttu-id="95727-103">Obtém um buffer do tamanho apropriado para o método no endereço virtual relativo especificado.</span><span class="sxs-lookup"><span data-stu-id="95727-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="95727-104">Este método é obsoleto e não deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="95727-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95727-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="95727-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95727-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="95727-106">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="95727-107">no O endereço virtual relativo do método para o qual retornar um buffer.</span><span class="sxs-lookup"><span data-stu-id="95727-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="95727-108">fora Um ponteiro para o buffer retornado.</span><span class="sxs-lookup"><span data-stu-id="95727-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95727-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95727-109">Requirements</span></span>  

 <span data-ttu-id="95727-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95727-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95727-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95727-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95727-112">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95727-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95727-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95727-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95727-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="95727-114">See also</span></span>

- [<span data-ttu-id="95727-115">Interface ICeeGen</span><span class="sxs-lookup"><span data-stu-id="95727-115">ICeeGen Interface</span></span>](iceegen-interface.md)
