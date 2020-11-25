---
title: Estrutura COR_PRF_FUNCTION_ARGUMENT_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 028395b1c8677d07d4a6481740ecdc7ebb48c180
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718508"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="11e22-102">Estrutura COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="11e22-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="11e22-103">Representa um bloco de argumentos de função armazenados de forma contígua em ordem da esquerda para a direita na memória.</span><span class="sxs-lookup"><span data-stu-id="11e22-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11e22-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11e22-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="11e22-105">Membros</span><span class="sxs-lookup"><span data-stu-id="11e22-105">Members</span></span>  
  
|<span data-ttu-id="11e22-106">Membros</span><span class="sxs-lookup"><span data-stu-id="11e22-106">Members</span></span>|<span data-ttu-id="11e22-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="11e22-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="11e22-108">O endereço inicial do bloco.</span><span class="sxs-lookup"><span data-stu-id="11e22-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="11e22-109">O comprimento do bloco contíguo.</span><span class="sxs-lookup"><span data-stu-id="11e22-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11e22-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11e22-110">Requirements</span></span>  

 <span data-ttu-id="11e22-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11e22-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11e22-112">**Cabeçalho:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="11e22-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="11e22-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11e22-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11e22-114">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11e22-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e22-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="11e22-115">See also</span></span>

- [<span data-ttu-id="11e22-116">Estruturas de criação de perfil</span><span class="sxs-lookup"><span data-stu-id="11e22-116">Profiling Structures</span></span>](profiling-structures.md)
