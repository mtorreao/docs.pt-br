---
title: Estrutura COR_VERSION
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: 874c0520482cc5a3bbfcdd17924edee84fe91ff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675315"
---
# <a name="cor_version-structure"></a><span data-ttu-id="0ae05-102">Estrutura COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="0ae05-102">COR_VERSION Structure</span></span>

<span data-ttu-id="0ae05-103">Armazena o número da versão com quatro partes padrão do CLR.</span><span class="sxs-lookup"><span data-stu-id="0ae05-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae05-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0ae05-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="0ae05-105">Membros</span><span class="sxs-lookup"><span data-stu-id="0ae05-105">Members</span></span>  
  
|<span data-ttu-id="0ae05-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0ae05-106">Member</span></span>|<span data-ttu-id="0ae05-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0ae05-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="0ae05-108">O número da versão principal.</span><span class="sxs-lookup"><span data-stu-id="0ae05-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="0ae05-109">O número da versão secundária.</span><span class="sxs-lookup"><span data-stu-id="0ae05-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="0ae05-110">O número de build.</span><span class="sxs-lookup"><span data-stu-id="0ae05-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="0ae05-111">O número da subcompilação.</span><span class="sxs-lookup"><span data-stu-id="0ae05-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ae05-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="0ae05-112">Remarks</span></span>  

 <span data-ttu-id="0ae05-113">Se o número de versão for 1.0.3705.288, 1 será o número de versão principal, 0 é o número de versão secundária, 3705 é o número da compilação e 288 é o número da subcompilação.</span><span class="sxs-lookup"><span data-stu-id="0ae05-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae05-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ae05-114">Requirements</span></span>  

 <span data-ttu-id="0ae05-115">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae05-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae05-116">**Cabeçalho:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="0ae05-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="0ae05-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ae05-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ae05-118">**.NET Framework versões:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae05-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae05-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ae05-119">See also</span></span>

- [<span data-ttu-id="0ae05-120">Estruturas de depuração</span><span class="sxs-lookup"><span data-stu-id="0ae05-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="0ae05-121">Depuração</span><span class="sxs-lookup"><span data-stu-id="0ae05-121">Debugging</span></span>](index.md)
