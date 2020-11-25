---
title: Enumeração CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: cb65663ec1c1562009d0281c2e176b628b6366b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732171"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="d02a4-102">Enumeração CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="d02a4-102">CorDebugCodeInvokePurpose Enumeration</span></span>

<span data-ttu-id="d02a4-103">Descreve por que uma função exportada chama código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d02a4-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d02a4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d02a4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="d02a4-105">Membros</span><span class="sxs-lookup"><span data-stu-id="d02a4-105">Members</span></span>  
  
|<span data-ttu-id="d02a4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d02a4-106">Member</span></span>|<span data-ttu-id="d02a4-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="d02a4-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="d02a4-108">Nenhum ou desconhecido.</span><span class="sxs-lookup"><span data-stu-id="d02a4-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="d02a4-109">O código gerenciado será executado em qualquer ponto de entrada gerenciado, como um p-invoke inverso.</span><span class="sxs-lookup"><span data-stu-id="d02a4-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="d02a4-110">Qualquer finalidade mais detalhada é desconhecida pelo runtime.</span><span class="sxs-lookup"><span data-stu-id="d02a4-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="d02a4-111">O código gerenciado executará um construtor estático.</span><span class="sxs-lookup"><span data-stu-id="d02a4-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="d02a4-112">O código gerenciado executará a implementação de um método de interface que foi chamado.</span><span class="sxs-lookup"><span data-stu-id="d02a4-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d02a4-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="d02a4-113">Remarks</span></span>  

 <span data-ttu-id="d02a4-114">Essa enumeração é usada pelo método [ICorDebugProcess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) para fornecer informações sobre como percorrer código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d02a4-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d02a4-115">Essa enumeração destina-se ao uso em cenários de depuração .NET Native apenas.</span><span class="sxs-lookup"><span data-stu-id="d02a4-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d02a4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d02a4-116">Requirements</span></span>  

 <span data-ttu-id="d02a4-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d02a4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d02a4-118">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d02a4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d02a4-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d02a4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d02a4-120">**.NET Framework versões:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d02a4-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02a4-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="d02a4-121">See also</span></span>

- [<span data-ttu-id="d02a4-122">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="d02a4-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="d02a4-123">Depuração</span><span class="sxs-lookup"><span data-stu-id="d02a4-123">Debugging</span></span>](index.md)
