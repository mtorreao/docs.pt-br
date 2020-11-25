---
title: Estrutura CVStruct
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: db36b94fafe20b58b9bcbb886b8d285326960f67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715570"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="3d488-102">Estrutura CVStruct</span><span class="sxs-lookup"><span data-stu-id="3d488-102">CVStruct Structure</span></span>

<span data-ttu-id="3d488-103">Contém informações que são usadas ao instalar um módulo ou uma imagem composta.</span><span class="sxs-lookup"><span data-stu-id="3d488-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d488-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d488-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="3d488-105">Membros</span><span class="sxs-lookup"><span data-stu-id="3d488-105">Members</span></span>  
  
|<span data-ttu-id="3d488-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3d488-106">Member</span></span>|<span data-ttu-id="3d488-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="3d488-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3d488-108">Principal</span><span class="sxs-lookup"><span data-stu-id="3d488-108">Major</span></span>|<span data-ttu-id="3d488-109">Número de Build da versão principal.</span><span class="sxs-lookup"><span data-stu-id="3d488-109">Major version build number.</span></span>|  
|<span data-ttu-id="3d488-110">Secundária</span><span class="sxs-lookup"><span data-stu-id="3d488-110">Minor</span></span>|<span data-ttu-id="3d488-111">Número de Build da versão secundária.</span><span class="sxs-lookup"><span data-stu-id="3d488-111">Minor version build number.</span></span>|  
|<span data-ttu-id="3d488-112">Sub</span><span class="sxs-lookup"><span data-stu-id="3d488-112">Sub</span></span>|<span data-ttu-id="3d488-113">Número de subcompilação.</span><span class="sxs-lookup"><span data-stu-id="3d488-113">Sub-build number.</span></span>|  
|<span data-ttu-id="3d488-114">Compilação</span><span class="sxs-lookup"><span data-stu-id="3d488-114">Build</span></span>|<span data-ttu-id="3d488-115">Número da compilação.</span><span class="sxs-lookup"><span data-stu-id="3d488-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d488-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d488-116">Requirements</span></span>  

 <span data-ttu-id="3d488-117">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d488-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d488-118">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3d488-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d488-119">**Biblioteca:** Usado como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d488-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d488-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d488-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d488-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="3d488-121">See also</span></span>

- [<span data-ttu-id="3d488-122">Estruturas de metadados</span><span class="sxs-lookup"><span data-stu-id="3d488-122">Metadata Structures</span></span>](metadata-structures.md)
