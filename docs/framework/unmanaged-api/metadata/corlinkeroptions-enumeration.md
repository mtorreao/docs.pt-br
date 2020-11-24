---
title: Enumeração CorLinkerOptions
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 188301d31b2fcfaf7b1c6139111e8f1296ccf7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677221"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="4aa8c-102">Enumeração CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="4aa8c-102">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="4aa8c-103">Especifica sinalizadores para selecionar opções para o vinculador de metadados.</span><span class="sxs-lookup"><span data-stu-id="4aa8c-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa8c-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4aa8c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="4aa8c-105">Membros</span><span class="sxs-lookup"><span data-stu-id="4aa8c-105">Members</span></span>  
  
|<span data-ttu-id="4aa8c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4aa8c-106">Member</span></span>|<span data-ttu-id="4aa8c-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4aa8c-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="4aa8c-108">Os tipos privados e as funções globais não são preservadas.</span><span class="sxs-lookup"><span data-stu-id="4aa8c-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="4aa8c-109">Os tipos privados e as funções globais são preservados.</span><span class="sxs-lookup"><span data-stu-id="4aa8c-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4aa8c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4aa8c-110">Requirements</span></span>  

 <span data-ttu-id="4aa8c-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aa8c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aa8c-112">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="4aa8c-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4aa8c-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aa8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa8c-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="4aa8c-114">See also</span></span>

- [<span data-ttu-id="4aa8c-115">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="4aa8c-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
