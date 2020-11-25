---
title: Enumeração CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: e251bf67adcaf2bbd6565eda068d487eb0d70efd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725762"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="78f44-102">Enumeração CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="78f44-102">CorDebugUnmappedStop Enumeration</span></span>

<span data-ttu-id="78f44-103">Especifica o tipo de código não mapeado que pode disparar uma interrupção na execução do código pelo passador.</span><span class="sxs-lookup"><span data-stu-id="78f44-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f44-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78f44-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="78f44-105">Membros</span><span class="sxs-lookup"><span data-stu-id="78f44-105">Members</span></span>  
  
|<span data-ttu-id="78f44-106">Membro</span><span class="sxs-lookup"><span data-stu-id="78f44-106">Member</span></span>|<span data-ttu-id="78f44-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="78f44-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="78f44-108">Não pare em nenhum tipo de código não mapeado.</span><span class="sxs-lookup"><span data-stu-id="78f44-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="78f44-109">Parar no código de prólogo.</span><span class="sxs-lookup"><span data-stu-id="78f44-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="78f44-110">Pare no código epílogo.</span><span class="sxs-lookup"><span data-stu-id="78f44-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="78f44-111">Pare no código que não tem informações de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="78f44-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="78f44-112">Pare no código não mapeado que não caiba nas categorias prólogo, epílogo, no-Mapping-Information ou unmanaged.</span><span class="sxs-lookup"><span data-stu-id="78f44-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="78f44-113">Parar em código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="78f44-113">Stop in unmanaged code.</span></span> <span data-ttu-id="78f44-114">Esse valor é válido somente com depuração de interoperabilidade.</span><span class="sxs-lookup"><span data-stu-id="78f44-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="78f44-115">Parar em todos os tipos de código não mapeado.</span><span class="sxs-lookup"><span data-stu-id="78f44-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78f44-116">Comentários</span><span class="sxs-lookup"><span data-stu-id="78f44-116">Remarks</span></span>  

 <span data-ttu-id="78f44-117">Use o método [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) para definir os sinalizadores que especificam o código não mapeado no qual o stepper será interrompido.</span><span class="sxs-lookup"><span data-stu-id="78f44-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f44-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78f44-118">Requirements</span></span>  

 <span data-ttu-id="78f44-119">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78f44-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f44-120">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78f44-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78f44-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78f44-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78f44-122">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f44-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f44-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="78f44-123">See also</span></span>

- [<span data-ttu-id="78f44-124">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="78f44-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
