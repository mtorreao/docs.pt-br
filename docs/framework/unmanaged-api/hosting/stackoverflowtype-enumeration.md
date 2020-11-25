---
title: Enumeração StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: bbdc68721378e6bbb09f5e4eade08e2e6e03b097
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729900"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="683b5-102">Enumeração StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="683b5-102">StackOverflowType Enumeration</span></span>

<span data-ttu-id="683b5-103">Contém valores que indicam a causa subjacente de um evento de estouro de pilha.</span><span class="sxs-lookup"><span data-stu-id="683b5-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="683b5-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="683b5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="683b5-105">Membros</span><span class="sxs-lookup"><span data-stu-id="683b5-105">Members</span></span>  
  
|<span data-ttu-id="683b5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="683b5-106">Member</span></span>|<span data-ttu-id="683b5-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="683b5-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="683b5-108">O estouro de pilha foi causado pelo mecanismo de execução.</span><span class="sxs-lookup"><span data-stu-id="683b5-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="683b5-109">O estouro de pilha foi causado por código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="683b5-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="683b5-110">O estouro de pilha foi causado por código não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="683b5-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="683b5-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="683b5-111">Remarks</span></span>  

 <span data-ttu-id="683b5-112">Essas informações são passadas para o host por meio de uma chamada para o método [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="683b5-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="683b5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="683b5-113">Requirements</span></span>  

 <span data-ttu-id="683b5-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="683b5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="683b5-115">**Cabeçalho:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="683b5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="683b5-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="683b5-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="683b5-117">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="683b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683b5-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="683b5-118">See also</span></span>

- [<span data-ttu-id="683b5-119">Hospedando enumerações</span><span class="sxs-lookup"><span data-stu-id="683b5-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
