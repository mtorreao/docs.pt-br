---
title: Interface ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679475"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="a95be-102">Interface ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a95be-102">ICorDebugVariableSymbol Interface</span></span>

<span data-ttu-id="a95be-103">Recupera as informações de símbolo de depuração para uma variável.</span><span class="sxs-lookup"><span data-stu-id="a95be-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a95be-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a95be-104">Methods</span></span>  
  
|<span data-ttu-id="a95be-105">Método</span><span class="sxs-lookup"><span data-stu-id="a95be-105">Method</span></span>|<span data-ttu-id="a95be-106">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="a95be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a95be-107">Método GetName</span><span class="sxs-lookup"><span data-stu-id="a95be-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="a95be-108">Obtém o nome de uma variável.</span><span class="sxs-lookup"><span data-stu-id="a95be-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="a95be-109">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="a95be-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="a95be-110">Obtém o tamanho de uma variável em bytes.</span><span class="sxs-lookup"><span data-stu-id="a95be-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="a95be-111">Método GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a95be-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="a95be-112">Obtém o índice de slot gerenciado de uma variável local.</span><span class="sxs-lookup"><span data-stu-id="a95be-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="a95be-113">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="a95be-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="a95be-114">Obtém o valor de uma variável como uma matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="a95be-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="a95be-115">Método SetValue</span><span class="sxs-lookup"><span data-stu-id="a95be-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="a95be-116">Atribui o valor de uma matriz de bytes a uma variável.</span><span class="sxs-lookup"><span data-stu-id="a95be-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a95be-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="a95be-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a95be-118">Essa interface está disponível somente com .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a95be-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a95be-119">Se você implementar essa interface para cenários ICorDebug fora do .NET Native, o Common Language Runtime ignorará essa interface.</span><span class="sxs-lookup"><span data-stu-id="a95be-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a95be-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a95be-120">Requirements</span></span>  

 <span data-ttu-id="a95be-121">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a95be-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a95be-122">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a95be-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a95be-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a95be-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a95be-124">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a95be-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95be-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="a95be-125">See also</span></span>

- [<span data-ttu-id="a95be-126">Depurando interfaces</span><span class="sxs-lookup"><span data-stu-id="a95be-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a95be-127">Depuração</span><span class="sxs-lookup"><span data-stu-id="a95be-127">Debugging</span></span>](index.md)
