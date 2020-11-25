---
title: Interface ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703623"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="580ad-102">Interface ICLRDataEnumMemoryRegionsCallback</span><span class="sxs-lookup"><span data-stu-id="580ad-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="580ad-103">Fornece um método de retorno de chamada para [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) para relatar ao depurador o resultado de uma tentativa de enumerar uma região especificada de memória.</span><span class="sxs-lookup"><span data-stu-id="580ad-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="580ad-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="580ad-104">Methods</span></span>  
  
|<span data-ttu-id="580ad-105">Método</span><span class="sxs-lookup"><span data-stu-id="580ad-105">Method</span></span>|<span data-ttu-id="580ad-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="580ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="580ad-107">Método EnumMemoryRegion</span><span class="sxs-lookup"><span data-stu-id="580ad-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="580ad-108">Chamado por `ICLRDataEnumMemoryRegions::EnumMemoryRegions` para relatar ao depurador o resultado de uma tentativa de enumerar uma região especificada de memória.</span><span class="sxs-lookup"><span data-stu-id="580ad-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="580ad-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="580ad-109">Requirements</span></span>  

 <span data-ttu-id="580ad-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="580ad-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="580ad-111">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="580ad-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="580ad-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="580ad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="580ad-113">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="580ad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580ad-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="580ad-114">See also</span></span>

- [<span data-ttu-id="580ad-115">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="580ad-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
