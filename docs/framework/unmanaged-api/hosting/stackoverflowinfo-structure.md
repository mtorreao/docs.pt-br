---
title: Estrutura StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729922"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="ee765-102">Estrutura StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="ee765-102">StackOverflowInfo Structure</span></span>

<span data-ttu-id="ee765-103">Armazena o tipo de estouro que ocorreu e informações sobre a exceção que foi lançada devido ao estouro.</span><span class="sxs-lookup"><span data-stu-id="ee765-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee765-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ee765-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="ee765-105">Membros</span><span class="sxs-lookup"><span data-stu-id="ee765-105">Members</span></span>  
  
|<span data-ttu-id="ee765-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ee765-106">Member</span></span>|<span data-ttu-id="ee765-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="ee765-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="ee765-108">Um valor da enumeração [StackOverflowType](stackoverflowtype-enumeration.md) que especifica o tipo de estouro.</span><span class="sxs-lookup"><span data-stu-id="ee765-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="ee765-109">Um ponteiro para um `EXCEPTION_POINTERS` objeto Win32, que contém um registro de exceção com uma descrição independente de computador de uma exceção e um registro de contexto com uma descrição dependente de computador do contexto do processador no momento da exceção.</span><span class="sxs-lookup"><span data-stu-id="ee765-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee765-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="ee765-110">Remarks</span></span>  

 <span data-ttu-id="ee765-111">Um `StackOverflowInfo` objeto é passado para o método [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) para `Event_StackOverflow` eventos.</span><span class="sxs-lookup"><span data-stu-id="ee765-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee765-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee765-112">Requirements</span></span>  

 <span data-ttu-id="ee765-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee765-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee765-114">**Cabeçalho:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="ee765-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ee765-115">**Biblioteca:** Incluído como um recurso no MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee765-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee765-116">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee765-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee765-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee765-117">See also</span></span>

- [<span data-ttu-id="ee765-118">Estruturas de hospedagem</span><span class="sxs-lookup"><span data-stu-id="ee765-118">Hosting Structures</span></span>](hosting-structures.md)
