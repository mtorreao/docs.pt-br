---
title: Interface ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6087411e8d23a9c3c97cb97ac8159d436e24759b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731820"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="8d231-102">Interface ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="8d231-102">ICorDebugLoadedModule Interface</span></span>

<span data-ttu-id="8d231-103">Fornece informações sobre um módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="8d231-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d231-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d231-104">Methods</span></span>  
  
|<span data-ttu-id="8d231-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d231-105">Method</span></span>|<span data-ttu-id="8d231-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8d231-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d231-107">Método GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="8d231-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="8d231-108">Obtém o endereço base do módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="8d231-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="8d231-109">Método GetName</span><span class="sxs-lookup"><span data-stu-id="8d231-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="8d231-110">Obtém o nome do módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="8d231-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="8d231-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="8d231-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="8d231-112">Obtém o tamanho em bytes do módulo carregado.</span><span class="sxs-lookup"><span data-stu-id="8d231-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d231-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="8d231-113">Remarks</span></span>  

 <span data-ttu-id="8d231-114">A `ICorDebugLoadedModule` interface é implementada por um depurador e é usada pelas interfaces de depuração CLR para obter informações sobre o módulo carregado do depurador.</span><span class="sxs-lookup"><span data-stu-id="8d231-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d231-115">Essa interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8d231-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8d231-116">Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.</span><span class="sxs-lookup"><span data-stu-id="8d231-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d231-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d231-117">Requirements</span></span>  

 <span data-ttu-id="8d231-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d231-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d231-119">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d231-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d231-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d231-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d231-121">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d231-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d231-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d231-122">See also</span></span>

- [<span data-ttu-id="8d231-123">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="8d231-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8d231-124">Depuração</span><span class="sxs-lookup"><span data-stu-id="8d231-124">Debugging</span></span>](index.md)
