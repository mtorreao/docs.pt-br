---
title: Enumeração CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: fbe721bad56ec2be434039f00e741ad9a177815f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718963"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="8fad3-102">Enumeração CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="8fad3-102">CorAttributeTargets Enumeration</span></span>

<span data-ttu-id="8fad3-103">Especifica os elementos do aplicativo no qual ele é válido para aplicar um atributo.</span><span class="sxs-lookup"><span data-stu-id="8fad3-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fad3-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8fad3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="8fad3-105">Membros</span><span class="sxs-lookup"><span data-stu-id="8fad3-105">Members</span></span>  
  
|<span data-ttu-id="8fad3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8fad3-106">Member</span></span>|<span data-ttu-id="8fad3-107">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="8fad3-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="8fad3-108">O atributo pode ser aplicado a um assembly.</span><span class="sxs-lookup"><span data-stu-id="8fad3-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="8fad3-109">O atributo pode ser aplicado a um módulo executável portátil (. dll ou. exe).</span><span class="sxs-lookup"><span data-stu-id="8fad3-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="8fad3-110">O atributo pode ser aplicado a uma classe.</span><span class="sxs-lookup"><span data-stu-id="8fad3-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="8fad3-111">Atributo pode ser aplicado a uma estrutura; ou seja, um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="8fad3-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="8fad3-112">O atributo pode ser aplicado a uma enumeração.</span><span class="sxs-lookup"><span data-stu-id="8fad3-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="8fad3-113">O atributo pode ser aplicado a um construtor.</span><span class="sxs-lookup"><span data-stu-id="8fad3-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="8fad3-114">O atributo pode ser aplicado a um método.</span><span class="sxs-lookup"><span data-stu-id="8fad3-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="8fad3-115">O atributo pode ser aplicado a uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="8fad3-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="8fad3-116">O atributo pode ser aplicado a um campo.</span><span class="sxs-lookup"><span data-stu-id="8fad3-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="8fad3-117">O atributo pode ser aplicado a um evento.</span><span class="sxs-lookup"><span data-stu-id="8fad3-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="8fad3-118">O atributo pode ser aplicado a uma interface.</span><span class="sxs-lookup"><span data-stu-id="8fad3-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="8fad3-119">O atributo pode ser aplicado a um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8fad3-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="8fad3-120">O atributo pode ser aplicado a um delegado.</span><span class="sxs-lookup"><span data-stu-id="8fad3-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="8fad3-121">O atributo pode ser aplicado a um parâmetro genérico.</span><span class="sxs-lookup"><span data-stu-id="8fad3-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="8fad3-122">O atributo pode ser aplicado a qualquer elemento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fad3-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="8fad3-123">O atributo pode ser aplicado a um membro de uma classe.</span><span class="sxs-lookup"><span data-stu-id="8fad3-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fad3-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="8fad3-124">Remarks</span></span>  

 <span data-ttu-id="8fad3-125">Os `CorAttributeTargets` valores de enumeração podem ser combinados com uma operação OR bit a bit para obter a combinação preferida.</span><span class="sxs-lookup"><span data-stu-id="8fad3-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="8fad3-126">O `CorAttributeTargets` paraleliza a enumeração gerenciada <xref:System.AttributeTargets?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8fad3-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fad3-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fad3-127">Requirements</span></span>  

 <span data-ttu-id="8fad3-128">**Plataformas:** confira [Requisitos do sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fad3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fad3-129">**Cabeçalho:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="8fad3-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8fad3-130">**.NET Framework versões:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fad3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fad3-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="8fad3-131">See also</span></span>

- [<span data-ttu-id="8fad3-132">Enumerações de metadados</span><span class="sxs-lookup"><span data-stu-id="8fad3-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
