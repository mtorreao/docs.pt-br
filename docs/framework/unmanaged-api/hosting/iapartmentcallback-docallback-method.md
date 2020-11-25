---
title: Método IApartmentCallback::DoCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: e3031bf123ff9107b4cebc0723f1be0d423bdaec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721745"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="7d8b7-102">Método IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="7d8b7-102">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="7d8b7-103">Executa a função especificada em um apartamento.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8b7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7d8b7-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8b7-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7d8b7-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="7d8b7-106">no Um ponteiro para a função a ser executada dentro do apartamento.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="7d8b7-107">no Um ponteiro para o argumento da função.</span><span class="sxs-lookup"><span data-stu-id="7d8b7-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8b7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d8b7-108">Requirements</span></span>  

 <span data-ttu-id="7d8b7-109">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d8b7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8b7-110">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7d8b7-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d8b7-111">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d8b7-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d8b7-112">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8b7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8b7-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="7d8b7-113">See also</span></span>

- [<span data-ttu-id="7d8b7-114">Interface IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="7d8b7-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
