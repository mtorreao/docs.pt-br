---
title: Enumeração COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 2fbcbb6f6115ec48085b533dbf5611054a8235c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696733"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="b4420-102">Enumeração COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="b4420-102">COR_PRF_STATIC_TYPE Enumeration</span></span>

<span data-ttu-id="b4420-103">Indica se um campo é estático e, em caso positivo, a qualidade estática aplicada ao campo.</span><span class="sxs-lookup"><span data-stu-id="b4420-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="b4420-104">Esses valores podem ser combinados usando-se a operação OR de bits para indicar que o campo tem várias qualidades estáticas diferentes.</span><span class="sxs-lookup"><span data-stu-id="b4420-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4420-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4420-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="b4420-106">Membros</span><span class="sxs-lookup"><span data-stu-id="b4420-106">Members</span></span>  
  
|<span data-ttu-id="b4420-107">Membro</span><span class="sxs-lookup"><span data-stu-id="b4420-107">Member</span></span>|<span data-ttu-id="b4420-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b4420-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="b4420-109">O campo não é estático.</span><span class="sxs-lookup"><span data-stu-id="b4420-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="b4420-110">O campo é um domínio de aplicativo estático.</span><span class="sxs-lookup"><span data-stu-id="b4420-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="b4420-111">O campo é thread-estático.</span><span class="sxs-lookup"><span data-stu-id="b4420-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="b4420-112">O campo é de contexto estático.</span><span class="sxs-lookup"><span data-stu-id="b4420-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="b4420-113">O campo é um endereço virtual relativo (RVA)-estático.</span><span class="sxs-lookup"><span data-stu-id="b4420-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4420-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4420-114">Requirements</span></span>  

 <span data-ttu-id="b4420-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4420-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4420-116">**Cabeçalho:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b4420-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4420-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4420-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4420-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4420-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4420-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4420-119">See also</span></span>

- [<span data-ttu-id="b4420-120">Criando perfil de enumerações</span><span class="sxs-lookup"><span data-stu-id="b4420-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
