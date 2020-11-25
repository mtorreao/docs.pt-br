---
title: Coclass ComCallUnmarshal
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731716"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="b3dd0-102">Coclass ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="b3dd0-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="b3dd0-103">Fornece interfaces para gerenciar o marshaling de ponteiros de interface.</span><span class="sxs-lookup"><span data-stu-id="b3dd0-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3dd0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b3dd0-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="b3dd0-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b3dd0-105">Interfaces</span></span>  
  
|<span data-ttu-id="b3dd0-106">Interface</span><span class="sxs-lookup"><span data-stu-id="b3dd0-106">Interface</span></span>|<span data-ttu-id="b3dd0-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3dd0-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="b3dd0-108">Fornece métodos para criar, inicializar e gerenciar um proxy em um processo de cliente.</span><span class="sxs-lookup"><span data-stu-id="b3dd0-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3dd0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3dd0-109">Requirements</span></span>  

 <span data-ttu-id="b3dd0-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3dd0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3dd0-111">**Cabeçalho:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="b3dd0-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b3dd0-112">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3dd0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3dd0-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3dd0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dd0-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="b3dd0-114">See also</span></span>

- [<span data-ttu-id="b3dd0-115">Hospedando coclasses</span><span class="sxs-lookup"><span data-stu-id="b3dd0-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
