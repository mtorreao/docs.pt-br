---
title: Enumeração CeeSectionAttr
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 4b2fb80298f6eef331b5b7ae4a46222ce97ede6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732728"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="9f040-102">Enumeração CeeSectionAttr</span><span class="sxs-lookup"><span data-stu-id="9f040-102">CeeSectionAttr Enumeration</span></span>

<span data-ttu-id="9f040-103">Fornece valores que especificam atributos de uma seção para uso pela interface [ICeeGen](iceegen-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f040-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f040-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f040-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9f040-105">Membros</span><span class="sxs-lookup"><span data-stu-id="9f040-105">Members</span></span>  
  
|<span data-ttu-id="9f040-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9f040-106">Member</span></span>|<span data-ttu-id="9f040-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="9f040-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="9f040-108">A seção não tem atributos.</span><span class="sxs-lookup"><span data-stu-id="9f040-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="9f040-109">A seção contém dados inicializados que só podem ser lidos, não atualizados.</span><span class="sxs-lookup"><span data-stu-id="9f040-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="9f040-110">A seção contém dados inicializados que podem ser lidos ou atualizados.</span><span class="sxs-lookup"><span data-stu-id="9f040-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="9f040-111">A seção contém código executável que pode ser lido e executado.</span><span class="sxs-lookup"><span data-stu-id="9f040-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f040-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f040-112">Requirements</span></span>  

 <span data-ttu-id="9f040-113">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f040-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f040-114">**Cabeçalho:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9f040-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f040-115">**Biblioteca:** Incluído como um recurso no MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f040-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f040-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f040-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f040-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f040-117">See also</span></span>

- [<span data-ttu-id="9f040-118">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="9f040-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
