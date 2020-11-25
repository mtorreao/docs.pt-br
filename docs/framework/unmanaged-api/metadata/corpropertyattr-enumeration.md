---
title: Enumeração CorPropertyAttr
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: d76de80f87a8e5a63eac9f6a413f2efb0e394b0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706118"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="df91a-102">Enumeração CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="df91a-102">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="df91a-103">Contém valores que descrevem os metadados de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="df91a-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df91a-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df91a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="df91a-105">Membros</span><span class="sxs-lookup"><span data-stu-id="df91a-105">Members</span></span>  
  
|<span data-ttu-id="df91a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="df91a-106">Member</span></span>|<span data-ttu-id="df91a-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="df91a-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="df91a-108">Especifica que a propriedade é especial e que seu nome descreve como.</span><span class="sxs-lookup"><span data-stu-id="df91a-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="df91a-109">Reservado para uso interno pelo Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="df91a-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="df91a-110">Especifica que os Common Language Runtime APIs internas de metadados devem verificar a codificação do nome da propriedade.</span><span class="sxs-lookup"><span data-stu-id="df91a-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="df91a-111">Especifica que a propriedade tem um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="df91a-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="df91a-112">Não utilizado.</span><span class="sxs-lookup"><span data-stu-id="df91a-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df91a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df91a-113">Requirements</span></span>  

 <span data-ttu-id="df91a-114">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df91a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df91a-115">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="df91a-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="df91a-116">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df91a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df91a-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="df91a-117">See also</span></span>

- [<span data-ttu-id="df91a-118">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="df91a-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
