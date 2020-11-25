---
title: Interface ICorProfilerInfo5
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: a6206e35280e073df2abfb7ae46aa84d34b30208
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733796"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="79f8e-102">Interface ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="79f8e-102">ICorProfilerInfo5 Interface</span></span>

<span data-ttu-id="79f8e-103">[Com suporte no .NET Framework 4.5.2 e versões posteriores]</span><span class="sxs-lookup"><span data-stu-id="79f8e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="79f8e-104">Uma subclasse de [ICorProfilerInfo4](icorprofilerinfo4-interface.md) que fornece métodos para uso por infilers de código para se comunicar com o Common Language Runtime (CLR) para controlar o monitoramento de eventos.</span><span class="sxs-lookup"><span data-stu-id="79f8e-104">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79f8e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="79f8e-105">Methods</span></span>  
  
|<span data-ttu-id="79f8e-106">Método</span><span class="sxs-lookup"><span data-stu-id="79f8e-106">Method</span></span>|<span data-ttu-id="79f8e-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="79f8e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79f8e-108">Método GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="79f8e-108">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="79f8e-109">Obtém as categorias de eventos atuais para os quais o criador de perfis deseja receber notificações do CLR.</span><span class="sxs-lookup"><span data-stu-id="79f8e-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="79f8e-110">Método SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="79f8e-110">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="79f8e-111">Define um valor que especifica os tipos de eventos para os quais o criador de perfil deseja receber notificações de evento do CLR.</span><span class="sxs-lookup"><span data-stu-id="79f8e-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79f8e-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="79f8e-112">Remarks</span></span>  

 <span data-ttu-id="79f8e-113">Os métodos disponíveis nesta interface destinam-se a substituir os métodos [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) e [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="79f8e-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79f8e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79f8e-114">Requirements</span></span>  

 <span data-ttu-id="79f8e-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79f8e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79f8e-116">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="79f8e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79f8e-117">**.NET Framework versões:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79f8e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f8e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="79f8e-118">See also</span></span>

- [<span data-ttu-id="79f8e-119">Criação de perfil de interfaces</span><span class="sxs-lookup"><span data-stu-id="79f8e-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
