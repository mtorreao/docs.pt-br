---
title: Enumeração CorValidatorModuleType
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 2fb7f11677870f7d53439f1867f167fabe70b22a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723838"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="0a5dd-102">Enumeração CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="0a5dd-102">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="0a5dd-103">Especifica o tipo de um módulo.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5dd-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0a5dd-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="0a5dd-105">Membros</span><span class="sxs-lookup"><span data-stu-id="0a5dd-105">Members</span></span>  
  
|<span data-ttu-id="0a5dd-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0a5dd-106">Member</span></span>|<span data-ttu-id="0a5dd-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="0a5dd-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="0a5dd-108">O módulo é um tipo inválido.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="0a5dd-109">O valor mínimo da `CorValidatorModuleType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="0a5dd-110">O módulo é um arquivo executável portátil (PE).</span><span class="sxs-lookup"><span data-stu-id="0a5dd-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="0a5dd-111">O módulo é um arquivo. obj.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="0a5dd-112">O módulo é uma sessão do depurador de editar e continuar.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="0a5dd-113">O módulo é um que foi compilado incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="0a5dd-114">O valor máximo da `CorValidatorModuleType` enumeração.</span><span class="sxs-lookup"><span data-stu-id="0a5dd-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a5dd-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a5dd-115">Requirements</span></span>  

 <span data-ttu-id="0a5dd-116">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a5dd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a5dd-117">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a5dd-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a5dd-118">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a5dd-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a5dd-119">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a5dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a5dd-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="0a5dd-120">See also</span></span>

- [<span data-ttu-id="0a5dd-121">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="0a5dd-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
