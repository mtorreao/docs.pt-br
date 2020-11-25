---
title: Método CloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 4e8aeef3520c4d5c9735b2c8975ac1e39470ba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717013"
---
# <a name="closeassembly-method"></a><span data-ttu-id="38fca-102">Método CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="38fca-102">CloseAssembly Method</span></span>

<span data-ttu-id="38fca-103">Finaliza operações de assembly.</span><span class="sxs-lookup"><span data-stu-id="38fca-103">Finalizes assembly operations.</span></span> <span data-ttu-id="38fca-104">Chame esse método antes de iniciar um novo assembly ou módulo não associado.</span><span class="sxs-lookup"><span data-stu-id="38fca-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38fca-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="38fca-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="38fca-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="38fca-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="38fca-107">ID do assembly.</span><span class="sxs-lookup"><span data-stu-id="38fca-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38fca-108">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="38fca-108">Return Value</span></span>  

 <span data-ttu-id="38fca-109">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="38fca-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38fca-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38fca-110">Requirements</span></span>  

 <span data-ttu-id="38fca-111">Requer ALink. h.</span><span class="sxs-lookup"><span data-stu-id="38fca-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fca-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="38fca-112">See also</span></span>

- [<span data-ttu-id="38fca-113">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="38fca-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="38fca-114">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="38fca-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="38fca-115">API do ALink</span><span class="sxs-lookup"><span data-stu-id="38fca-115">ALink API</span></span>](index.md)
