---
title: Enumeração CorSaveSize
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 81d47a3e4d72f991dc15924e7ff1ecc8df2e7322
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706043"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="9b945-102">Enumeração CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="9b945-102">CorSaveSize Enumeration</span></span>

<span data-ttu-id="9b945-103">Contém valores que indicam o nível de precisão necessário ao consultar o tamanho de uma operação de salvamento.</span><span class="sxs-lookup"><span data-stu-id="9b945-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b945-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9b945-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="9b945-105">Membros</span><span class="sxs-lookup"><span data-stu-id="9b945-105">Members</span></span>  
  
|<span data-ttu-id="9b945-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9b945-106">Member</span></span>|<span data-ttu-id="9b945-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9b945-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="9b945-108">Especifica que o valor de retorno deve ser exato.</span><span class="sxs-lookup"><span data-stu-id="9b945-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="9b945-109">Especifica que o valor de retorno deve ser estimado.</span><span class="sxs-lookup"><span data-stu-id="9b945-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="9b945-110">Especifica que os tipos descartados devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="9b945-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b945-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b945-111">Requirements</span></span>  

 <span data-ttu-id="9b945-112">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b945-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b945-113">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="9b945-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9b945-114">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b945-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b945-115">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b945-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b945-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b945-116">See also</span></span>

- [<span data-ttu-id="9b945-117">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="9b945-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
