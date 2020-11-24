---
title: Método ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 386f975ab0bbbe804fda2bd7567acf24f69e77fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676069"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="c357e-102">Método ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="c357e-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>

<span data-ttu-id="c357e-103">Enumera áreas especificadas de memória.</span><span class="sxs-lookup"><span data-stu-id="c357e-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c357e-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c357e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c357e-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="c357e-105">Parameters</span></span>  

 `callback`  
 <span data-ttu-id="c357e-106">no Um ponteiro para uma instância de [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) que é chamada por esse método para cada região de memória que está sendo enumerada para notificar o depurador do resultado.</span><span class="sxs-lookup"><span data-stu-id="c357e-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="c357e-107">A enumeração de regiões de memória continua mesmo que o retorno de chamada indique uma falha.</span><span class="sxs-lookup"><span data-stu-id="c357e-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="c357e-108">no Não usado.</span><span class="sxs-lookup"><span data-stu-id="c357e-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="c357e-109">no Um valor da enumeração [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) que especifica as regiões de memória a serem enumeradas.</span><span class="sxs-lookup"><span data-stu-id="c357e-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c357e-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="c357e-110">Remarks</span></span>  

 <span data-ttu-id="c357e-111">Esse método usa a instância [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) especificada para notificar o chamador de resultados.</span><span class="sxs-lookup"><span data-stu-id="c357e-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c357e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c357e-112">Requirements</span></span>  

 <span data-ttu-id="c357e-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c357e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c357e-114">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c357e-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c357e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c357e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c357e-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c357e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c357e-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="c357e-117">See also</span></span>

- [<span data-ttu-id="c357e-118">Interface ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="c357e-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
