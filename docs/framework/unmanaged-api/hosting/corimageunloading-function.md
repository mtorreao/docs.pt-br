---
title: Função _CorImageUnloading
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723149"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="f3440-102">Função _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="f3440-102">_CorImageUnloading Function</span></span>

<span data-ttu-id="f3440-103">Notifica o carregador quando as imagens do módulo gerenciado são descarregadas.</span><span class="sxs-lookup"><span data-stu-id="f3440-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="f3440-104">Esta função não está implementada.</span><span class="sxs-lookup"><span data-stu-id="f3440-104">This function is not implemented.</span></span> <span data-ttu-id="f3440-105">Se chamado, ele retornará E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f3440-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3440-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f3440-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3440-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f3440-107">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="f3440-108">no Um ponteiro para o local inicial da imagem a ser descarregada.</span><span class="sxs-lookup"><span data-stu-id="f3440-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3440-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3440-109">Requirements</span></span>  

 <span data-ttu-id="f3440-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3440-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3440-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f3440-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3440-112">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f3440-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f3440-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3440-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3440-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="f3440-114">See also</span></span>

- [<span data-ttu-id="f3440-115">Funções estáticas globais de metadados</span><span class="sxs-lookup"><span data-stu-id="f3440-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
