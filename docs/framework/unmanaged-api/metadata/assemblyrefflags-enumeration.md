---
title: Enumeração AssemblyRefFlags
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732756"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="2ac6c-102">Enumeração AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="2ac6c-102">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="2ac6c-103">Contém valores que descrevem os recursos de uma referência de assembly.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac6c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2ac6c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="2ac6c-105">Membros</span><span class="sxs-lookup"><span data-stu-id="2ac6c-105">Members</span></span>  
  
|<span data-ttu-id="2ac6c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2ac6c-106">Member</span></span>|<span data-ttu-id="2ac6c-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="2ac6c-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="2ac6c-108">Especifica que a referência de assembly contém informações completas e sem hash sobre o Publicador do assembly.</span><span class="sxs-lookup"><span data-stu-id="2ac6c-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ac6c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ac6c-109">Requirements</span></span>  

 <span data-ttu-id="2ac6c-110">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac6c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac6c-111">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2ac6c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ac6c-112">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac6c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac6c-113">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ac6c-113">See also</span></span>

- [<span data-ttu-id="2ac6c-114">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="2ac6c-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="2ac6c-115">Interface IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="2ac6c-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="2ac6c-116">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="2ac6c-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
