---
title: Estrutura CorDebugGuidToTypeMapping
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 859853521b741f42f1de7921de813941d2501173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729090"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="77a6d-102">Estrutura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="77a6d-102">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="77a6d-103">Mapeia um GUID de Windows Runtime para seu objeto ICorDebugType correspondente.</span><span class="sxs-lookup"><span data-stu-id="77a6d-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a6d-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="77a6d-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="77a6d-105">Membros</span><span class="sxs-lookup"><span data-stu-id="77a6d-105">Members</span></span>  
  
|<span data-ttu-id="77a6d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="77a6d-106">Member</span></span>|<span data-ttu-id="77a6d-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="77a6d-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="77a6d-108">O GUID do tipo de Windows Runtime em cache.</span><span class="sxs-lookup"><span data-stu-id="77a6d-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="77a6d-109">Um ponteiro para um objeto ICorDebugType que fornece informações sobre o tipo armazenado em cache.</span><span class="sxs-lookup"><span data-stu-id="77a6d-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77a6d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77a6d-110">Requirements</span></span>  

 <span data-ttu-id="77a6d-111">**Plataformas:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="77a6d-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="77a6d-112">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77a6d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77a6d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77a6d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77a6d-114">**.NET Framework versões:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a6d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a6d-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="77a6d-115">See also</span></span>

- [<span data-ttu-id="77a6d-116">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="77a6d-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="77a6d-117">Depuração</span><span class="sxs-lookup"><span data-stu-id="77a6d-117">Debugging</span></span>](index.md)
