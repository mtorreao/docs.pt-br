---
title: Interface ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: dee5108439610b67c3397cebcd8ee5f84d4eacea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723630"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="67275-102">Interface ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="67275-102">ICLRDataTarget2 Interface</span></span>

<span data-ttu-id="67275-103">Uma subclasse de [ICLRDataTarget](iclrdatatarget-interface.md) que é usada pela camada de serviços de acesso a dados para manipular regiões de memória virtual no processo de destino.</span><span class="sxs-lookup"><span data-stu-id="67275-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67275-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="67275-104">Methods</span></span>  
  
|<span data-ttu-id="67275-105">Método</span><span class="sxs-lookup"><span data-stu-id="67275-105">Method</span></span>|<span data-ttu-id="67275-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="67275-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67275-107">Método AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="67275-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="67275-108">Aloca memória no espaço de endereço do processo de destino.</span><span class="sxs-lookup"><span data-stu-id="67275-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="67275-109">Método FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="67275-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="67275-110">Libera a memória que foi alocada anteriormente no espaço de endereço do processo de destino.</span><span class="sxs-lookup"><span data-stu-id="67275-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67275-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="67275-111">Remarks</span></span>  

 <span data-ttu-id="67275-112">O cliente da API (ou seja, o depurador) deve implementar a interface conforme o apropriado para o processo de destino específico.</span><span class="sxs-lookup"><span data-stu-id="67275-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="67275-113">Por exemplo, um processo dinâmico teria uma implementação diferente da implementação de um despejo de memória.</span><span class="sxs-lookup"><span data-stu-id="67275-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="67275-114">O destino pode não oferecer suporte à modificação de suas regiões de memória.</span><span class="sxs-lookup"><span data-stu-id="67275-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67275-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67275-115">Requirements</span></span>  

 <span data-ttu-id="67275-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67275-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67275-117">**Cabeçalho:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="67275-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="67275-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67275-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67275-119">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67275-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67275-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="67275-120">See also</span></span>

- [<span data-ttu-id="67275-121">Interface ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="67275-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="67275-122">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="67275-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
