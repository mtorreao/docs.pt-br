---
title: Enumeração CorFileFlags
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: 70d789f417700734b546cac6ff527ed5aa84fcf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688621"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="5b6e0-102">Enumeração CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="5b6e0-102">CorFileFlags Enumeration</span></span>

<span data-ttu-id="5b6e0-103">Contém valores que descrevem o tipo de arquivo definido em uma chamada para [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="5b6e0-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6e0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5b6e0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5b6e0-105">Membros</span><span class="sxs-lookup"><span data-stu-id="5b6e0-105">Members</span></span>  
  
|<span data-ttu-id="5b6e0-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5b6e0-106">Member</span></span>|<span data-ttu-id="5b6e0-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="5b6e0-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="5b6e0-108">Indica que o arquivo não é um arquivo de recurso.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="5b6e0-109">Indica que o arquivo, possivelmente um arquivo de recurso, não contém metadados.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b6e0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b6e0-110">Requirements</span></span>  

 <span data-ttu-id="5b6e0-111">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b6e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6e0-112">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="5b6e0-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5b6e0-113">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6e0-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b6e0-114">See also</span></span>

- [<span data-ttu-id="5b6e0-115">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="5b6e0-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
