---
title: Método SetNonAssemblyFlags
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
ms.openlocfilehash: b7bcf530947c161decc9c01c07df310550d69738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733757"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="f03b1-102">Método SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="f03b1-102">SetNonAssemblyFlags Method</span></span>

<span data-ttu-id="f03b1-103">Define sinalizadores que não são específicos do assembly.</span><span class="sxs-lookup"><span data-stu-id="f03b1-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03b1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f03b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f03b1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f03b1-105">Parameters</span></span>  

 `afFlags`  
 <span data-ttu-id="f03b1-106">Sinalizadores ALink.</span><span class="sxs-lookup"><span data-stu-id="f03b1-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f03b1-107">Valor Retornado</span><span class="sxs-lookup"><span data-stu-id="f03b1-107">Return Value</span></span>  

 <span data-ttu-id="f03b1-108">Retorna S_OK se o método tiver sucesso.</span><span class="sxs-lookup"><span data-stu-id="f03b1-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03b1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f03b1-109">Requirements</span></span>  

 <span data-ttu-id="f03b1-110">Requer ALink. h</span><span class="sxs-lookup"><span data-stu-id="f03b1-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03b1-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="f03b1-111">See also</span></span>

- [<span data-ttu-id="f03b1-112">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="f03b1-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f03b1-113">Interface IALink2</span><span class="sxs-lookup"><span data-stu-id="f03b1-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f03b1-114">API do ALink</span><span class="sxs-lookup"><span data-stu-id="f03b1-114">ALink API</span></span>](index.md)
