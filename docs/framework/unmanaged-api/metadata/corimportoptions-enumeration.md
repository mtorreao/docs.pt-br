---
title: Enumeração CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 3d5989d43644088403a77f26c02af9ffaae0732b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677200"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="f5ad9-102">Enumeração CorImportOptions</span><span class="sxs-lookup"><span data-stu-id="f5ad9-102">CorImportOptions Enumeration</span></span>

<span data-ttu-id="f5ad9-103">Contém valores de sinalizador que controlam o comportamento durante a importação de um assembly fora do escopo atual.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ad9-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5ad9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="f5ad9-105">Membros</span><span class="sxs-lookup"><span data-stu-id="f5ad9-105">Members</span></span>  
  
|<span data-ttu-id="f5ad9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f5ad9-106">Member</span></span>|<span data-ttu-id="f5ad9-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="f5ad9-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="f5ad9-108">Indica o comportamento padrão, que é para ignorar os registros excluídos.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="f5ad9-109">Indica que todos os metadados devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="f5ad9-110">Indica que todos os TypeDefs, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="f5ad9-111">Indica que todos os MethodDefs, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="f5ad9-112">Indica que todos os FieldDefs, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="f5ad9-113">Indica que todos os PropertyDefs, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="f5ad9-114">Indica que todos os EventDefs, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="f5ad9-115">Indica que todos os atributos personalizados, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="f5ad9-116">Indica que todos os tipos exportados, incluindo aqueles excluídos, devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f5ad9-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5ad9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5ad9-117">Requirements</span></span>  

 <span data-ttu-id="f5ad9-118">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ad9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ad9-119">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f5ad9-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f5ad9-120">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ad9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ad9-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5ad9-121">See also</span></span>

- [<span data-ttu-id="f5ad9-122">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="f5ad9-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
