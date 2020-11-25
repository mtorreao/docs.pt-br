---
title: Método ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 4824fcfc53bae6c81760a23f76e83fb8ae7efd79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715804"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="ed167-102">Método ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="ed167-102">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="ed167-103">Define a interface de retorno de chamada a ser usada pelo coletor de lixo para solicitar que o host altere os limites de memória virtual.</span><span class="sxs-lookup"><span data-stu-id="ed167-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed167-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ed167-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed167-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ed167-105">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="ed167-106">no Um ponteiro para um objeto [IGCHostControl](igchostcontrol-interface.md) que permite que o coletor de lixo solicite o host para alterar os limites de memória virtual.</span><span class="sxs-lookup"><span data-stu-id="ed167-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed167-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed167-107">Requirements</span></span>  

 <span data-ttu-id="ed167-108">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed167-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed167-109">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ed167-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed167-110">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed167-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed167-111">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed167-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed167-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed167-112">See also</span></span>

- [<span data-ttu-id="ed167-113">Interface ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed167-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
